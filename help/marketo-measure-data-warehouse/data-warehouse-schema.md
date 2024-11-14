---
unique-page-id: 35586140
description: Data Warehouse 스키마 - Marketo Measure - 제품 설명서
title: Data Warehouse 스키마
exl-id: f1895eb1-a32d-4c43-93fb-0aa838527946
feature: Data Warehouse
source-git-commit: 3ad812a05671f277d3dd3f9bc58e3b2ea3606e71
workflow-type: tm+mt
source-wordcount: '21110'
ht-degree: 3%

---

# Data Warehouse 스키마 {#data-warehouse-schema}

Data Warehouse을 사용하면 원하는 만큼 추적하고, 원하는 위치에 속성 데이터를 보고하고, 다른 데이터 세트에 연결할 수 있습니다.

>[!IMPORTANT]
>
>* _DELETED_DATE 값이 있는 행은 7일 동안 유지된 다음 Snowflake에서 제거됩니다.
>* Snowflake에 사용된 시간대는 UTC(협정 세계시)를 따릅니다.

>[!NOTE]
>
>이 문서의 맨 아래에 있는 샘플 쿼리를 보려면 [여기를 클릭](#sample-queries)하십시오.

## 엔티티 관계 다이어그램 {#entity-relationship-diagrams}

_Data Warehouse 데이터 모델_ ERD는 데이터 웨어하우스의 데이터가 어떻게 흐르며 서로 연결되는지를 보여 줍니다. 일부 테이블은 매핑 테이블, 이미 존재하는 다른 테이블의 뷰 또는 더 이상 사용하지 않는 테이블을 나타내므로 이 다이어그램에는 Data Warehouse에서 사용할 수 있는 모든 테이블이 포함되지 않습니다. 아래 데이터 웨어하우스에 있는 표 및 열에 대한 자세한 설명을 참조하십시오. 이러한 테이블 중 대다수는 비정규화된 필드를 포함하지만, 이 다이어그램은 대신 차원 테이블의 데이터를 활용하는 권장 데이터 모델입니다.

추가 _광고 차원 데이터 모델_ ERD는 광고 특정 차원의 테이블을 기본 데이터 모델의 테이블에 가장 잘 연결할 수 있는 방법을 보여 줍니다. 광고 차원도 다른 표에서 비정규화되지만, 이는 이러한 차원을 결합하는 데 권장되는 모델을 나타냅니다.

_전체 크기 버전에 대한 이미지를 클릭하십시오_

<table style="table-layout:auto">
 <tbody> 
  <tr> 
   <th>Data Warehouse 데이터 모델</th>
   <th>광고 차원 데이터 모델</th>
  </tr> 
  <tr> 
   <td><a href="assets/data-warehouse-data-model.pdf"><img src="assets/data-warehouse-data-model-thumb.png"></a></td>
   <td><a href="assets/ads-dimensional-data-model.pdf"><img src="assets/ads-dimensional-data-model-thumb.png"></a></td> 
  </tr> 
 </tbody> 
</table>

## 보기 횟수 {#views}

### BIZ_ACCOUNT {#biz-accounts}

소스 시스템에서 가져온 계정.

<table>
  <tbody>
    <tr>
      <th><strong>열</strong></th>
      <th><strong>데이터 유형</strong></th>
      <th><strong>설명</strong></th>
      <th><strong>샘플 데이터</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>소스 시스템의 계정 ID입니다.</td>
      <td>0013100001kpAXaam</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 계정이 생성된 날짜입니다.</td>
      <td>2016-08-28 00:32:55.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 계정의 마지막 수정 날짜입니다.</td>
      <td>2018년 8월 1일 17일:38:30년 0월 0일</td>
    </tr>
    <tr>
      <td>이름</td>
      <td>varchar</td>
      <td>소스 시스템의 계정 이름.</td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>WEB_SITE</td>
      <td>varchar</td>
      <td>소스 시스템에 기록된 계정 웹 사이트로, 잠재 고객-계정 매핑에 사용됩니다.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>참여 등급</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 기계 학습 모델에서 생성된 문자 등급(A, B, C, D, N/A)입니다. ABM이 비활성화된 경우 null입니다.</td>
      <td>B</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_SCORE</td>
      <td>번호(38,19)</td>
      <td>예측 참여 점수(Engagement_Rating)를 생성하기 위해 [!DNL Marketo Measure] 머신 러닝에서 계산한 숫자 점수입니다. ABM이 비활성화된 경우 null입니다.</td>
      <td>0.1417350147058800000</td>
    </tr>
    <tr>
      <td>도메인</td>
      <td>varchar</td>
      <td>웹 사이트의 구문 분석된 버전으로 도메인만 저장됩니다.</td>
      <td>adobe</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>소스 시스템에서 레코드가 삭제되는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Account_Type__c": "Security", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>∗</b> 업계</td>
      <td>varchar</td>
      <td>계정의 기본 비즈니스.</td>
      <td>소매, 통신</td>
    </tr>
    <tr>
      <td><b>∗</b> 국가</td>
      <td>varchar</td>
      <td>계정 주소의 국가 부분입니다.</td>
      <td>미국, 캐나다</td>
    </tr>
  </tbody>
</table>
<p>
<b>∗</b> <i>Marketo Measure Ultimate에서만 사용 가능</i>
<p>

### BIZ_ACCOUNT_TO_EMAILS {#biz-account-to-emails}

알려진 리드/연락처 이메일 주소와 계정 간의 매핑 테이블. ABM이 비활성화된 경우 이 테이블은 비어 있습니다.

<table>
  <tbody>
    <tr>
    <th><strong>열</strong></th>
      <th><strong>데이터 유형</strong></th>
      <th><strong>설명</strong></th>
      <th><strong>샘플 데이터</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>레코드에 대한 고유 ID.</td>
      <td>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13.000</td>
    </tr>
    <tr>
      <td>ACCOUNT_ID</td>
      <td>varchar</td>
      <td>Source 시스템 계정 ID.</td>
      <td>0013100001phrBAAY</td>
    </tr>
    <tr>
      <td>이메일</td>
      <td>varchar</td>
      <td>연락처 관계 또는 잠재 고객 대 계정 매핑을 통해 계정에 매핑된 이메일 주소.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 계정의 마지막 수정 날짜입니다.</td>
      <td>2018년 8월 31일 23일:53:39년 0월</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 계정이 생성된 날짜입니다.</td>
      <td>2018-08-18 22:01:32.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>레코드가 삭제된 것으로 간주되는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ACTIVITIES {#biz-activities}

소스 시스템 또는 연결된 광고 계정에서 가져온 활동.

<table>
  <tbody>
  <tr>
    <th><strong>열</strong></th>
    <th><strong>데이터 유형</strong></th>
    <th><strong>설명</strong></th>
    <th><strong>샘플 데이터</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>소스 시스템의 활동 ID입니다.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>리드 ID</td>
      <td>varchar</td>
      <td>활동과 연관된 잠재 고객의 ID입니다.</td>
      <td>15530482</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>활동과 연관된 연락처의 ID입니다.
      </td>
      <td>13792552</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_ID</td>
      <td>varchar</td>
      <td>소스 시스템의 활동 유형에 대한 ID.</td>
      <td>104</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_이름</td>
      <td>varchar</td>
      <td>소스 시스템의 활동 이름.</td>
      <td>
        <p>진행 상태 변경</p>
      </td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템의 활동 시작 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestapm_ntz</td>
      <td>소스 시스템의 활동 종료 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>캠페인 ID</td>
      <td>varchar</td>
      <td>활동이 속해 있는 캠페인의 소스 시스템 ID입니다.</td>
      <td>
        <p>li.508038570.147643566</p>
      </td>
    </tr>
    <tr>
      <td>SOURCE 시스템</td>
      <td>varchar</td>
      <td>소스 시스템 유형을 식별합니다.</td>
      <td>Marketo</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 행이 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 행이 마지막으로 수정된 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>AD_FORM_ID</td>
      <td>varchar</td>
      <td>소스 시스템에서 활동이 속해 있는 광고 양식의 ID입니다.</td>
      <td>li.507063119.3757704</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADS {#biz-ads}

연결된 광고 계정에서 가져온 광고.

<table>
  <tbody>
    <tr>
      <th><strong>열</strong></th>
      <th><strong>데이터 유형</strong></th>
      <th><strong>설명</strong></th>
      <th><strong>샘플 데이터</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>광고에 대한 고유 ID.</td>
      <td>fb.106851586409075.6052044288804.6052044290004.6053457066804</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>소스 시스템의 광고 ID.</td>
      <td>6053457066804</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고를 가져올 광고 계정의 ID입니다.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>광고를 가져온 광고 계정의 이름입니다.</td>
      <td>[!DNL Marketo Measure] 계정</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고, 특히 Doubleclick에 대한 광고주 ID.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>광고용 광고주 이름, 특히 Doubleclick의 경우.</td>
      <td>Marketing Analytics</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고에 대한 광고 그룹 ID.</td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>AD_GROUP_이름</td>
      <td>varchar</td>
      <td>광고에 대한 광고 그룹 이름.</td>
      <td>광고 B에 대한 광고 세트</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고 캠페인 ID.</td>
      <td>fb.106851586409075.6052044288804</td>
    </tr>
    <tr>
      <td>AD_캠페인_NAME</td>
      <td>varchar</td>
      <td>광고 캠페인의 이름입니다.</td>
      <td>리드 생성 캠페인</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>부울</td>
      <td>소스 시스템에서 광고가 여전히 활성 상태인지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>소스 시스템에서 광고가 삭제되었는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드를 마지막으로 수정한 날짜입니다.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORT</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드를 처음 가져온 날짜.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>이름</td>
      <td>varchar</td>
      <td>소스 시스템의 광고 이름입니다.</td>
      <td>년</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>부울</td>
      <td>[!DNL Marketo Measure] 태그 지정에 대해 광고를 업데이트해야 하는지 여부입니다.
      <p>(내부 처리에 사용되는 진단 필드)
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>그룹화 키</td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "광고"입니다.</td>
      <td>광고</td>
    </tr>
    <tr>
      <td>PROVIDER_유형</td>
      <td>varchar</td>
      <td>광고에 대한 광고 공급자의 이름입니다.</td>
      <td>Facebook</td>
    </tr>
    <tr>
      <td>URL_CURRENT</td>
      <td>varchar</td>
      <td>랜딩 페이지의 URL입니다.
        <p>(진단 필드, 내부 처리용)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_OLD</td>
      <td>varchar</td>
      <td>URL_CURRENT의 이전 값.
      <p>(진단 필드, 내부 처리용)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 매개 변수로 데코레이트할 URL입니다.
      <p>(진단 필드, 내부 처리용)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL 대체 항목</td>
      <td>varchar</td>
      <td>소스 시스템에서 가져옵니다.
      <p>(진단 필드, 내부 처리용)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADVERTISERS {#biz-advertisers}

연결된 광고 계정에서 가져온 광고주

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>광고주에 대한 고유 Id입니다.</td>
      <td>dc.6114.9143143</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>소스 시스템의 광고주 ID.</td>
      <td>9143143</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고를 가져올 광고 계정의 ID입니다.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>광고를 가져온 광고 계정의 이름입니다.</td>
      <td>[!DNL Marketo Measure] 계정</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Doubleclick에 특히 대한 광고주 ID.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>광고주 이름, 특히 Doubleclick에 사용됩니다.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고 계층 구조에서 광고주 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_GROUP_이름</td>
      <td>varchar</td>
      <td>광고 계층 구조에서 광고주 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고 계층 구조에서 광고주 위에 광고 캠페인이 없으므로 Null이 되어야 합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_캠페인_NAME</td>
      <td>varchar</td>
      <td>광고 계층 구조에서 광고 광고주 위에 캠페인이 없으므로 Null이 되어야 합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>부울</td>
      <td>광고주가 소스 시스템에서 여전히 활성 상태인지 여부입니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>소스 시스템에서 광고주가 삭제되었는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드를 마지막으로 수정한 날짜입니다.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORT</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드를 처음 가져온 날짜.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>이름</td>
      <td>varchar</td>
      <td>소스 시스템의 광고주 이름입니다.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>부울</td>
      <td>[!DNL Marketo Measure] 태그 지정에 대해 광고주를 업데이트해야 하는지 여부입니다.
      <p>(내부 처리에 사용되는 진단 필드)
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>그룹화 키</td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "광고주"입니다.</td>
      <td>광고주</td>
    </tr>
    <tr>
      <td>PROVIDER_유형</td>
      <td>varchar</td>
      <td>광고주용 광고 공급자입니다.</td>
      <td>더블클릭</td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_ACCOUNTS {#biz-ad-accounts}

연결된 광고 계정에서 가져온 광고 계정.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>
        <p>광고 계정에 대한 고유 식별자.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 광고 계정 ID.</td>
      <td>
        <p>6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>광고 계층의 광고 계정에 대한 레코드이므로 null이 필요합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>광고 계층의 광고 계정에 대한 레코드이므로 null이 필요합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 광고 계정 위에 광고주가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 광고 계정 위에 광고주가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조의 광고 계정 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조의 광고 계정 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조의 광고 계정 위에 광고 캠페인이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조의 광고 계정 위에 광고 캠페인이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>광고 계정이 소스 시스템에서 여전히 활성 상태인지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 광고 계정이 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-09-06 12:54:37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 광고 계정 이름입니다.</td>
      <td>
        <p>[!DNL Marketo Measure] 광고 계정</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 광고주를 업데이트해야 하는지 여부입니다.</p>
        <p>(내부 처리에 사용되는 진단 필드)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "계정"입니다.</p>
      </td>
      <td>
        <p>계정</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계정에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_CURRENCY_UNIT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템에서 광고 계정에 사용되는 통화 코드.</p>
      </td>
      <td>
        <p>미국 달러</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY_ID</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용됩니다.</td>
      <td>1933789</td>
    </tr>
    <tr>
      <td>
        <p>소스</p>
      </td>
      <td>varchar</td>
      <td>utm_source의 URL에서 구문 분석됩니다.</td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>utm_medium의 URL에서 구문 분석됩니다.</td>
      <td>
        <p>리수07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_COST</p>
      </td>
      <td>
        <p>번호(38,19)</p>
      </td>
      <td>
        <p>지난 30일 동안 가져온 지출 금액으로, AdWords에만 적용됩니다.</p>
      </td>
      <td>
        <p>17260.000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_IMPRESSIONS</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>지난 30일 동안의 노출 횟수로, AdWords에만 적용됩니다.</p>
      </td>
      <td>
        <p>730060</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CLICKS</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>지난 30일 동안의 클릭 횟수로, AdWords에만 적용할 수 있습니다.</p>
      </td>
      <td>
        <p>3400</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CONVERSIONS</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>지난 30일 동안 보고된 전환 횟수로, AdWords에만 적용됩니다.</p>
      </td>
      <td>
        <p>180</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계정 수준에서 AdWords 또는 랜딩 페이지에 태그를 지정하는 Bing에 추적 템플릿이 추가되었습니다.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_CAMPAIGNS {#biz-ad-campaigns}

연결된 광고 계정, 소스 시스템, utm 및 자체 보고에서 가져온 캠페인

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>캠페인에 대한 고유 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 캠페인 ID.</td>
      <td>
        <p>285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인을 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인을 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Campaign, 특히 Doubleclick에 대한 광고주 ID.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인에 대한 광고주 이름, 특히 Doubleclick에 대한 이름입니다.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 캠페인 위에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 캠페인 위에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인에 대한 고유 ID입니다. 대신 ID 필드를 사용하십시오.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인의 이름입니다. 이름 필드를 대신 사용하십시오.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 Campaign이 여전히 활성 상태인지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 Campaign이 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 이름.</p>
      </td>
      <td>
        <p>파트너 재타겟팅</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 캠페인을 업데이트해야 하는지 여부입니다.</p>
        <p>(내부 처리에 사용되는 진단 필드)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "캠페인"입니다.</p>
      </td>
      <td>
        <p>Campaign</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DAILY_예산</p>
      </td>
      <td>
        <p>번호(38,19)</p>
      </td>
      <td>
        <p>캠페인에 대한 광고 플랫폼에서 설정되는 일일 예산.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지에 태그 지정하기 위해 AdWords 또는 Bing용 캠페인 수준에 추가된 추적 템플릿입니다.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_FORMS {#biz-ad-forms}

광고 Forms을 연결된 광고 계정에서 가져왔습니다.

<table>
  <tr>
    <th>
      <p>열</p>
    </th>
    <th>
      <p>데이터 유형</p>
    </th>
    <th>
      <p>설명</p>
    </th>
    <th>
      <p>샘플 데이터</p>
    </th>
  </tr>
  <tbody>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>광고 양식에 대한 고유 ID입니다.</p>
      </td>
      <td>
        <p>li.507063119.3757704</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식을 가져올 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>li.507063119</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식을 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 상태가 삭제되었습니다. 상태가 초안, 보관됨 또는 취소됨인 경우 삭제로 설정합니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식 이름.</p>
      </td>
      <td>
        <p>NSPA 전자책 LGF (2020년 5월)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "AdForm"입니다.</p>
      </td>
      <td>
        <p>AdForm</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>설명</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식에 대한 설명.</p>
      </td>
      <td>
        <p>인텔리전트 자동화를 통해 모기지 리파이낸스 대출 애플리케이션에서 프로세스 효율성을 높이는 방법을 알아봅니다.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>제목</p>
      </td>
      <td>varchar</td>
      <td>광고 양식의 헤드라인.</td>
      <td>
        <p>리파이낸싱 애플리케이션 프로세스 자동화</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 URL</p>
      </td>
      <td>varchar</td>
      <td>광고 양식의 랜딩 URL.</td>
      <td>
        <p>https://adobe.com/blog/refinancing-application-process/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>질문</p>
      </td>
      <td>varchar</td>
      <td>광고 양식에 대한 질문 목록입니다.</td>
      <td>
        <p>이름:성:이메일 주소:국가/지역:직함:회사 이름</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>상태</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 양식 상태.</p>
      </td>
      <td>
        <p>제출됨</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>레코드가 시작된 Source의 ID입니다.</td>
      <td>aw.3284209</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_GROUPS {#biz-ad-groups}

연결된 광고 계정에서 가져온 광고 그룹.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>광고 그룹에 대한 고유 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955.23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 광고 그룹 ID입니다.</td>
      <td>
        <p>23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹을 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹을 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 광고 계층 구조에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 광고 계층 구조에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>계층 구조의 광고 그룹에 대한 레코드이므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>계층 구조의 광고 그룹에 대한 레코드이므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹에 대한 캠페인 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹에 대한 캠페인의 이름입니다.</p>
      </td>
      <td>
        <p>수익 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>광고 계정이 소스 시스템에서 여전히 활성 상태인지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 광고 계정이 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹 이름.</p>
      </td>
      <td>
        <p>수익 속성 - 계정 기반</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 광고주를 업데이트해야 하는지 여부입니다.</p>
        <p>(내부 처리에 사용되는 진단 필드)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "AdGroup".</p>
      </td>
      <td>
        <p>AdGroup</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NETWORK_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 그룹이 실행 중인 매체입니다.</p>
      </td>
      <td>
        <p>검색, 표시, YouTube_Search, YouTube_Watch</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계정 수준에서 AdWords 또는 랜딩 페이지에 태그를 지정하는 Bing에 추적 템플릿이 추가되었습니다.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-5594512713562690000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_PROVIDERS

<p>해당되는 경우 자체 보고된 항목을 포함하여 연결된 광고 계정의 광고 공급자입니다.</p>

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>광고 공급자에 대한 고유 ID.</p>
      </td>
      <td>
        <p>빙</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>빙</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>4783788151269206864</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_TOUCHPOINTS {#biz-attribution-touchpoints}

<p>구매자 속성 접점, 기회와 연관된 모든 접점.</p>
<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Buyer Attribution Touchpoint(BAT)의 고유 ID입니다.</p>
      </td>
      <td>
        <p>BAT2_0060Z00000lFHtOQAW_</p>
        <p>0030Z00003K5bpKQAR_2017-06-20:01-05-20-6193330.0b5c5678807c</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-09-01 04:53:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>영업 기회 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BAT이 귀속되는 영업 기회의 ID입니다.</p>
      </td>
      <td>
        <p>0060Z00000lFHtOQAW</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>BAT과 연결된 연락처의 ID입니다.</p>
      </td>
      <td>
        <p>0030Z00003K5bpKQAR</p>
      </td>
    </tr>
    <tr>
      <td>이메일</td>
      <td>varchar</td>
      <td>BAT과 연계된 이메일 주소.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BAT이 속하는 계정의 ID입니다.</p>
      </td>
      <td>
        <p>0013100001otbIAAAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BAT을 생성한 사용자 터치포인트의 ID입니다.</p>
      </td>
      <td>
        <p>person@adobe.com_00v1B00003ZbWzHQAV</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>터치포인트의 날짜입니다.</p>
      </td>
      <td>
        <p>2017-06-20 01:05:20.000</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>BAT과 연계된 방문자 ID.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>활동 유형, 웹 방문, 웹 양식, 웹 채팅, 전화 통화, [CRM] Campaign 또는 [CRM] 활동. CRM에서 "터치포인트 유형"이라고 합니다.</p>
      </td>
      <td>
        <p>웹 양식</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>채널</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 사용자 지정 채널 정의에 정의된 대로 터치포인트가 속하는 채널입니다. CRM에서는 "마케팅 채널 - 경로"라고 합니다.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 첫 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>ABC</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>범주2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 두 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>예</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>범주3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 세 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>중소기업</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>카테고리 4</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 네 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td>
        <p>새로운 비즈니스</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>범주5</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 다섯 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>범주6</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 여섯 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 7번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 8번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 9번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>범주10</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 10번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리11</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 11번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리12</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 12번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리13</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 13번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리14</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 14번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리15</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 15번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>브라우저 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있던 브라우저가 검색되었습니다.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSERVERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있었던 브라우저의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>플랫폼 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 플랫폼입니다.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_버전</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 플랫폼의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. CRM에서는 "랜딩 페이지"라고 합니다.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover- truth-behind-per-lead</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지 원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. 원시 랜딩 페이지에는 URL의 모든 쿼리 매개 변수가 포함됩니다. CRM에서는 "랜딩 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover-truth -behind-cost-per-lead?utm_content=27322869&amp;utm_ medium=social&amp;utm_source=linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. CRM에서 "레퍼러 페이지"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. 원시 레퍼러 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "레퍼러 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Attribution_Touchpoints 테이블에 표시되지 않고 Form_Submits 테이블에 표시됩니다. CRM에서 "양식 URL"이라고 합니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Attribution_Touchpoints 테이블에 표시되지 않고 Form_Submits 테이블에 표시됩니다. 원시 양식 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "양식 URL - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>양식 제출이 발생한 날짜.</p>
      </td>
      <td>
        <p>2017-06-20 01:06:41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>도시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 도시입니다.</p>
      </td>
      <td>
        <p>샌프란시스코</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>지역</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 영역입니다.</p>
      </td>
      <td>
        <p>캘리포니아</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>국가</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 국가입니다.</p>
      </td>
      <td>
        <p>미국</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 미디어를 정의하는 데 사용됩니다. URL의 utm_medium에서 구문 분석하거나, 또는 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "cpc" 또는 "display"와 같은 값이 될 수 있습니다.</p>
      </td>
      <td>
        <p>소셜</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 소스를 정의하는 데 사용됩니다. 이 값은 utm_source의 URL에서 구문 분석할 수 있으며, CRM에서 동기화된 경우 일반적으로 "CRM Campaign"으로 설정되거나 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "Google AdWords" 또는 "Facebook"와 같은 값일 수 있습니다. CRM에서 "터치포인트 Source"라고 합니다.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자가 검색하기 위해 브라우저에 입력한 후 웹 사이트에서 종료한 값. 키워드 구입에 따라 유료 검색 플랫폼에서 구입한 키워드와 일치하거나 일치하지 않을 수 있습니다.</p>
      </td>
      <td>
        <p>google [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 플랫폼 [!DNL Marketo Measure]은(는) 일반적으로 통합 파트너 중 하나에서 확인할 수 있습니다.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 이름.</p>
      </td>
      <td>
        <p>마케팅 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 ID입니다. 이는 Google Adwords에만 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 이름. 이는 Google AdWords에만 적용됩니다.</p>
      </td>
      <td>
        <p>마케팅 속성 - 일반</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 ID입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>
        <p>dc.6114.8882972.25272734.492579576</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 이름입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>
        <p>예산 웨비나 - 사이드바</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 ID. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.182716179597</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>B2B 마케팅 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 첫 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>CMO 안내서 다운로드</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 두 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>마케팅 활동을 매출에 연결하여 속성이 ROI를 측정하는 방법을 알아봅니다</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에서 클릭스루하는 랜딩 페이지. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에 표시되는 친숙한 URL 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/CMOs-Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 ID입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.4838421670</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다</p>
      </td>
      <td>
        <p>"마케팅 기여도"</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 구문과 구매 키워드 간에 일치하는 항목의 유형입니다.</p>
      </td>
      <td>
        <p>정확</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 첫 번째 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 리드 생성 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 영업 기회 창출 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 닫힘 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGES_TOUCHED</p>
      </td>
      <td>varchar</td>
      <td>이 필드는 더 이상 사용되지 않습니다. 스테이지 정보에 대해서는 Stage_Transitions 테이블을 사용합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 세션 중에 양식 채우기를 했는지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 첫 번째 노출 터치로 처리되는지 여부</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>첫 번째 터치이므로 이 터치포인트에 할당된 계산된 백분율입니다(Is_First_Touch 참조).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>잠재 고객 생성 터치이므로 이 접점에 할당된 계산된 백분율입니다(Is_Lead_Creation_Touch 참조).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>U자형 터치의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch 및 Is_Lead_Creation_Touch 참조).</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>W자형 터치의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch, Is_Lead_Creation_Touch 및 Is_Opp_Creation_Touch 참조).</p>
      </td>
      <td>
        <p>0.0153374234214425</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>전체 경로 모델의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch 참조).</p>
      </td>
      <td>
        <p>0.0143061513081193</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>번호(22,19)</td>
      <td>이 접점은 사용자 지정 모델의 일부이므로 이 접점에 할당된 계산된 백분율입니다(Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch 참조).</td>
      <td>0.0143061513081193</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>영업 기회 행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>랜딩 페이지 키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_ROW_KEY</p>
      </td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_AI_TOUCHPOINTS {#biz-attribution-ai-touchpoints}

Attribution AI 통합에서 생성된 데이터입니다. 이러한 필드는 Marketo Measure Ultimate 고객에게만 채워집니다.

<table>
<thead>
  <tr>
    <th>열</th>
    <th>데이터 유형</th>
    <th>설명</th>
    <th>샘플 데이터</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CONVERSION_DATE</td>
    <td>Timestamp_ntz</td>
    <td>전환 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>전환 이름</td>
    <td>varchar</td>
    <td>전환 이벤트의 이름(UI 설정에서 고객이 지정한 대로)</td>
    <td> </td>
  </tr>
  <tr>
    <td>CONVERSION_ID</td>
    <td>varchar</td>
    <td>전환 이벤트의 id(소스 데이터 세트의 이벤트 데이터 레코드와 함께 전송된 원래 고유 id 값)</td>
    <td>0013100001b44aGAAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_ID</td>
    <td>varchar</td>
    <td>전환 이벤트에 대한 원래 MM 이벤트 ID 
    <br>사용자 터치포인트 또는 단계 전환에 매핑</td>
    <td>00U0Z00000pCZmyUAG</td>
  </tr>
  <tr>
    <td>CONVERSION_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>전환 이벤트에 대한 원래 MM 계정 ID</td>
    <td>0013100001kpAXaam</td>
  </tr>
  <tr>
    <td>CONVERSION_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>전환 이벤트에 대한 원래 MM 영업 기회 ID</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>CONVERSION_LEAD_ID</td>
    <td>varchar</td>
    <td>전환 이벤트 <br>의 원래 MM 리드 ID는 대부분 null일 수 있습니다.</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_CONTACT_ID</td>
    <td>varchar</td>
    <td>전환 이벤트에 대한 원래 MM 연락처 ID
    <br>대부분의 경우 null일 수 있음</td>
    <td>00331000032MxRAAU</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_TYPE</td>
    <td>varchar</td>
    <td>전환 이벤트 유형(b2b = 가망 고객 전환, b2c = 기회 전환)</td>
    <td>b2b</td>
  </tr>
  <tr>
    <td>SCORE_DATE</td>
    <td>Timestamp_ntz</td>
    <td>터치포인트가 마지막으로 채점된 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>IMPACTED_PERCENT</td>
    <td>번호(38,35)</td>
    <td>각 접점이 담당하는 전환의 비율입니다.</td>
    <td>0.10</td>
  </tr>
  <tr>
    <td>INCREMENT_PERCENT</td>
    <td>번호(38,35)</td>
    <td>접점에 의해 직접 발생한 한계 영향의 양</td>
    <td>0.25</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_DATE</td>
    <td>Timestamp_ntz</td>
    <td>접점 또는 단계 전환 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_EVENT_ID</td>
    <td>varchar</td>
    <td>터치포인트를 생성한 이벤트의 id</td>
    <td>00U3100000VLUnEEAX</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>터치포인트에 연결된 영업 기회의 id</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>터치포인트에 연결된 계정의 id</td>
    <td>0013100001kpAXaam</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_LEAD_ID</td>
    <td>varchar</td>
    <td>터치포인트에 연결된 잠재 고객의 id</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_CONTACT_ID</td>
    <td>varchar</td>
    <td>터치포인트와 연계된 연락처 id</td>
    <td>00331000032MxRAAU</td>
  </tr>
  <tr>
    <td>COUNT_TO_CONVERSION</td>
    <td>번호(38,0)</td>
    <td>전환 이벤트로 이어지는 체인에서 터치포인트의 등급 또는 서수 값</td>
    <td>10000</td>
  </tr>
  <tr>
    <td>AAI_SOURCE_ID</td>
    <td>varchar</td>
    <td>기여도 ai 소스 테이블의 외래 키</td>
    <td> </td>
  </tr>
  <tr>
    <td>_CREATED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Snowflake에서 레코드가 생성된 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>_MODIFIED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>레코드가 Snowflake에서 마지막으로 수정된 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>_DELETED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Snowflake에서 레코드가 삭제된 날짜</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
</tbody>
</table>

### BIZ_CAMPAIGN_MEMBERS {#biz-campaign-members}

소스 시스템에서 가져온 캠페인 멤버. Campaign 동기화가 비활성화되면 이 테이블은 비어 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>소스 시스템의 캠페인 멤버 ID.</td>
      <td>00v0Z00001VZDlqat</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 캠페인 멤버의 마지막 수정 날짜.</p>
      </td>
      <td>
        <p>2018-08-31 20:49:54.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 캠페인 멤버의 생성 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-31 20:49:54.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_TOUCH_POINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>고객이 캠페인 날짜를 대체하도록 설정한 날짜 및 시간이며 대신 접점 날짜에 대해 이 값을 사용합니다.</p>
      </td>
      <td>
        <p>2018-08-30 18:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버가 연결된 잠재 고객의 ID입니다.</p>
      </td>
      <td>
        <p>00Q0Z000013dw4GUAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버가 연결된 잠재 고객 이메일입니다.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버와 연결된 연락처의 ID입니다.</p>
      </td>
      <td>
        <p>00331000032MxRAAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버 연락처의 이메일이 연결되어 있습니다.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>상태</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버의 상태(일반적으로 [전송됨] 또는 [응답됨] 또는 다른 사용자 정의 값으로 설정됨)입니다. 이 상태는 Campaign_Sync_Type에 연결되어 터치포인트를 만들 캠페인 구성원을 결정합니다.</p>
      </td>
      <td>
        <p>보냄</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_RESPONDED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>캠페인 멤버가 상태 선택기에서 "응답됨"으로 표시되었는지 여부를 알려줍니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_RESPONDED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>캠페인 멤버가 처음 응답한 날짜.</p>
      </td>
      <td>
        <p>2018-08-30 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버가 속한 관련 캠페인의 이름입니다.</p>
      </td>
      <td>
        <p>빠른 CMO 인터뷰</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버가 속한 관련 캠페인의 ID입니다.</p>
      </td>
      <td>
        <p>7010Z000001TcKlQAK</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>캠페인 멤버가 속한 관련 캠페인에 대해 선택된 유형. 유형은 마케팅 채널을 매핑하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>오프라인</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_SYNC_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 만들 캠페인 구성원을 결정합니다. 가능한 값은 Include_All, Include_Responded, Exclude_All입니다.</p>
      </td>
      <td>
        <p>Include_All</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>감사 필드: 잠재 고객에 대해 Buyer Touchpoint이 생성되었는지 여부를 나타냅니다. 터치포인트가 만들어지지 않으면 예선 탈락의 이유를 적시한다.</p>
      </td>
      <td>
        <p>접점 없음: 모델 외부 날짜</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>감사 필드는 연락처에 대해 Buyer Touchpoint이 생성되었는지 여부를 나타냅니다. 터치포인트가 만들어지지 않으면 예선 탈락의 이유를 적시한다.</p>
      </td>
      <td>
        <p>터치포인트 생성됨</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>감사 필드에는 Opportunity에 대해 Buyer Attribution Touchpoint이 생성되었는지 여부가 표시됩니다. 터치포인트가 만들어지지 않으면 예선 탈락의 이유를 적시한다.</p>
      </td>
      <td>
        <p>터치포인트 생성됨</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Campaign_Type__c":"Dinners","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CHANNEL {#biz-channels}

[!DNL Marketo Measure] 응용 프로그램에서 만든 마케팅 채널입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>채널에 대한 고유 ID입니다.</p>
      </td>
      <td>
        <p>유기 검색.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>채널 이름.</p>
      </td>
      <td>
        <p>유기 검색.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>snowflake에서 레코드가 생성된 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드를 마지막으로 수정한 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드가 Snowflake에서 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CONTACT {#biz-contacts}

소스 시스템에서 가져온 연락처.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 연락처 ID.</p>
      </td>
      <td>
        <p>0030Z00003OzioeQAB</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 연락처 레코드를 마지막으로 수정한 날짜.</p>
      </td>
      <td>
        <p>2018-09-05 05:17:53.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 연락처 레코드를 만든 날짜.</p>
      </td>
      <td>
        <p>2018-09-05 05:17:51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 연락처에 대한 이메일 주소.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>연락처와 관련된 계정의 ID입니다.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>잠재 고객이 생성된 Source.</p>
      </td>
      <td>
        <p>광고</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에서 만들 수 있는 사용자 지정 단계로 인식되는 연락처의 현재 단계입니다.</p>
      </td>
      <td>
        <p>데모 예약됨</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>연락처의 이전 모든 단계는 [!DNL Marketo Measure] 응용 프로그램에서 만들 수 있는 사용자 지정 단계로 인식됩니다.</p>
      </td>
      <td>
        <p>열기 - 연락처</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>번호(38,19)</p>
      </td>
      <td>
        <p>이 기능은 더 이상 사용되지 않습니다. 이 열은 사용하지 마십시오.</p>
      </td>
      <td>
        <p>N/A</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>오프라인 이벤트를 웹 세션에 매핑하기 위해 통합 파트너에서 채우는 데 사용되는 [!DNL Marketo Measure] 쿠키 ID입니다. 요구 사항: 호출 추적 활성화: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 레코드가 삭제되는지 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>부울</td>
      <td>CRM 및 Marketo 통합이 모두 설정된 경우 레코드 중복을 제거하는 데 사용됩니다. 중복 항목이 있는 경우 Marketo 연락처는 true로 표시됩니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>SOURCE 시스템</td>
      <td>varchar</td>
      <td>레코드가 CRM에서 가져왔는지 Marketo 통합에서 가져왔는지 여부를 나타냅니다.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Marketo 통합의 사용자를 CRM 통합의 연락처와 매핑합니다. CRM과 Marketo 통합이 모두 있는 경우 값은 해당 ID입니다.</td>
      <td>1234 / 00Q0Z00001OohgTUAR</td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>∗</b> 작업 제목</td>
      <td>varchar</td>
      <td>연락처의 직책.</td>
      <td>CEO, 부사장</td>
    </tr>
  </tbody>
</table>
<p>
<b>∗</b> <i>Marketo Measure Ultimate에서만 사용 가능</i>
<p>

### BIZ_CONVERSION_RATES {#biz-conversion-rates}

소스 시스템에서 가져온 통화 전환율.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>번호(38,0)</td>
      <td>레코드에 대한 고유 ID.</td>
      <td>-5942345438803054604</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>번호(38,0)</td>
      <td>통화에 대한 ID 값입니다.</td>
      <td>7493833133899044458</td>
    </tr>
    <tr>
      <td>SOURCE_ISO_CODE</td>
      <td>varchar</td>
      <td>소스 시스템의 통화 ISO 코드.</td>
      <td>미국 달러</td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>전환율 시작일.</td>
      <td>2018-11-01 00:00:00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestamp_ntz</td>
      <td>전환율의 다음 시작 일자. (변환율의 종료 일자는 end_date에서 1일을 뺀 것입니다.)</td>
      <td>2018-09-01 00:00:00.000</td>
    </tr>
    <tr>
      <td>CONVERSION_RATE</td>
      <td>번호(38,0)</td>
      <td>통화를 회사 통화로 변환하는 데 사용되는 비율입니다.</td>
      <td>0.76728300</td>
    </tr>
    <tr>
      <td>IS_CURRENT</td>
      <td>부울</td>
      <td>이 필드의 의미 체계가 손상되었습니다. 사용하지 마십시오.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드가 생성된 날짜.</td>
      <td>2019-03-30 00:54:50.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2019-03-30 00:54:50.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_COST {#biz-costs}

연결된 광고 계정 또는 자체 보고된 마케팅 지출에서 가져온 비용 데이터입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>비용 레코드에 대한 고유 ID.</td>
      <td>aw.6601259029.285114995.21703163075.[AdWords Display]_2018-09-06</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드를 마지막으로 수정한 날짜입니다.</td>
      <td>2018-09-06 12:22:45.000</td>
    </tr>
    <tr>
      <td>COST_DATE</td>
      <td>timestamp_ntz</td>
      <td>비용이 발생한(또는 귀속된) 날짜.</td>
      <td>2018-09-06 00:00:00.000</td>
    </tr>
    <tr>
      <td>소스</td>
      <td>varchar</td>
      <td>보고된 비용의 Source.</td>
      <td>[AdWords 표시]</td>
    </tr>
    <tr>
      <td>COST_IN_MICRO</td>
      <td>번호(38,0)</td>
      <td>비용(백만 단위)입니다. 사용자는 값을 1000000으로 나누어야 합니다.</td>
      <td>1410000</td>
    </tr>
    <tr>
      <td>클릭수</td>
      <td>번호(38,0)</td>
      <td>그날 그룹에 대해 보고된 클릭 수입니다.</td>
      <td>4</td>
    </tr>
    <tr>
      <td>노출 횟수</td>
      <td>번호(38,0)</td>
      <td>그날 그룹에 대해 보고된 노출 횟수입니다.</td>
      <td>4187</td>
    </tr>
    <tr>
      <td>ESTIMATED_TOTAL_POSSIBLE_IMPRESSIONS</td>
      <td>번호(38,0)</td>
      <td>해당 일 그룹의 DCM에서 추정한 총 노출 횟수입니다.</td>
      <td>5024</td>
    </tr>
    <tr>
      <td>AD_PROVIDER</td>
      <td>varchar</td>
      <td>비용이 발생한 공급자.</td>
      <td>Google</td>
    </tr>
    <tr>
      <td>CHANNEL_고유_ID</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 만든 마케팅 채널의 ID.</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>채널 이름</td>
      <td>varchar</td>
      <td>고객이 [!DNL Marketo Measure] 앱에서 만든 마케팅 채널의 이름입니다.</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_IS_AGGREGATABLE_COST</td>
      <td>부울</td>
      <td>행에 채널로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 채널 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>광고 연결에서 가져온 Advertiser의 ID, 특히 Doubleclick 연결에 대한 ID.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>광고 연결에서 가져온 광고주의 이름, 특히 Doubleclick 연결에 대해 가져온 것입니다.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>ADVERTISER_IS_AGGREGATABLE_COST</td>
      <td>부울</td>
      <td>행에 광고주가 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (즉, 광고주 비용을 가져오려면 이 열이 true인 행의 합계를 구합니다.)</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 계정별로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 계정 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 캠페인 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 캠페인의 이름입니다.</p>
      </td>
      <td>
        <p>파트너 재타겟팅</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Campaign으로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 캠페인 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고 그룹의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.21703163075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고 그룹의 이름입니다.</p>
      </td>
      <td>
        <p>속성 관리 소프트웨어 | 구문</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 광고 그룹으로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 광고 그룹 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고 ID.</p>
      </td>
      <td>
        <p>dc.6114.9131003.24149929.467969200</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 광고의 이름입니다.</p>
      </td>
      <td>
        <p>광고 이름: Ad3-320x50.gif; 320 x 50</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Ad로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (즉, 광고 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 크리에이티브 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.51749608028.266050115160</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 크리에이티브의 이름입니다.</p>
      </td>
      <td>
        <p>Gartner Magic Quadrant 2019</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Creative로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (즉, 크리에이티브 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 키워드의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029.669328935.39419128772.99608705795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 키워드의 이름입니다.</p>
      </td>
      <td>
        <p>sfdc 마케팅 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Keyword로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (예: 키워드 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 배치 ID입니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 배치 이름입니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 배치로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 배치 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 사이트의 ID.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 연결에서 가져온 사이트의 이름입니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Site 로 합산될 수 있는 Cost 가 포함되어 있는지 여부를 나타냅니다. (예: 사이트 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>ISO_CURRENCY_CODE</td>
      <td>varchar</td>
      <td>소스 시스템에서 가져온 통화의 ISO 코드.</td>
      <td>미국 달러</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>레코드가 시작된 Source의 ID입니다.</td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ROW_KEY</p>
      </td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>번호(38,0)</td>
      <td>레코드에 대한 통화의 ID 값.</td>
      <td>
        <p>-3253183181619994799</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CREATIVE {#biz-creatives}

연결된 광고 계정에서 가져온 크리에이티브.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Creative의 고유 ID입니다.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 크리에이티브 ID.</td>
      <td>
        <p>10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브를 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브를 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브, 특히 Doubleclick에 대한 광고주 ID.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브 광고주 이름, 특히 Doubleclick의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브용 광고 그룹 ID.</p>
      </td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브용 광고 그룹의 이름입니다.</p>
      </td>
      <td>광고 B에 대한 광고 세트</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 캠페인 ID.</p>
      </td>
      <td>
        <p>ba.3284209.132855866</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브 캠페인 이름.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>크리에이티브가 소스 시스템에서 여전히 활성 상태인지 여부입니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 크리에이티브가 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 크리에이티브 이름입니다.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 Creative를 업데이트해야 하는지 여부입니다.</p>
        <p>(내부 처리에 사용되는 진단 필드)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>진단 필드(내부 처리용).</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "Creative"입니다.</p>
      </td>
      <td>
        <p>Creative</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>BingAd</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>모든 태그를 포함하는 URL의 현재 버전입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td>
        <p>cdn.adobe.com/redir?lp=http%3a%2f%2fwww.pipelinemarketing.com%2f&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}&amp;utm_content={adid}&amp;utm_term={keyword}&amp;utm_campaign=PipelineMarketing.com&amp;utm_source=bing&amp;utm_medium=cpc</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_DISPLAY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Creative에 표시되는 짧고 친숙한 URL입니다.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL_CURRENT의 이전 값.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 매개 변수로 데코레이트할 URL입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_SHORTENED</p>
      </td>
      <td>varchar</td>
      <td>Creative에 표시되는 짧고 친숙한 URL입니다. (LinkedIn 광고에만 사용됩니다.)</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ 유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>텍스트 또는 디스플레이일 수 있는 크리에이티브 유형</p>
      </td>
      <td>
        <p>텍스트</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>크리에이티브가 업그레이드된 URL을 사용하는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>제목</p>
      </td>
      <td>varchar</td>
      <td>
        <p>크리에이티브의 상위 라인(헤드라인)</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>창작 첫 줄의 카피</p>
      </td>
      <td>
        <p>수익 중심의 B2B 마케터로부터 연결 및 학습. 커뮤니티에 가입하십시오.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>문안의 두 번째 줄의 사본</p>
      </td>
      <td>
        <p>Analytics를 사용했습니까? 오늘 리뷰를 남겨 주십시오!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>내부 처리용 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>내부 처리용 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>내부 처리용 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>내부 처리용 진단 필드.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SHARE_URN</p>
      </td>
      <td>varchar</td>
      <td>
        <p>공유 ID입니다. (LinkedIn 광고에만 사용됩니다.)</p>
      </td>
      <td>
        <p>urn:li:share:6376987561897848832</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_EVENTS {#biz-crm-events}

소스 시스템에서 가져온 이벤트. 활동 동기화가 비활성화된 경우 이 테이블은 비어 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 이벤트 ID입니다.</p>
      </td>
      <td>
        <p>00U3100000VLUnEEAX</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 이벤트가 생성된 날짜.</p>
      </td>
      <td>
        <p>2016-12-12 19:32:53.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 이벤트가 마지막으로 수정된 날짜입니다.</p>
      </td>
      <td>
        <p>2018-09-03 08:39:51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이벤트와 연계된 잠재 고객 ID.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이벤트와 연계된 잠재 고객에 대한 이메일입니다.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>이벤트와 연계된 연락처 ID.</p>
      </td>
      <td>
        <p>0030Z00003OyjbQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이벤트와 연계된 연락처에 대한 이메일입니다.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>오프라인 이벤트를 웹 세션에 매핑하기 위해 통합 파트너에서 채우는 데 사용되는 [!DNL Marketo Measure] 쿠키 ID입니다. 요구 사항: 호출 추적 활성화: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>활동 유형 이름(소스 시스템)</p>
      </td>
      <td>
        <p>이메일</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_START_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>터치포인트 날짜를 결정하는 데 사용되는 옵션 중 하나인 이벤트의 시작 날짜입니다.</p>
      </td>
      <td>
        <p>2016-12-16 19:30:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_END_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>터치포인트 날짜를 결정하는 데 사용되는 옵션 중 하나인 이벤트의 종료 날짜입니다.</p>
      </td>
      <td>
        <p>2016-12-16 21:30:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</td>
      <td>
        <p>False</p>
      </td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Contact_Type__c":"CMO","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_TASKS {#biz-crm-tasks}

소스 시스템에서 가져온 작업. 활동 동기화 또는 호출 추적이 활성화되면 이 테이블이 채워집니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 작업 ID입니다.</p>
      </td>
      <td>
        <p>00T0Z00004Rf62rUAB</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 작업이 생성된 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-27 18:30:25.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 작업을 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018년 8월 27일 18일:31:53년 0월</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>작업과 연결된 잠재 고객의 ID입니다.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>작업과 연결된 잠재 고객에 대한 이메일입니다.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>작업과 연결된 연락처의 ID.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>작업과 연결된 연락처에 대한 전자 메일입니다.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>오프라인 이벤트를 웹 세션에 매핑하기 위해 통합 파트너에서 채우는 데 사용되는 [!DNL Marketo Measure] 쿠키 ID입니다. 요구 사항: 호출 추적 활성화: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>활동 유형 이름(소스 시스템)</p>
      </td>
      <td>
        <p>호출</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>터치 포인트 날짜를 결정하는 데 사용되는 옵션 중 하나인 작업이 발생한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-27 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>소스 시스템에서 레코드가 삭제된 것으로 간주되는지 여부.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CURRENCIES {#biz-currencies}

모든 ISO 통화 표.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>번호(38,0)</td>
      <td>통화 레코드에 대한 고유 ID.</td>
      <td>139474809945095870</td>
    </tr>
    <tr>
      <td>ISO_CODE</td>
      <td>varchar</td>
      <td>통화에 대한 ISO 코드.</td>
      <td>미국 달러</td>
    </tr>
    <tr>
      <td>IS_CORPORATION</td>
      <td>부울</td>
      <td>통화가 법인 통화인지 여부를 지정합니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>IS_ENABLED</td>
      <td>부울</td>
      <td>소스 시스템에서 통화가 사용되는지 여부를 지정합니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드가 [!DNL Marketo Measure]에서 마지막으로 조정된 날짜입니다.</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드가 생성된 날짜 [!DNL Marketo Measure]</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>소스 시스템에서 레코드가 생성된 날짜.</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>ISO_NUMERIC</td>
      <td>번호(38,0)</td>
      <td>ISO 표준 숫자 코드입니다.</td>
      <td>048</td>
    </tr>
    <tr>
      <td>지수</td>
      <td>번호(38,0)</td>
      <td>정의된 최소 통화 단위와 전체 통화 단위 사이의 소수점 이하 자리 수입니다.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>이름</td>
      <td>varchar</td>
      <td>통화 이름.</td>
      <td>아르헨티나 페소</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_AB_TESTS {#biz-customer-ab-tests}

AB 테스트가 기록되었습니다. AB 테스트가 활성화되지 않은 경우 이 테이블이 비어 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 id의 첫 번째 쿠키 id.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이벤트가 기록될 당시 기록된 쿠키 ID입니다.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>채팅이 기록된 날짜.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드를 마지막으로 수정한 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>IP 주소</td>
      <td>varchar</td>
      <td>
        <p>실험이 기록될 당시 기록된 IP 주소입니다.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>AB 테스트 플랫폼에서 가져온 실험의 ID.</p>
      </td>
      <td>123</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIENCE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>AB 테스트 플랫폼에서 가져온 실험의 이름입니다.</p>
      </td>
      <td>실험 A</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>AB 테스트 플랫폼에서 가져온 실험의 변형 ID입니다.</p>
      </td>
      <td>456</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>AB 테스트 플랫폼에서 가져온 실험의 변형 이름입니다.</p>
      </td>
      <td>파랑 검정</td>
    </tr>
    <tr>
      <td>
        <p>ABTEST_USER_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>AB 테스트 플랫폼에서 가져온 실험을 제공받은 사용자의 ID입니다.</p>
      </td>
      <td>584d64et</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>진단 및 감사에 사용되는 레코드 삭제 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_EVENTS {#biz-customer-events}

Javascript에서 사용자 지정 이벤트를 사용하여 기록된 웹 이벤트입니다. [!DNL Marketo Measure] 이벤트가 활성화되지 않으면 이 테이블이 비어 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 id의 첫 번째 쿠키 id.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 지정 Javascript에서 이벤트가 트리거될 때 기록된 쿠키 ID입니다.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>사용자 지정 Javascript에서 이벤트가 트리거된 날짜입니다.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>레코드가 마지막으로 수정된 날짜입니다.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>
        <p>IP 주소</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 지정 Javascript에서 이벤트가 트리거될 때 기록된 IP 주소입니다.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>키</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 지정 Javascript에서 트리거된 이벤트에 지정된 이름입니다.</p>
      </td>
      <td>비디오 보기</td>
    </tr>
    <tr>
      <td>
        <p>값</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 지정 Javascript에서 트리거된 이벤트에 지정된 값입니다.</p>
      </td>
      <td>75% 조회함</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>진단 및 감사에 사용되는 레코드 삭제 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOM_LANDING_PAGES {#biz-custom-landing-pages}

연결된 광고 계정에서 다운로드한 랜딩 페이지.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>레코드에 대한 고유 ID.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지를 가져온 광고 계정의 ID입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지를 가져온 광고 계정의 이름</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지, 특히 Doubleclick에 대한 광고주 ID.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지(특히 Doubleclick)에 대한 광고주 이름입니다.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지에 대한 광고 그룹 ID입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지에 대한 광고 그룹의 이름입니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지 캠페인 ID.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지에 대한 캠페인의 이름입니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행의 마지막 수정 날짜</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_EMAIL_TO_VISITOR_IDS {#biz-email-to-visitor-ids}

이메일 주소 및 방문자 ID에 대한 매핑 테이블입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>레코드에 대한 고유 ID.</td>
      <td>
        <p>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세션의 지정된 방문자 ID에 연결된 알려진 이메일 주소</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 ID의 첫 번째 쿠키</p>
      </td>
      <td>
        <p>v_36ec805b4db344d6e92c972c86aee34a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행의 마지막 수정 날짜</p>
      </td>
      <td>
        <p>2018년 8월 14일 23일:55:03년 0월</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행의 생성 날짜</p>
      </td>
      <td>
        <p>2018년 8월 14일 23일:55:03년 0월</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>레코드가 삭제된 것으로 간주되는지 여부, 진단 및 감사에 사용됨.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>IS_IGNORE</td>
      <td>부울</td>
      <td>이메일 또는 방문자 ID가 내부 처리에 사용되는 소음이나 스팸으로 간주되는지 보여 줍니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FACTS {#biz-facts}

노출 횟수, 페이지 보기 수, 방문 횟수, 양식 제출, 사용자 접점, 접점(BT), 속성 접점(BAT) 및 비용 데이터를 함께 조합합니다. [!DNL Marketo Measure] 보고를 지원하는 데 내부적으로 사용됩니다.

>[!IMPORTANT]
>
>Marketo Measure은 2024년 중반에 이 표를 더 이상 사용하지 않을 예정입니다. 사용자 측에서 생성하려는 경우 [이 SQL 쿼리](/help/marketo-measure-data-warehouse/assets/BIZ_FACTS.sql)를 실행하십시오.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>COST_키</td>
      <td>번호(38,0)</td>
      <td>비용 테이블에 조인하는 데 사용됩니다.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>ATP_KEY</td>
      <td>번호(38,0)</td>
      <td>속성 터치포인트 테이블에 결합하는 데 사용됩니다.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>TP_키</td>
      <td>번호(38,0)</td>
      <td>터치포인트 또는 사용자 터치포인트 테이블에 결합하는 데 사용됩니다.</td>
      <td>5028390208679093800</td>
    </tr>
    <tr>
      <td>PAGE_VIEW_키</td>
      <td>번호(38,0)</td>
      <td>페이지 보기 횟수 테이블에 조인하는 데 사용됩니다.</td>
      <td>-8044063242541720607</td>
    </tr>
    <tr>
      <td>SESSION_키</td>
      <td>번호(38,0)</td>
      <td>세션 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>관련 방문자 id의 첫 번째 쿠키 id.</td>
      <td>v_530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>COOKIE_</td>
      <td>varchar</td>
      <td>이벤트가 기록될 당시 기록된 쿠키 ID입니다.</td>
      <td>530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>FORM_SUBMIT_KEY</td>
      <td>번호(38,0)</td>
      <td>양식 제출 표에 조인하는 데 사용됩니다.</td>
      <td>-8659572802702769670</td>
    </tr>
    <tr>
      <td>노출 키</td>
      <td>번호(38,0)</td>
      <td>노출 횟수 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CURRENT_페이지_키</td>
      <td>번호(38,0)</td>
      <td>Url 테이블에 조인하는 데 사용됩니다.</td>
      <td>4079876040770132443</td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td>Url 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>FORM_페이지_키</td>
      <td>번호(38,0)</td>
      <td>Url 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>AD_PROVIDER_KEY</td>
      <td>번호(38,0)</td>
      <td>광고 공급자 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>
        <p>채널 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>채널 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>-1921844114032355934</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>광고 캠페인 테이블에 참여하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>252687814634577606</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>키워드 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Keywords 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>광고 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>광고 그룹 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Creative 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>-2333871387956621113</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Sites 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Advertisers 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>광고 계정 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>1825012532740770032</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>배치 테이블에 조인하는 데 사용됩니다.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>CATEGORY_01_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_02_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_03_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_04_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_05_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_06_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_07_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_08_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_09_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_10_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>범주_11_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_12_KEY</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_13_키</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_14_키</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_15_키</td>
      <td>숫자(38,0)</td>
      <td>세그먼트 테이블에 조인하는 데 사용됩니다.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>유형</td>
      <td>번호(38,0)</td>
      <td>행의 팩트 유형을 나타냅니다. 1 = Buyer Attribution Touchpoint 2 = 비용 3 = Buyer Touchpoint 4 = 사용자 접점 5 = 페이지 보기 6 = 세션 7 = 양식 제출 8 = 노출 횟수</td>
      <td>3</td>
    </tr>
    <tr>
      <td>날짜</td>
      <td>날짜</td>
      <td>이벤트 발생 날짜.</td>
      <td>2018년 8월 28일</td>
    </tr>
    <tr>
      <td>타임스탬프</td>
      <td>timestamp_ntz</td>
      <td>이벤트가 발생한 날짜 및 시간입니다.</td>
      <td>2018-08-28 19:39:15.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행이 마지막으로 수정된 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-29 00:46:47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COST_IN_MICRO</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>비용(백만 단위)입니다. 사용자는 값을 1000000으로 나누어야 합니다.</p>
      </td>
      <td>
        <p>27370000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>노출 횟수</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>그날 그룹에 대해 보고된 노출 횟수입니다.</p>
      </td>
      <td>
        <p>340</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>클릭수</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>그날 그룹에 대해 보고된 클릭 수입니다.</p>
      </td>
      <td>4</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>첫 번째 터치이므로 이 터치포인트에 할당된 계산된 비율입니다.</p>
      </td>
      <td>0.0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>리드 만들기 터치이므로 이 접점에 할당된 계산된 비율입니다.</p>
      </td>
      <td>100.0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>U자형 터치의 일부이므로 이 접점에 할당되는 계산된 백분율입니다.</p>
      </td>
      <td>
        <p>100.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>W자형 터치의 일부이므로 이 접점에 할당되는 계산된 백분율입니다.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>전체 경로 모델의 일부이므로 이 터치포인트에 할당되는 계산된 백분율입니다.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>사용자 지정 모델의 일부이므로 이 터치포인트에 할당되는 계산된 백분율입니다.</p>
      </td>
      <td>
        <p>0.0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>금액</p>
      </td>
      <td>
        <p>번호(38,8)</p>
      </td>
      <td>
        <p>소스 시스템의 영업 기회 금액.</p>
      </td>
      <td>
        <p>42000.00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>Opportunity 가 won으로 분류된 단계로 이동되었는지 보여 줍니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CLOSED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>Opportunity 가 Closed 로 분류된 단계로 이동했는지 여부를 나타냅니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>영업 기회 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 영업 기회 ID.</p>
      </td>
      <td>
        <p>0060Z00000nFEfEQAW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 Opportunity 가 생성된 날짜입니다.</p>
      </td>
      <td>
        <p>2018년 8월 31일 15일:45:47년 0월</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 Opportunity 의 Close Date</p>
      </td>
      <td>
        <p>2018-12-31 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 연락처 레코드를 만든 날짜.</p>
      </td>
      <td>2017-04-28 00:21:52.000</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 연락처 ID.</p>
      </td>
      <td>
        <p>0030Z00003ORVJmQAP</p>
      </td>
    </tr>
    <tr>
      <td>이메일</td>
      <td>varchar</td>
      <td>레코드에 대한 이메일 주소.</td>
      <td>personb@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>LEAD_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 리드 레코드가 생성된 날짜.</p>
      </td>
      <td>
        <p>2017-04-28 00:21:52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 잠재 고객 ID.</p>
      </td>
      <td>
        <p>00Q3100001GMPIsEAP</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Ad로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (즉, 광고 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_ADVERTISER</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 광고주가 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (즉, 광고주 비용을 가져오려면 이 열이 true인 행의 합계를 구합니다.)</p>
      </td>
      <td>참</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_ACCOUNT</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 계정별로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 계정 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_GROUP</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 광고 그룹으로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 광고 그룹 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CAMPAIGN</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Campaign으로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 캠페인 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CHANNEL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 채널로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 채널 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CREATIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Creative로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (즉, 크리에이티브 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_KEYWORD</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Keyword로 합산할 수 있는 Cost가 포함되어 있는지 여부를 나타냅니다. (예: 키워드 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_PLACEMENT</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 배치로 합산할 수 있는 비용이 포함되어 있는지 여부를 나타냅니다. (예: 배치 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_SITE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행에 Site 로 합산될 수 있는 Cost 가 포함되어 있는지 여부를 나타냅니다. (예: 사이트 비용을 가져오려면 이 열이 true인 행의 합계를 구하십시오.)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>기록 삭제 여부, 감사 추적으로 사용됨.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>번호(38,0)</td>
      <td>레코드에 대한 통화의 ID 값.</td>
      <td>-3253183181619994799</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FORM_SUBMITTS {#biz-forms-submits}

캡처된 양식 제출.

<table>
  <tbody>
    <tr>
      <th>
        열
      </th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>양식 제출에 대한 고유 ID.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-21-927280.9bc63c34482f4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출이 기록될 때 기록된 쿠키 ID입니다.</p>
      </td>
      <td>
        <p>9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 id의 첫 번째 쿠키 id. 레코드가 is_duplicate = true로 표시되면 이 필드는 null입니다.</p>
      </td>
      <td>
        <p>v_9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출이 기록될 때 기록된 세션 ID입니다. 레코드가 is_duplicate = true로 표시되면 이 필드는 null입니다.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-24-1231230.9bc63c34482f</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>양식 제출 날짜.</p>
      </td>
      <td>
        <p>2018-08-06 01:35:21.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-07 23:09:52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 양식이 제출된 URL.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함하여 양식이 제출된 URL입니다.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzNkhW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP 주소</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출 시 기록된 IP 주소입니다.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>유형</p>
      </td>
      <td>varchar</td>
      <td>이벤트 유형을 나타냅니다.</td>
      <td>
        <p>FormSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_에이전트_문자열</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출 시 기록된 장치 및 브라우저입니다.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh, Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, Gecko) 버전/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>세션에서 페이지 보기가 발생한 순서를 나타냅니다.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>내부 감사 및 처리에 사용됩니다.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>레코드가 중복으로 간주되는지 여부를 나타냅니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>내부 처리에 사용됩니다.</td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript에서 캡처한 양식 이메일 주소.</p>
      </td>
      <td>
        <p>personc@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_TYPE</p>
      </td>
      <td>varchar</td>
      <td>제출된 양식의 유형을 나타냅니다.</td>
      <td>
        <p>채팅</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>onSubmit 또는 AjaxIntercept와 같이 양식을 인식하는 메서드를 나타냅니다.</p>
      </td>
      <td>
        <p>onSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_IDENTIFIER</p>
      </td>
      <td>varchar</td>
      <td>양식에 대한 ID 값입니다.</td>
      <td>
        <p>-956012665</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_페이지_키</td>
      <td>번호(38,0)</td>
      <td>URL 테이블에 대한 외래 키.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_IMPTIONS {#biz-impressions}

실행 및 녹화된 노출 횟수. 이 표에는 DoubleClick 연결 및 True로 설정된 뷰스루 활성화가 필요합니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>노출에 대한 고유 ID.</p>
      </td>
      <td>
        <p>6acd7b43290490fe5c53eed31281d09a|2020-05-18:22:20:59|000|0|2869369052</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>노출 시 기록된 쿠키 ID입니다.</p>
      </td>
      <td>08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 id의 첫 번째 쿠키 id.</p>
      </td>
      <td>v_08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>노출이 기록되었을 때 기록된 세션 ID입니다.</p>
      </td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>노출이 제공된 날짜.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 노출이 제공된 URL입니다.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함하여 노출이 제공된 URL입니다.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzNkhW</td>
    </tr>
    <tr>
      <td>
        <p>IP 주소</p>
      </td>
      <td>varchar</td>
      <td>
        <p>노출 시 기록된 IP 주소.</p>
      </td>
      <td>174.127.184.158</td>
    </tr>
    <tr>
      <td>
        <p>유형</p>
      </td>
      <td>varchar</td>
      <td>이벤트 유형을 나타냅니다.</td>
      <td>노출 횟수</td>
    </tr>
    <tr>
      <td>
        <p>USER_에이전트_문자열</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출 시 기록된 장치 및 브라우저입니다.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh, Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, Gecko) 버전/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>세션에서 페이지 보기가 발생한 순서를 나타냅니다.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>내부 감사 및 처리에 사용됩니다.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>레코드가 중복으로 간주되는지 여부를 나타냅니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>내부 처리에 사용됩니다.</td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. CRM에서 "레퍼러 페이지"라고 합니다.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE-RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. 원시 레퍼러 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "레퍼러 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>도시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 구/군/시.</p>
      </td>
      <td>
        <p>시애틀</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>지역</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 영역입니다.</p>
      </td>
      <td>
        <p>워싱턴</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>국가</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 국가입니다.</p>
      </td>
      <td>
        <p>미국</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ISP 이름</p>
      </td>
      <td>varchar</td>
      <td>필드가 사용되지 않으므로 null이 되어야 합니다.</td>
      <td>NULL</td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 플랫폼 [!DNL Marketo Measure]은(는) 일반적으로 통합 파트너 중 하나에서 확인할 수 있습니다.</p>
      </td>
      <td>Google</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 ID입니다.</p>
      </td>
      <td>aw.6601259029</td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 이름입니다.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>마케팅 분석 시장 측정</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 ID입니다.</p>
      </td>
      <td>aw.6601259029.317738075</td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 이름.</p>
      </td>
      <td>마케팅 속성</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>노출에 대한 Doubleclick 계층에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>노출에 대한 Doubleclick 계층에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 ID입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>
        <p>68035923</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 이름입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>
        <p>centurylink_banner_98121</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 Creative가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 키워드가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 키워드가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 키워드가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>브라우저 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있던 브라우저가 검색되었습니다.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSERVERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있었던 브라우저의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>플랫폼 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 플랫폼입니다.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_버전</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 플랫폼의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>BIZ_FACTS 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_페이지_키</p>
      </td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_KEYWORDS {#biz-keywords}

연결된 광고 계정에서 가져온 키워드입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 고유 ID입니다.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365.39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 키워드 ID.</td>
      <td>
        <p>39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드를 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드를 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 키워드가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doubleclick 노출 계층 구조에 키워드가 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 광고 그룹 ID.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 광고 그룹의 이름입니다.</p>
      </td>
      <td>
        <p>수익 속성 - B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 캠페인 ID.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 캠페인 이름.</p>
      </td>
      <td>
        <p>수익 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 Keyword가 여전히 활성 상태인지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 키워드가 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>
        <p>2018-08-02 06:37:29.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 키워드 이름입니다.</p>
      </td>
      <td>
        <p>[매출 기여도 분석 b2b]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 키워드를 업데이트해야 하는지 여부입니다.</p>
        <p>(진단 필드, 내부 처리에 사용됨)</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "키워드"입니다.</p>
      </td>
      <td>
        <p>키워드</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>키워드에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>
        <p>BingAd</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지의 URL입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL_CURRENT의 이전 값.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 매개 변수가 있는 랜딩 페이지의 URL입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>진단 필드(내부 처리용).</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WORD</p>
      </td>
      <td>varchar</td>
      <td>사용자가 입력한 검색 단계입니다.</td>
      <td>
        <p>수익 속성 b2b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 구문과 키워드 간에 발견된 일치 유형입니다.</p>
      </td>
      <td>
        <p>정확</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>내부 진단에 사용됩니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>URL 추적 템플릿 [!DNL Marketo Measure]이(가) 키워드에 추가되었습니다.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>-2712935512233520000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_랜딩_PAGES {#biz-landing-pages}

연결된 광고 계정에서 가져온 랜딩 페이지.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지에 대한 고유 ID입니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지를 가져온 광고 계정의 ID입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지를 가져온 광고 계정의 이름입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지, 특히 Doubleclick에 대한 광고주 ID.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지(특히 Doubleclick)에 대한 광고주 이름입니다.</p>
      </td>
      <td>Marketing Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지에 대한 광고 그룹 ID입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지에 대한 광고 그룹의 이름입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지 캠페인 ID.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>랜딩 페이지에 대한 캠페인의 이름입니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행의 마지막 수정 날짜입니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEAD {#biz-leads}

출처 시스템에서 임포트된 가망 고객.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 잠재 고객 ID.</p>
      </td>
      <td>
        <p>00Q0Z00001MZcj8UAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 잠재 고객 레코드가 마지막으로 수정된 날짜.</p>
      </td>
      <td>
        <p>2018-08-27 21:52:10.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 리드 레코드가 생성된 날짜.</p>
      </td>
      <td>2018-08-27 21:52:10.000</td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 잠재 고객 이메일 주소.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>WEB_SITE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Lead2Account 매핑에 사용되는 소스 시스템에서 Lead에 대해 입력한 웹 사이트입니다.</p>
      </td>
      <td>
        <p>adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>회사</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Lead2Account 매핑에 사용되는 소스 시스템에서 Lead에 대해 입력한 회사명입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>잠재 고객이 생성된 Source.</p>
      </td>
      <td>
        <p>광고</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CONVERTED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>잠재 고객이 연락처로 전환되었는지 여부입니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>잠재 고객 전환 후 관련 영업 기회의 ID.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>잠재 고객이 연락처로 전환된 날짜.</p>
      </td>
      <td>
        <p>2018-08-27 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>잠재 고객 전환 후 관련 연락처의 ID입니다.</p>
      </td>
      <td>
        <p>0030Z00003Oyp25QAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>매핑된 계정의 ID입니다. 요구 사항: ABM 활성화</p>
      </td>
      <td>
        <p>0010Z0000236F9GQAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에서 만들 수 있는 사용자 지정 단계로 인식되는 잠재 고객의 현재 단계입니다.</p>
      </td>
      <td>
        <p>데모 예약됨</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에서 만들 수 있는 사용자 지정 단계로 인식되는 잠재 고객의 이전 모든 단계입니다.</p>
      </td>
      <td>
        <p>MQL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>번호(38,19)</p>
      </td>
      <td>
        <p>이 기능은 더 이상 사용되지 않습니다. 이 열은 사용하지 마십시오.</p>
      </td>
      <td>
        <p>N/A</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_MODEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(사용하지 않음)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_RESULT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(사용하지 않음)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>오프라인 이벤트를 웹 세션에 매핑하기 위해 통합 파트너에서 채우는 데 사용되는 [!DNL Marketo Measure] 쿠키 ID입니다. 요구 사항: 호출 추적 활성화: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 레코드가 삭제되는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Lead_Type__c":"Sales Created", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>부울</td>
      <td>CRM 및 Marketo 통합이 모두 설정된 경우 레코드 중복을 제거하는 데 사용됩니다. 중복 항목이 있으면 Marketo 잠재 고객이 true로 표시됩니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>SOURCE 시스템</td>
      <td>varchar</td>
      <td>레코드가 CRM에서 가져왔는지 Marketo 통합에서 가져왔는지 여부를 나타냅니다.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Marketo 통합의 개인을 CRM 통합의 리드와 매핑합니다. CRM과 Marketo 통합이 모두 있는 경우 값은 해당 ID입니다.</td>
      <td>1234</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEAD_STAGE_TRANSITIONS {#biz-lead-stage-transitions}

리드 또는 연락처에 대한 단계 전환.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>전환에 대한 고유 ID.</p>
      </td>
      <td>
        <p>ST_0030Z00003FhkRXQAZ__FT-1_TP2_Person_0030Z00003FhkRXQAZ_2018-08-27:17-05-45-9474800.0d5c18c29d7b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 리드/연락처에 대해 제공된 이메일 주소.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환과 연결된 잠재 고객의 ID입니다.</p>
      </td>
      <td>
        <p>00Q3100001Fx6AlEAJ</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>전환과 연계된 연락처 ID.</p>
      </td>
      <td>
        <p>0033100003Aq9grAAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환에 연결된 Buyer Touchpoint의 ID입니다.</p>
      </td>
      <td>
        <p>TP2_Person_00Q3100001Fx6AlEAJ_2018-08-28:14-41-06-1674260.d00ceb09fbd3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드가 단계로 전환된 날짜.</p>
      </td>
      <td>
        <p>2018-08-27 16:05:34.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환 단계의 ID 값입니다.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>단계</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환 단계 이름.</p>
      </td>
      <td>
        <p>FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>순위</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 단계 매핑 설정에서 정렬된 스테이지의 숫자 등급입니다.</p>
      </td>
      <td>
        <p>5</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>색인</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>부메랑 단계의 색인화 및 순서를 지정하기 위한 내부 처리에 사용됩니다.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>부메랑 단계의 색인화 및 순서를 지정하기 위한 내부 처리에 사용됩니다.</td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_보류</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>접점이 보류 중으로 간주되고 아직 닫히지 않았는지 보여 줍니다. 전체 경로 속성 모델이 있는 고객에게만 표시됩니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행이 마일스톤 단계 전환에 연결되어 있는지 여부를 나타냅니다. 예를 들어 3개의 스테이지/시작(FT, LC, MQL)과 4개의 터치포인트가 있는 경우 스테이지가 없는 1 터치포인트는 "비전환"으로 간주되므로 값이 true와 같습니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>단계 순위에 따른 이전 단계의 전환 날짜.</p>
      </td>
      <td>
        <p>2017-11-28 21:26:44.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>단계 순위에 따라 다음 단계에 대한 전환 날짜입니다.</p>
      </td>
      <td>
        <p>2017-12-11 22:39:17.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드의 마지막 수정 날짜.</p>
      </td>
      <td>
        <p>2018-08-28 15:31:10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>전환 레코드가 삭제된 것으로 간주되는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_OPPORTUNITIES {#biz-opportunities}

소스 시스템에서 가져온 영업 기회.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 Opportunity ID 입니다.</p>
      </td>
      <td>
        <p>0060Z00000o89I4QAI</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 Opportunity 의 마지막 수정 날짜.</p>
      </td>
      <td>2017-11-28 21:26:44.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 Opportunity 가 생성된 날짜입니다.</p>
      </td>
      <td>2017-11-28 21:26:44.000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 계정의 ID입니다.</p>
      </td>
      <td>
        <p>001i000000qbyeAAA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 Opportunity 이름</p>
      </td>
      <td>
        <p>Mareketo 측정 갱신</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>영업 기회가 성공한 것으로 간주되는 단계로 이동했는지 보여 줍니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>영업 기회가 종료된 것으로 간주되는 단계로 이동했는지 보여 줍니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 Opportunity 의 예상 또는 실제 종료 일자.</p>
      </td>
      <td>
        <p>2019-08-28 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_CUSTOM_MODEL_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>(사용하지 않음)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>금액</p>
      </td>
      <td>
        <p>번호(38,8)</p>
      </td>
      <td>
        <p>Opportunity, Source System에서 예상되거나 종료된 딜 금액</p>
      </td>
      <td>
        <p>8988.00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>해당 영업 기회로 전환된 관련 잠재 고객의 ID입니다.</p>
        <p>이 필드는 설정되어 있지 않으며 모든 고객에 대해 Snowflake 시 null을 반환합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>해당 Opportunity 로 Convert 된 관련 Lead 의 Email 입니다.</p>
        <p>이 필드는 설정되어 있지 않으며 모든 고객에 대해 Snowflake 시 null을 반환합니다.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>기본 담당자 역할을 사용하는 경우 기본 담당자 역할로 나열된 관련 담당자의 ID입니다.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>기본 담당자 역할을 사용하는 경우 관련 담당자의 이메일이 기본 담당자 역할로 나열됩니다.</p>
      </td>
      <td>
        <p>personb@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>번호(38,19)</p>
      </td>
      <td>
        <p>이 기능은 더 이상 사용되지 않습니다. 이 열은 사용하지 마십시오.</p>
      </td>
      <td>
        <p>N/A</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에 정의된 영업 기회의 현재 단계입니다.</p>
      </td>
      <td>
        <p>DM 데모</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에 정의된 대로 Opportunity가 이전에 거쳤던 모든 단계의 문자열입니다.</p>
      </td>
      <td>
        <p>적격 검색, 데모 예약</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 레코드가 삭제되는지 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ISO_CODE</td>
      <td>varchar</td>
      <td>소스 시스템에서 가져온 통화의 ISO 코드.</td>
      <td>미국 달러</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>번호(38,0)</td>
      <td>레코드에 대한 통화의 ID 값.</td>
      <td>4609512587744160000</td>
    </tr>
    <tr>
      <td>사용자 지정 속성</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 소스 시스템에서 가져온 JSON 형식의 사용자 지정 속성입니다.</td>
      <td>{"Opportunity_Location__c":"Seattle", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>∗</b> 영업 기회 유형</td>
      <td>varchar</td>
      <td>영업 기회 유형(예: 신규 비즈니스, 갱신 등)</td>
      <td>갱신, 잠재 고객</td>
    </tr>
  </tbody>
</table>
<p>
<b>∗</b> <i>Marketo Measure Ultimate에서만 사용 가능</i>
<p>

### BIZ_OPP_STAGE_TRANSITIONS {#biz-opp-stage-transitions}

Opportunity 의 Stage 전환

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>전환에 대한 고유 ID.</p>
      </td>
      <td>
        <p>ST_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_Demo Scheduled-1_BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>영업 기회와 연계된 계정의 ID입니다.</p>
      </td>
      <td>
        <p>0013100001b44nTAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>영업 기회 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환에 연결된 영업 기회의 ID입니다.</p>
      </td>
      <td>
        <p>0060Z00000nEgjlQAC</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>전환과 연계된 연락처 ID.</p>
      </td>
      <td>
        <p>0030Z00003이조즈카르</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 연락처에 대해 제공된 이메일 주소입니다.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환에 연결된 Buyer Attribution Touchpoint의 ID입니다.</p>
      </td>
      <td>
        <p>BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드가 단계로 전환된 날짜.</p>
      </td>
      <td>
        <p>2018-05-26 07:29:43.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>단계</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환 단계 이름.</p>
      </td>
      <td>
        <p>데모 예약됨</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>전환 단계의 ID 값입니다.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>순위</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 단계 매핑 설정에서 정렬된 스테이지의 숫자 등급입니다.</p>
      </td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>색인</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>부메랑 단계의 색인화 및 순서를 지정하기 위한 내부 처리에 사용됩니다.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>부메랑 단계의 색인화 및 순서를 지정하기 위한 내부 처리에 사용됩니다.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>IS_보류</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>접점이 보류 중으로 간주되고 아직 닫히지 않았는지 보여 줍니다. 전체 경로 속성 모델이 있는 고객에게만 표시됩니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>행이 마일스톤 단계 전환에 연결되어 있는지 여부를 나타냅니다. 예를 들어 3개의 스테이지/시작(FT, LC, MQL)과 4개의 터치포인트가 있는 경우 스테이지가 없는 1 터치포인트는 "비전환"으로 간주되므로 값이 true와 같습니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>단계 순위에 따른 이전 단계의 전환 날짜.</p>
      </td>
      <td>
        <p>2015-07-16 17:41:49.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>단계 순위에 따라 다음 단계에 대한 전환 날짜입니다.</p>
      </td>
      <td>
        <p>2018년 8월 27일 19일:40:52년 0월</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드의 마지막 수정 날짜.</p>
      </td>
      <td>
        <p>2018-08-28 03:53:33.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>전환 레코드가 삭제된 것으로 간주되는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PAGE_VIEWS {#biz-page-views}

웹 방문에서 수집된 페이지 보기 수입니다. 여러 페이지 보기 수로 단일 세션을 구성할 수 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>페이지 보기에 대한 고유 ID입니다.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>페이지 보기가 기록될 때 기록된 쿠키 id.</p>
      </td>
      <td>
        <p>277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 ID의 첫 번째 쿠키입니다.</p>
      </td>
      <td>
        <p>v_277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>페이지 보기와 상관 관계가 있는 세션 ID입니다.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>페이지 조회수가 발생한 날짜.</p>
      </td>
      <td>
        <p>2018-08-19 16:49:58.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-19 16:55:37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 페이지 보기의 URL입니다.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함한 페이지 보기의 URL.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo?hsCtaTracking=207219e9-87b6-4105-8f4b-0a3b62ae1af8%7C48060522-3aeb-4c72-8ce5-fd4b1017f069</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP 주소</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출 시 기록된 IP 주소입니다.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>유형</p>
      </td>
      <td>varchar</td>
      <td>이벤트 유형을 나타냅니다.</td>
      <td>
        <p>페이지 보기</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_에이전트_문자열</p>
      </td>
      <td>varchar</td>
      <td>
        <p>양식 제출 시 기록된 장치 및 브라우저입니다.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (X11; Linux x86_64; rv:52.0) Gecko/20100101 Firefox/52.0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>세션에서 페이지 보기가 발생한 순서를 나타냅니다.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>내부 감사 및 처리에 사용됩니다.</td>
      <td>
        <p>103532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>레코드가 중복으로 간주되는지 여부를 나타냅니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>내부 처리에 사용됩니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 페이지 보기가 시작된 URL입니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함하여 페이지 보기가 시작된 URL입니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU%20-%20CMO%20JT&amp;utm_content=CMOs%20Guide&amp;utm_term=lisu05091601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_제목</p>
      </td>
      <td>varchar</td>
      <td>
        <p>페이지 제목</p>
      </td>
      <td>
        <p>B2B 마케팅 속성 다운로드에 대한 CMO의 안내서</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript에서 캡처한 대로 양식에 제공된 이메일 주소.</p>
      </td>
      <td>personc@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_페이지_키</td>
      <td>번호(38,0)</td>
      <td>URL 테이블에 대한 외래 키.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td>URL 테이블에 대한 외래 키.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>HAS_USER_CONSENT</td>
      <td>부울</td>
      <td>사용자가 추적에 동의했는지 보여 줍니다. False는 사용자 동의가 필요하지 않으므로 페이지 보기가 수집되었음을 의미합니다. True는 페이지 보기가 수집되었고 사용자가 추적되는 데 동의했음을 의미합니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PLACEMENTS {#biz-placements}

연결된 광고 계정에서 다운로드한 모든 배치, Doubleclick 통합의 객체를 저장하는 테이블입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>배치에 대한 고유 ID.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 배치 ID입니다.</td>
      <td>10426699711</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치를 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>fb. 106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치를 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치, 특히 Doubleclick에 대한 광고주 ID.</p>
      </td>
      <td>300184624</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치, 특히 Doubleclick에 대한 광고주 이름입니다.</p>
      </td>
      <td>[!DNL Marketo Measure] Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 배치 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에서 배치 위에 광고 그룹이 없으므로 Null이 되어야 합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치에 대한 캠페인 ID.</p>
      </td>
      <td>ba.3284209.132855866</td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치에 대한 캠페인의 이름입니다.</p>
      </td>
      <td>파이프라인 마케팅</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 배치가 여전히 활성 상태인지 여부.</p>
      </td>
      <td>참</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 배치가 삭제되었는지 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>2018-08-02 06:36:25.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>2018-08-02 06:36:25.000</td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 배치 이름입니다.</p>
      </td>
      <td>시장</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 배치를 업데이트해야 하는지 여부입니다.</p>
        <p>(내부 처리에 사용되는 진단 필드)</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>진단 필드(내부 처리용).</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "배치"입니다.</p>
      </td>
      <td>배치</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>배치에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>BingAd</td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake이 레코드를 만든 날짜</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake의 레코드 수정일</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>삭제된 경우 Snowflake의 삭제 날짜 기록</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENTS {#biz-segments}

[!DNL Marketo Measure] 응용 프로그램에 정의된 세그먼트 값입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>세그먼트에 대한 고유 ID.</p>
      </td>
      <td>
        <p>새로운 비즈니스</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세그먼트 이름.</p>
      </td>
      <td>
        <p>새로운 비즈니스</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENT_NAMES {#biz-segment-names}

사용자 지정 세그먼트의 이름을 해당 카테고리 값에 매핑합니다. (터치포인트 테이블에 있는 Category1 - 15 열 헤더에 열 이름을 매핑합니다.)

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>
        <p>범주</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세그먼트 이름이 매핑된 범주를 나타냅니다.</p>
      </td>
      <td>
        <p>CategoryOne</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2022-02-28 18:12:35.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEGMENT_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>범주에 매핑된 세그먼트의 이름입니다.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>부울</td>
      <td>범주가 사용 중인지 여부를 나타냅니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>부울</td>
      <td>레코드가 삭제되는지 여부를 나타냅니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SESSIONS {#biz-sessions}

페이지 보기에서 처리된 세션. 여러 페이지 보기 수가 하나의 세션을 구성할 수 있으며 단일 방문자 ID를 여러 세션에 연결할 수 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>세션의 고유 ID입니다.</p>
      </td>
      <td>
        <p>2016-08-01:14-24-21-9079480.33163948f0a3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>관련 방문자 ID의 첫 번째 쿠키입니다.</p>
      </td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세션의 기록된 쿠키 ID입니다.</p>
      </td>
      <td>277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>세션 날짜.</p>
      </td>
      <td>
        <p>2016년 8월 1일 14일:24:21년 0월 0일</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>수정한 날짜</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-09-01 03:49:10.000</p>
      </td>
    </tr>
    <tr>
      <td>IS_FIRST_SESSION</td>
      <td>부울</td>
      <td>방문자 ID에 대한 첫 번째 세션인지 여부를 나타냅니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>
        <p>채널</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램에 설정된 채널 정의에 정의된 대로 세션에 기여된 채널 특성입니다.</p>
      </td>
      <td>
        <p>유료 Search.AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_제목</p>
      </td>
      <td>varchar</td>
      <td>
        <p>웹 페이지 이름.</p>
      </td>
      <td>
        <p>Salesforce Google Analytics | [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 세션의 첫 번째 페이지 보기 URL.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지 원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함한 세션의 첫 번째 페이지 보기 URL</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics?_bt=83558988035&amp;_bk=google%20analytics%20salesforce&amp;_bm= p&amp;gclid=CMvd5YTLo84CFUI9gQodd-kLEQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수 없이 세션이 시작된 URL.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>쿼리 매개 변수를 포함하여 세션이 시작된 URL.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>레퍼러 페이지의 이름입니다.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자가 검색하기 위해 브라우저에 입력한 후 웹 사이트에서 종료한 값입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] google salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세션을 발생시킨 소스를 정의하는 데 사용됩니다. [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 utm_source의 URL에서 구문 분석하거나 광고 공급자로 설정할 수 있습니다.</p>
      </td>
      <td>
        <p>Google AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_FORM</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>세션에 양식 채우기가 포함되어 있는지 여부,</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CHAT</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>세션에 웹 채팅이 포함되었는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_EMAIL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>세션에 이메일 주소가 있는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CRM_ACTIVITY</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>CRM 활동 레코드에서 세션이 시작되었는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>장치</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세션 중 사용자의 브라우저 및 운영 체제입니다.</p>
      </td>
      <td>
        <p>Chrome(65.0), Windows(6.1)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 플랫폼 [!DNL Marketo Measure]은(는) 일반적으로 통합 파트너 중 하나에서 해결되었습니다.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고주 ID, 특히 Doubleclick 연결에서.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고주 이름, 특히 Doubleclick 연결에서.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 사이트의 ID. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 사이트의 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 배치 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>해결된 광고 배치 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 캠페인 ID.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 캠페인 이름.</p>
      </td>
      <td>
        <p>예산 웨비나 계획</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 확인된 광고 그룹의 ID. 이는 Google Adwords에만 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 그룹의 이름. 이는 Google Adwords에만 적용됩니다.</p>
      </td>
      <td>
        <p>SALESFORCE - GOOGLE ANALYTICS</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>다음에서 확인된 광고 ID. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>aw.6601259029.321586235.23182235435</td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>다음에서 해결된 광고 이름. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>겨울 프로모션 - 녹색</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 ID. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.83558988035</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 크리에이티브의 이름. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>GA 및 Salesforce 통합</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 첫 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>Salesforce 및 Analytics 통합</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 두 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>매출에 최적화합니다. 방법을 알아봅니다.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에서 클릭스루하는 랜딩 페이지. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에 표시되는 친숙한 URL 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>adobe.com/Salesforce-for-GA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 확인된 키워드 ID. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.35934468937</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 키워드 이름. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>google analytics salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 구문과 구매 키워드 간에 일치하는 항목의 유형입니다.</p>
      </td>
      <td>
        <p>구문</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인</p>
      </td>
      <td>varchar</td>
      <td>
        <p>utm_campaign의 URL에서 구문 분석됩니다.</p>
      </td>
      <td>
        <p>SU - ABC 계정 - 유료 미디어 스킬</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>소스</p>
      </td>
      <td>varchar</td>
      <td>
        <p>utm_source의 URL에서 구문 분석됩니다.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>utm_medium의 URL에서 구문 분석됩니다.</p>
      </td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>용어</p>
      </td>
      <td>varchar</td>
      <td>
        <p>utm_term의 URL에서 구문 분석됩니다.</p>
      </td>
      <td>
        <p>리수07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>콘텐츠</p>
      </td>
      <td>varchar</td>
      <td>
        <p>utm_content의 URL에서 구문 분석됩니다.</p>
      </td>
      <td>
        <p>2016 AdWords 벤치마크 보고서</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>도시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 구/군/시.</p>
      </td>
      <td>밴쿠버</td>
    </tr>
    <tr>
      <td>
        <p>지역</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 영역입니다.</p>
      </td>
      <td>브리티시컬럼비아</td>
    </tr>
    <tr>
      <td>
        <p>국가</p>
      </td>
      <td>varchar</td>
      <td>
        <p>IP 주소에서 확인된 국가입니다.</p>
      </td>
      <td>캐나다</td>
    </tr>
    <tr>
      <td>
        <p>ISP 이름</p>
      </td>
      <td>varchar</td>
      <td>필드가 사용되지 않으므로 null이 되어야 합니다.</td>
      <td>
        <p>NULL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP 주소</p>
      </td>
      <td>varchar</td>
      <td>
        <p>세션 시 기록된 IP 주소입니다.</p>
      </td>
      <td>
        <p>174.127.184.158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 세션이 다른 세션과 병합되었으며 삭제해야 하는지 여부를 결정합니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>랜딩 페이지 키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITES {#biz-sites}

연결된 광고 계정에서 가져온 사이트.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 고유 ID.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>소스 시스템의 사이트 ID입니다.</td>
      <td>39464932147</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트를 가져온 광고 계정의 ID입니다.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트를 가져온 광고 계정의 이름입니다.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 광고주, 특히 Doubleclick에 대한 Id.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 광고주 이름, 특히 Doubleclick에 대한 이름입니다.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에 사이트 위에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 계층 구조에 사이트 위에 광고 그룹이 없으므로 Null이 필요합니다.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 캠페인 ID.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 캠페인의 이름입니다.</p>
      </td>
      <td>수익 속성</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 사이트가 여전히 활성 상태인지 여부.</p>
      </td>
      <td>참</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>소스 시스템에서 사이트가 삭제되었는지 여부.</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>소스 시스템에서 레코드를 처음 가져온 날짜.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>소스 시스템의 사이트 이름입니다.</p>
      </td>
      <td>매출</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 태그 지정에 대해 사이트를 업데이트해야 하는지 여부입니다.</p>
        <p>(진단 필드, 내부 처리에 사용됨)</p>
      </td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td>내부 처리에 사용되는 진단 필드.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "사이트"입니다.</p>
      </td>
      <td>위치</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트에 대한 광고 공급자의 이름입니다.</p>
      </td>
      <td>AdWords</td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITE_LINKS {#biz-site-links}

연결된 광고 계정의 사이트 링크.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 고유 ID</p>
      </td>
      <td>
        <p>aw.6601259029.285077795.1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 연결된 광고 계정의 ID</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 연결된 광고 계정의 이름</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크, 특히 Doubleclick에 대한 광고주 ID입니다.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크(특히 Doubleclick)에 대한 광고주 이름입니다.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 광고 그룹 ID</p>
      </td>
      <td>aw.6601259029.208548635.16750166675</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 광고 그룹 이름</p>
      </td>
      <td>브랜드 - 핵심</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 캠페인 ID</p>
      </td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_캠페인_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 캠페인 이름</p>
      </td>
      <td>
        <p>브랜드</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>광고 계정에서 사이트 링크가 여전히 활성화되어 있는지 여부</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>광고 계정에서 사이트 링크가 삭제되었는지 여부</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>행의 마지막 수정 날짜</p>
      </td>
      <td>
        <p>2018년 8월 2일 06일:36:50년 0월 0일</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORT</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>사이트 링크를 처음 다운로드한 날짜 [!DNL Marketo Measure]</p>
      </td>
      <td>
        <p>2018년 8월 2일 06일:36:50년 0월 0일</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크의 이름입니다.</p>
      </td>
      <td>링크 A</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>Marekto 측정 단위 태깅을 가져오기 위해 사이트 링크를 업데이트해야 하는지 여부</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>그룹화 키</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>이 테이블의 주 개체 또는 엔터티입니다. 이 경우 "SiteLink"</p>
      </td>
      <td>
        <p>SiteLink</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사이트 링크에 대한 광고 공급자의 이름</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>랜딩 페이지의 URL입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td>
        <p>http://adobe.com/b2b-marketing-attribution?_bt =</p>
        <p>{creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL_CURRENT의 이전 값.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 매개 변수로 데코레이트할 URL입니다.</p>
        <p>(진단 필드, 내부 처리용)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake이 레코드를 만든 날짜</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake의 레코드 수정일</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>삭제된 경우 Snowflake의 삭제 날짜 기록</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_STAGE_DEFINITIONS {#biz-stage-definitions}

[!DNL Marketo Measure] 응용 프로그램에서 가져오거나 정의한 단계 목록입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>단계에 대한 고유 ID입니다.</p>
      </td>
      <td>
        <p>01J3100000QE753EAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-22 17:27:27.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>스테이지 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>단계 이름.</p>
      </td>
      <td>
        <p>구두</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_INACTIVE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>단계가 비활성 상태로 간주되는지 여부를 나타냅니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IN_CUSTOM_MODEL</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>사용자 지정 모델에서 추적할 단계가 선택되었는지 여부를 나타냅니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_BOOMERANG</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>부메랑 단계로 추적하기 위해 단계가 선택되었는지 여부를 나타냅니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_TRANSITION_TRACKING</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>전환을 추적하기 위해 단계가 선택되었는지 보여 줍니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>단계 상태</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 응용 프로그램 단계 매핑에 정의된 단계의 상태입니다.</p>
      </td>
      <td>
        <p>열기</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FROM_SALESFORCE</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>스테이지를 외부 소스 시스템에서 가져오는지 여부를 나타냅니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DEFAULT</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>단계가 기본값으로 설정되었는지 여부를 나타냅니다.</td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>순위</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>단계를 전환 순서로 정렬하는 데 사용되는 단계의 숫자 순위입니다.</p>
      </td>
      <td>
        <p>53</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>단계가 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_TOUCHPOINT {#biz-touchpoints}

구매자 접점, 리드 또는 연락처와 연관된 모든 접점. 리드 터치포인트 또는 연락처 터치포인트가 비활성화된 경우 이 테이블은 비어 있습니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Buyer Touchpoint(BT)의 고유 ID입니다.</p>
      </td>
      <td>
        <p>TP2_Person_00Q0Z000013e2PYUAY_2018-08-27:20-04-40-5655690.1ee8567c175a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-08-29 22:29:30.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>BT과 연계된 이메일 주소.</td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>BT과 연결된 연락처의 ID입니다.</p>
      </td>
      <td>0030Z00003K5bpKQAR</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BT과 연결된 계정의 ID입니다.</p>
      </td>
      <td>
        <p>0013100001lSSLcAAO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>리드 ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BT과 연계된 잠재 고객 ID.</p>
      </td>
      <td>
        <p>00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>UNIQUE_ID_PERSON</p>
      </td>
      <td>varchar</td>
      <td>
        <p>잠재 고객 또는 연락처와 관련된 상위 개인 레코드.</p>
      </td>
      <td>
        <p>Person_00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>BT을 생성한 사용자 터치포인트의 ID입니다.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-08-29:18-14-53-8102030.10df92cbb414</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>BT과 연계된 방문자 ID.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>터치포인트의 날짜입니다.</p>
      </td>
      <td>
        <p>2018년 8월 27일 20일:04:40년 0월</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>활동 유형, 웹 방문, 웹 양식, 웹 채팅, 전화 통화, [CRM] Campaign 또는 [CRM] 활동. CRM에서 "터치포인트 유형"이라고 합니다.</p>
      </td>
      <td>
        <p>웹 양식</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>채널</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 사용자 지정 채널 정의에 정의된 대로 터치포인트가 속하는 채널입니다. CRM에서는 "마케팅 채널 - 경로"라고 합니다.</p>
      </td>
      <td>Social.LinkedIn</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 첫 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>ABC</td>
    </tr>
    <tr>
      <td>
        <p>범주2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 두 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>예</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>범주3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 세 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>기타</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>카테고리 4</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 네 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td>
        <p>파트너</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>범주5</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 다섯 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>범주6</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 여섯 번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 7번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 8번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 9번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>범주10</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 10번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리11</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 11번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리12</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 12번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리13</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 13번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리14</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 14번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>카테고리15</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 세그먼트 정의에 정의된 대로 터치포인트가 속하는 15번째 범주에 대한 세그먼트 값입니다. CRM에서 "세그먼트"라고 합니다.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>브라우저 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있던 브라우저가 검색되었습니다.</p>
      </td>
      <td>Chrome</td>
    </tr>
    <tr>
      <td>
        <p>BROWSERVERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있었던 브라우저의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>68</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>플랫폼 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 플랫폼입니다.</p>
      </td>
      <td>
        <p>Windows</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_버전</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 플랫폼의 감지된 버전입니다.</p>
      </td>
      <td>10_12</td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. CRM에서는 "랜딩 페이지"라고 합니다.</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지 원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. 원시 랜딩 페이지에는 URL의 모든 쿼리 매개 변수가 포함됩니다. CRM에서는 "랜딩 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>https://info.adpbe.com/definitive-guide-to-pipeline-marketing?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU_COM_Demand_ Skills&amp;utm_content=DGPM&amp;utm_term=lisu03151846&amp;_bl=66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. CRM에서 "레퍼러 페이지"라고 합니다.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. 원시 레퍼러 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "레퍼러 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/feed</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Touchpoints 테이블에 표시되지 않고 Form_Submisses 테이블에 표시됩니다. CRM에서 "양식 URL"이라고 합니다.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>FORM_PAGE_RAW</td>
      <td>varchar</td>
      <td>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Touchpoints 테이블에 표시되지 않고 Form_Submisses 테이블에 표시됩니다. 원시 양식 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "양식 URL - 원시"라고 합니다.</td>
      <td>https://info.adobe.com/demo?hsCtaTracking=98adcc2f-afe2-40c4-9d79-40dcc41663ee%7C3cfaa909-39cb-4f5d-93eb-be05de6b0180</td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>양식 제출이 발생한 날짜.</p>
      </td>
      <td>
        <p>2017-06-20 01:06:41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>도시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 도시입니다.</p>
      </td>
      <td>
        <p>뉴욕</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>지역</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 영역입니다.</p>
      </td>
      <td>
        <p>뉴욕</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>국가</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 국가입니다.</p>
      </td>
      <td>
        <p>미국</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 미디어를 정의하는 데 사용됩니다. URL의 utm_medium에서 구문 분석하거나, 또는 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "cpc" 또는 "display"와 같은 값이 될 수 있습니다.</p>
      </td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 소스를 정의하는 데 사용됩니다. 이 값은 utm_source의 URL에서 구문 분석할 수 있으며, CRM에서 동기화된 경우 일반적으로 "CRM Campaign"으로 설정되거나 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "Google AdWords" 또는 "Facebook"와 같은 값일 수 있습니다. CRM에서 "터치포인트 Source"라고 합니다.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자가 검색하기 위해 브라우저에 입력한 후 웹 사이트에서 종료한 값. 키워드 구입에 따라 유료 검색 플랫폼에서 구입한 키워드와 일치하거나 일치하지 않을 수 있습니다.</p>
      </td>
      <td>
        <p>markeot measure 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 플랫폼 [!DNL Marketo Measure]은(는) 일반적으로 통합 파트너 중 하나에서 확인할 수 있습니다.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>li.502664737</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>MM SC 2016_14605342_3/7-3/31/16</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Marketo Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 ID입니다.</p>
      </td>
      <td>
        <p>li.502664737.138949954</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 이름.</p>
      </td>
      <td>
        <p>SU - COM 계정 - 수요 기술</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 ID입니다. 이는 Google Adwords에만 적용됩니다.</p>
      </td>
      <td>aw.6601259029.317738075.23105327435</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 이름. 이는 Google AdWords에만 적용됩니다.</p>
      </td>
      <td>마케팅 속성 - 일반</td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 ID입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 이름입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>예산 웨비나 - 사이드바</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 ID. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>li.502664737.138949954.66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>리수03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 첫 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>리드 생성 완료</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 두 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>파이프라인 마케팅에 대한 확실한 가이드를 다운로드합니다. https://lnkd.in/e9xYj5M</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에서 클릭스루하는 랜딩 페이지. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>https://image-store.slidesharecdn.com/d29165c0-1e0b-4ffc-a494-d2c77e7cd4a6-large.jpeg</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에 표시되는 친숙한 URL 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>marektomeasure.com/guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 ID입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>__GAId__lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다</p>
      </td>
      <td>
        <p>리수03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 구문과 구매 키워드 간에 일치하는 항목의 유형입니다.</p>
      </td>
      <td>
        <p>광범위</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 첫 번째 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 리드 생성 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 영업 기회 창출 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 닫힘 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>STAGES_TOUCHED</td>
      <td>varchar</td>
      <td>이 필드는 더 이상 사용되지 않습니다. 스테이지 정보에 대해서는 Stage_Transitions 테이블을 사용합니다.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 세션 중에 양식 채우기를 했는지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 첫 번째 노출 터치로 처리되는지 여부</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>첫 번째 터치이므로 이 터치포인트에 할당된 계산된 백분율입니다(Is_First_Touch 참조).</p>
      </td>
      <td>
        <p>10</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>잠재 고객 생성 터치이므로 이 접점에 할당된 계산된 백분율입니다(Is_Lead_Creation_Touch 참조).</p>
      </td>
      <td>
        <p>10</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>U자형 터치의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch 및 Is_Lead_Creation_Touch 참조).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>W자형 터치의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch, Is_Lead_Creation_Touch 및 Is_Opp_Creation_Touch 참조). BT이므로 0이 되어야 합니다.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENT</p>
      </td>
      <td>
        <p>번호(22,19)</p>
      </td>
      <td>
        <p>전체 경로 모델의 일부이므로 이 접점에 할당된 계산된 백분율(Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch 참조). BT이므로 0이 되어야 합니다.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_MODEL_PERCENTAGE</td>
      <td>번호(22,19)</td>
      <td>이 접점은 사용자 지정 모델의 일부이므로 이 접점에 할당된 계산된 백분율입니다(Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch 참조). BT이므로 0이 되어야 합니다.</p>
      </td>
      <td>0</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 삭제되었는지 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>행 키</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td>
        <p>Biz_Facts 보기에 대한 외래 키.</p>
      </td>
      <td>
        <p>-9004910726709710000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ROW_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ROW_KEY</p>
      </td>
      <td>
        <p>번호(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>랜딩 페이지 키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_URL {#biz-urls}

랜딩 페이지, 레퍼러 페이지 및 페이지 조회수의 URL 집계입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>전체 URL,.</td>
      <td>https://www.adobe.com/blog/strategic-marketing-plangoals</td>
    </tr>
    <tr>
      <td>체계</td>
      <td>varchar</td>
      <td>네트워크를 통한 웹 페이지의 보안 통신.</td>
      <td>https</td>
    </tr>
    <tr>
      <td>호스트</td>
      <td>varchar</td>
      <td>하위 도메인이 있는 URL의 도메인.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>PAGE_제목</td>
      <td>varchar</td>
      <td>페이지 제목</td>
      <td>B2B 마케팅 속성 다운로드에 대한 CMO의 안내서</td>
    </tr>
    <tr>
      <td>경로</td>
      <td>varchar</td>
      <td>호스트의 특정 위치를 가리키는 URL의 부분입니다.</td>
      <td>/블로그/전략적 마케팅 계획</td>
    </tr>
    <tr>
      <td>포트</td>
      <td>varchar</td>
      <td>인터넷 호스트의 포트이며 URL에서 선택 사항입니다.</td>
      <td>584</td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>5686109553536636820</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_USER_TOUCHPOINTS {#biz-user-touchpoints}

이메일에 연결된 이벤트에서 생성된 모든 터치포인트.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트에 대한 고유 ID.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2018-09-05 23:30:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>이메일</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트와 연계된 이메일 주소.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트를 만든 세션의 ID입니다.</p>
      </td>
      <td>
        <p>2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_MEMBER_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트를 생성한 캠페인 멤버의 ID입니다.</p>
      </td>
      <td>
        <p>00v0Z00001VTgv1QAD</p>
      </td>
    </tr>
    <tr>
      <td>CRM_ACTIVITY_ID</td>
      <td>varchar</td>
      <td>사용자 터치포인트를 만든 활동의 ID입니다.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>
        <p>CRM_EVENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트를 만든 이벤트의 ID입니다.</p>
      </td>
      <td>
        <p>00U0Z00000pCZmyUAG</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CRM_TASK_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트를 생성한 작업에 대한 항목입니다.</p>
      </td>
      <td>
        <p>00T0Z00004Qbd1jUAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자 터치포인트를 생성한 노출에 대한 ID.</p>
      </td>
      <td>00T0Z00004Qbd1jUAB</td>
    </tr>
    <tr>
      <td>IS_FIRST_KNOWN_TOUCH</td>
      <td>부울</td>
      <td>이 터치포인트가 영업 기회 여정의 첫 번째 터치로 처리되는지 여부입니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>관련 방문자 id의 첫 번째 쿠키 id.</td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>사용자 터치포인트가 발생한 날짜.</p>
      </td>
      <td>
        <p>2018년 1월 5일 16일:47:02월 0일</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>활동 유형, 웹 방문, 웹 양식, 웹 채팅, 전화 통화, [CRM] Campaign 또는 [CRM] 활동. CRM에서 "터치포인트 유형"이라고 합니다.</p>
      </td>
      <td>
        <p>웹 양식</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>채널</p>
      </td>
      <td>varchar</td>
      <td>
        <p>[!DNL Marketo Measure] 앱 내의 사용자 지정 채널 정의에 정의된 대로 터치포인트가 속하는 채널입니다. CRM에서는 "마케팅 채널 - 경로"라고 합니다.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>브라우저 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있던 브라우저가 검색되었습니다.</p>
      </td>
      <td>
        <p>Firefox</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSERVERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있었던 브라우저의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>33</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>플랫폼 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 플랫폼입니다.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_버전</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 플랫폼의 감지된 버전입니다.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. CRM에서는 "랜딩 페이지"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>랜딩 페이지 원시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트가 발생한 세션의 첫 번째 랜딩 페이지입니다. 원시 랜딩 페이지에는 URL의 모든 쿼리 매개 변수가 포함됩니다. CRM에서는 "랜딩 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+ marketo+%maeasure%27s+Pipeline+Marketing+Blog%29</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>레퍼러 페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. CRM에서 "레퍼러 페이지"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>일반적으로 사용자가 웹 사이트에 접속하기 직전의 외부 랜딩 페이지입니다. 원시 레퍼러 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "레퍼러 페이지 - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_페이지</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Attribution_Touchpoints 테이블에 표시되지 않고 Form_Submits 테이블에 표시됩니다. CRM에서 "양식 URL"이라고 합니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트를 초래한 세션에 기록된 첫 번째 양식입니다. 이후 양식 제출은 Attribution_Touchpoints 테이블에 표시되지 않고 Form_Submits 테이블에 표시됩니다. 원시 양식 페이지는 URL에 쿼리 매개 변수를 포함할 수 있습니다. CRM에서 "양식 URL - 원시"라고 합니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation?utm_source=linkedin&amp;utm_medium=paid&amp;utm_content=sfskill&amp;utm _campaign=Content%20-%20AdWords%20Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>양식 제출이 발생한 날짜.</p>
      </td>
      <td>
        <p>2015-06-03 17:49:10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>도시</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 도시입니다.</p>
      </td>
      <td>
        <p>오클랜드</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>지역</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 사용자가 세션 중에 있었던 감지된 영역입니다.</p>
      </td>
      <td>
        <p>캘리포니아</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>국가</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Javascript 및 IP 주소에서 세션 중에 사용자가 있는 감지된 국가입니다.</p>
      </td>
      <td>
        <p>미국</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 미디어를 정의하는 데 사용됩니다. URL의 utm_medium에서 구문 분석하거나, 또는 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "cpc" 또는 "display"와 같은 값이 될 수 있습니다.</p>
      </td>
      <td>
        <p>유료</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>터치포인트의 원인이 되는 소스를 정의하는 데 사용됩니다. 이 값은 utm_source의 URL에서 구문 분석할 수 있으며, CRM에서 동기화된 경우 일반적으로 "CRM Campaign"으로 설정되거나 [!DNL Marketo Measure]에서 광고를 확인할 수 있는 경우 "Google AdWords" 또는 "Facebook"와 같은 값일 수 있습니다. CRM에서 "터치포인트 Source"라고 합니다.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>사용자가 검색하기 위해 브라우저에 입력한 후 웹 사이트에서 종료한 값. 키워드 구입에 따라 유료 검색 플랫폼에서 구입한 키워드와 일치하거나 일치하지 않을 수 있습니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고 플랫폼 [!DNL Marketo Measure]은(는) 일반적으로 통합 파트너 중 하나에서 확인할 수 있습니다.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>계정 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 이름입니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 계정</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고주 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 사이트 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 ID입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 배치 이름입니다. 이는 Doubleclick Campaign Manager에만 적용됩니다.</p>
      </td>
      <td>
        <p>도로 방책</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_고유_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 ID입니다.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>캠페인 이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 캠페인 이름.</p>
      </td>
      <td>
        <p>브랜드</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 ID입니다. 이는 Google Adwords에만 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 그룹 이름. 이는 Google AdWords에만 적용됩니다.</p>
      </td>
      <td>
        <p>브랜드 - 핵심</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 ID입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 광고 이름입니다. 이는 Doubleclick Campaign Manager 및 Facebook(디스플레이)에 적용됩니다.</p>
      </td>
      <td>예산 웨비나 - 사이드바</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 ID. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.195329631298</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_이름</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정의 크리에이티브 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] 공식 사이트</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 첫 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>수익 계획 및 속성</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 광고에서 가져온 크리에이티브의 두 번째 줄이며, 광고가 해결된 광고 계정에서 가져옵니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>250개 이상의 회사가 마케팅 기여도를 위해 [!DNL Marketo Measure]을(를) 선택하는 이유를 알아봅니다. 데모 다운로드!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에서 클릭스루하는 랜딩 페이지. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>http://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 검색 광고에 표시되는 친숙한 URL 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 ID입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.46267805426</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>광고가 해결된 광고 계정에서 가져온 유료 검색 구매에서 구매한 키워드의 이름입니다. 이는 Google AdWords 및 Bing Ads(검색)에 적용됩니다</p>
      </td>
      <td>
        <p>[marketo]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_유형</p>
      </td>
      <td>varchar</td>
      <td>
        <p>검색 구문과 구매 키워드 간에 일치하는 항목의 유형입니다.</p>
      </td>
      <td>
        <p>정확</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 세션 중에 양식 채우기를 했는지 여부.</p>
      </td>
      <td>
        <p>참</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>이 터치포인트가 영업 기회 여정의 첫 번째 노출 터치로 처리되는지 여부입니다.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>부울</p>
      </td>
      <td>
        <p>터치포인트 삭제 여부.</p>
      </td>
      <td>
        <p>거짓</p>
      </td>
    </tr>
    <tr>
      <td>행 키</td>
      <td>번호(38,0)</td>
      <td>Biz_Facts 보기에 대한 외래 키.</td>
      <td>-5269090762570690000</td>
    </tr>
    <tr>
      <td>랜딩 페이지 키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>레퍼러_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_페이지_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_키</td>
      <td>번호(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_WEB_HOST_MAPPING {#biz-web-host-mappings}

[!DNL Marketo Measure] 세션 ID를 Adobe ECID 및 Munckin ID에 매핑하기 위한 매핑 테이블입니다.

<table>
  <tbody>
    <tr>
      <th>열</th>
      <th>데이터 유형</th>
      <th>설명</th>
      <th>샘플 데이터</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>매핑 레코드에 대한 고유 ID.</td>
      <td>
        <p>0d643578c0c74753eff91abe668ed328|2020-06-17:19:03:36|002|0|568668</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure]이(가) 기록된 쿠키 ID입니다.</td>
      <td>0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>관련 방문자 id의 첫 번째 쿠키 id.</td>
      <td>v_0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 세션 ID.</td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>매핑이 기록된 날짜.</td>
      <td>
        <p>2020-06-17 19:03:36.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>레코드를 마지막으로 수정한 날짜입니다.</p>
      </td>
      <td>
        <p>2020-06-17 19:03:36.000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_페이지</td>
      <td>varchar</td>
      <td>쿼리 매개 변수 없이 페이지 보기의 URL입니다.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_원시</td>
      <td>varchar</td>
      <td>쿼리 매개 변수를 포함한 페이지 보기의 URL.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html?x=nGfrBF&amp;utm_medium=cpc&amp;utm_source=intensify</p>
      </td>
    </tr>
    <tr>
      <td>IP 주소</td>
      <td>varchar</td>
      <td>기록된 IP 주소입니다.</td>
      <td>
        <p>159.203.142.127</p>
      </td>
    </tr>
    <tr>
      <td>유형</td>
      <td>varchar</td>
      <td>이벤트 유형을 나타냅니다.</td>
      <td>
        <p>호스트 매핑</p>
      </td>
    </tr>
    <tr>
      <td>USER_에이전트_문자열</td>
      <td>varchar</td>
      <td>페이지 보기 시 기록된 장치 및 브라우저입니다.</td>
      <td>
        <p>Mozilla/5.0(Windows NT 10.0, Win64, x64) AppleWebKit/537.36(KHTML, Gecko) Chrome/79.0.3945.130 Safari/537.36</p>
      </td>
    </tr>
    <tr>
      <td>CLIENT_SEQUENCE</td>
      <td>varchar</td>
      <td>세션에서 페이지 보기가 발생한 순서를 나타냅니다.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>CLIENT_RANDOM</td>
      <td>varchar</td>
      <td>내부 감사 및 처리에 사용됩니다.</td>
      <td>566868</td>
    </tr>
    <tr>
      <td>IS_DUPLICATED</td>
      <td>부울</td>
      <td>레코드가 중복으로 간주되는지 여부를 나타냅니다.</td>
      <td>거짓</td>
    </tr>
    <tr>
      <td>IS_PROCESSED</td>
      <td>부울</td>
      <td>내부 처리에 사용됩니다.</td>
      <td>참</td>
    </tr>
    <tr>
      <td>MAPPING_유형</td>
      <td>varchar</td>
      <td>[!DNL Marketo Measure] 쿠키 ID에 매핑된 ID 유형입니다.</td>
      <td>Adobe_OrgId_Ecid</td>
    </tr>
    <tr>
      <td>MAPPING_ORD_ID</td>
      <td>varchar</td>
      <td>Adobe IMS 조직 ID.</td>
      <td>8CC867C25245ADC30A490D4C</td>
    </tr>
    <tr>
      <td>MAPPING_COOKIE_ID</td>
      <td>varchar</td>
      <td>주어진 조직 ID에 대한 Adobe ECID.</td>
      <td>09860926390077352923264316157493772857</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 생성된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 마지막으로 수정된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake에서 레코드가 삭제된 것으로 표시된 날짜.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

## 샘플 쿼리 {#sample-queries}

**지난 달에 각 채널/하위 채널에 대해 몇 개의 구매자 접점(BT)이 있었습니까?**

```
--Note: This query can quickly be modified to show Buyer Attribution Touchpoint (BAT) counts by switching the biz_touchpoints table to the biz_attribution_touchpoints table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,trim(split(ch.name,'.')[1])  as subchannel
      ,count(bt.id)                 as buyer_touchpoint_count
  from biz_user_touchpoints     ut
       left outer join
       biz_touchpoints          bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_channels             ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
   and ut.touchpoint_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
group by 1,2
```

**전체 경로 속성 모델에 대해 지난 달에 종료된 각 채널의 특성 매출은 얼마입니까?**

```
--Note: This query does not perform any currency conversion.  If your data contains multiple currencies, you will need to add in logic to perform the conversion to the desired currency using the biz_conversion_rates table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,sum(opp.amount*(bat.full_path_percentage/100))   as attributed_revenue
  from biz_user_touchpoints         ut
       inner join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       inner join
       biz_opportunities            opp
        on bat.opportunity_id       = opp.id
       and opp._deleted_date        is null
       and opp.is_closed            = true
       and opp.is_won               = true
       and opp.close_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
       left outer join
       biz_channels                 ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
group by 1
```

**한 사람에 대한 전체 여정은 무엇입니까?  (단일 이메일 주소에 대한 모든 터치포인트를 표시합니다.)**

```
select ut.touchpoint_date
      ,ut.marketing_touch_type
      ,listagg(distinct ifnull(sdl.stage_name,sdo.stage_name),',')           as touchpoint_position
  from biz_user_touchpoints         ut
       left outer join
       biz_touchpoints              bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       left outer join
       biz_lead_stage_transitions   lst
        on lst.touchpoint_id        = bt.id
       and lst._deleted_date        is null
       and lst.is_pending           = false
       and lst.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdl
        on lst.stage_id             = sdl.id
       and sdl._deleted_date        is null
       left outer join
       biz_opp_stage_transitions    ost
        on ost.touchpoint_id        = bat.id
       and ost._deleted_date        is null
       and ost.is_pending           = false
       and ost.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdo
        on ost.stage_id             = sdo.id
       and sdo._deleted_date        is null
 where ut._deleted_date     is null
   and ut.email             = [email address]
group by 1,2
order by 1
```

**단일 기회에 대한 모든 구매자 속성 접점(BAT) 및 해당 속성 매출을 표시합니다.**

>[!NOTE]
>
>이 쿼리는 w 모양 모델에 대한 속성 매출을 반환합니다. 속성 매출 계산에서 필드를 업데이트하여 모델을 변경합니다.

```
select bat.id
      ,bat.touchpoint_date
      ,bat.email
      ,opp.amount*(bat.w_shape_percentage/100)             as attributed_revenue
      ,listagg(osd.stage_name,', ')                        as touchpoint_position
  from biz_opportunities               opp
       inner join
       biz_attribution_touchpoints     bat
        on bat.opportunity_id      = opp.id
       and bat._deleted_date       is null
       left outer join
       biz_opp_stage_transitions       ost
        on ost.touchpoint_id       = bat.id
       and ost._deleted_date       is null
       and ost.is_pending          = false
       and ost.is_non_transitional = false
       left outer join
       biz_stage_definitions            osd
        on ost.stage_id             = osd.id
       and osd._deleted_date        is null
 where opp._deleted_date    is null
   and opp.id               = [opportunity id]
group by 1,2,3,4
order by touchpoint_date
```

[위로 돌아가기](#data-warehouse-schema)
