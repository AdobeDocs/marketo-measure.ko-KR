---
unique-page-id: 18874672
description: 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 - Marketo 측정 - 제품 설명서
title: 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 14%

---

# 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

그 사이의 관계를 자세히 살펴봅시다 [!DNL Marketo Measure] 그리고 Salesforce.

## Salesforce 및 [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

한 번 [!DNL Marketo Measure] 계정이 만들어져서 [!DNL Salesforce] 연결되어 있고 [!DNL Marketo Measure] 에서는 마케팅 데이터를 CRM 인스턴스에 푸시하기 시작합니다 [!DNL Marketo Measure] 관리 패키지가 설치되고 [!DNL Marketo Measure] Salesforce 사용자에게는 편집 권한이 있습니다.

을 설치하지 않았다면 [!DNL Marketo Measure] Salesforce 패키지, [!DNL Marketo Measure] 에서는 Salesforce 인스턴스에 데이터를 쓰지 않습니다.

![](assets/1-3.png)

기본적으로 [!DNL Marketo Measure] 작업이 CRM에 데이터를 보낼 때마다 API 크레딧당 200개의 레코드를 내보냅니다. 대부분의 고객의 경우 이 API 크레딧은 [!DNL Marketo Measure] 및 CRM의 CPU 리소스 요구 사항입니다. 그러나 워크플로우 및 트리거와 같은 복잡한 CRM 구성이 있는 고객의 경우 일괄 처리 크기를 작게 지정하면 CRM 성능을 향상시키는 데 도움이 될 수 있습니다. 이를 위해 [!DNL Marketo Measure] 고객이 CRM 내보내기 배치 크기를 구성할 수 있습니다. 이 설정은 [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] 페이지의 [!DNL Marketo Measure] 웹 애플리케이션 및 고객은 일괄 처리 크기 200(기본값), 100, 50 또는 25 중에서 선택할 수 있습니다.

![](assets/how-bizible-and-salesforce-interact-2.png)

이 설정을 수정할 때는 작은 일괄 처리 크기가 CRM에서 더 많은 API 크레딧을 사용한다는 점에 유의하십시오. CRM에서 CPU 시간 초과 또는 높은 CPU 로드가 발생하는 경우에만 일괄 처리 크기를 줄이는 것이 좋습니다.

## Salesforce 표준 개체 및 액세스 {#salesforce-standard-objects-and-access}

여기에는 다음 항목이 나열됩니다 [!DNL Salesforce] 다음 표준 객체 [!DNL Marketo Measure] 연결이 설정되고 [!DNL Marketo Measure] 패키지가 설치되었습니다. 즉시 [!DNL Marketo Measure] 표준 [!DNL Salesforce] 개체 필드.

**리드**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>이메일</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>상태</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>변환된 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedContactId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedOpportunityId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>웹 사이트</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>회사</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Account__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**연락처**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>계정</p></td> 
   <td><p>표준</p></td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>이메일</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>작성일</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Case**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>SuppliedEmail</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**계정**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>웹 사이트</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Engagement_Score__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**기회**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>계정</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsWon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsClosed</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CloseDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>StageName</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>금액</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Bizible_Opportunity_Amount__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**캠페인**

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>이메일</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>상태</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>변환된 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedContactId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedOpportunityId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>웹 사이트</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>회사</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>유형</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td><br></td> 
  </tr> 
 </tbody> 
</table>

**캠페인 구성원**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>마지막 수정 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDeleted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>FirstResponseDate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>HasResponse</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ContactId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LeadId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CampaignId</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Bizible_Touchpoint_Date__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Date__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Contact__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Leade__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Opportunity__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] 의 사용자 지정 개체 [!DNL Salesforce] {#marketo-measure-custom-objects-in-salesforce}

SFDC의 표준 개체에서 사용자 지정 필드를 만드는 것 외에도 한 번 [!DNL Marketo Measure] 패키지가 설치되면 두 개의 사용자 지정 개체가 만들어집니다. 다음은 이러한 사용자 정의 객체 목록과 해당 필드를 나타내는 표가 있습니다 [!DNL Marketo Measure] 에 쓸 것입니다.

**구매자 터치포인트**

구매자 터치포인트는 [!DNL Marketo Measure] 사용자 지정 개체로서, 연락처, 리드 및 사례에 대한 마케팅 상호 작용을 캡슐화합니다.

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__Bizible_Person__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__SF_Campaign__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_Path__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Type__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Content__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Group_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Group_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Form_URL__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Form_URL_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Platform__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Browser__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_City__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Country__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Region__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_MatchType__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Position__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Text__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Medium__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Search_Phrase__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Segment__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_First_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_Lead_Creation_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_U_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Destination_URL__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Case__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**[!DNL Marketo Measure]개인**

다음 [!DNL Marketo Measure] 사람은 [!DNL Marketo Measure] Lead, Contact 및 Case 객체와 관련된 사용자 정의 객체입니다.

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Lead__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Case__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

## 구매자 기여도 분석 터치포인트 {#buyer-attribution-touchpoint}

구매자 기여도 분석 터치포인트는 [!DNL Marketo Measure] Opportunity에 대한 마케팅의 영향을 캡슐화하는 사용자 지정 개체입니다.

**구매자 기여도 분석 터치포인트**

<table> 
 <tbody> 
  <tr> 
   <th><p>필드</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__Account__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__SF_Campaign__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Opportunity__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Marketing_Channel_Path__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Type__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Content__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Group_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Group_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Campaign_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Name__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Form_URL__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Form_URL_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Platform__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Browser__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_City__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Country__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Region__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Id__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_MatchType__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Position__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Text__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Medium__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page_Raw__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Search_Phrase__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Segment__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_First_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_Lead_Conversion_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_U_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_W_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_Custom_Model__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Attribution_Custom_Model_2__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_First_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_Lead_Creation_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_U_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_W_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_Custom_Model__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Count_Custom_Model_2__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Destination_URL__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_First_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_Lead_Creation_Touch__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_U_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_W_Shaped__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_Custom_Model__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_Custom_Model_2__c</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>
