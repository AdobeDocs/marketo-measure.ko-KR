---
unique-page-id: 18874672
description: ' [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 방법 - Marketo Measure - 제품 설명서'
title: ' [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 방법'
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: 3b14e758e81f237406da4e0fe1682a02b7a841fd
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 18%

---

# [!DNL Marketo Measure]과(와) [!DNL Salesforce]이(가) 상호 작용하는 방법 {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure]과(와) Salesforce 간의 관계를 자세히 살펴보겠습니다.

## Salesforce 및 [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

[!DNL Marketo Measure] 계정이 만들어지고 [!DNL Salesforce]이(가) 연결되면 [!DNL Marketo Measure] 관리 패키지가 설치되어 있고 [!DNL Marketo Measure] Salesforce 사용자에게 편집 권한이 있는 한 [!DNL Marketo Measure]에서 마케팅 데이터를 CRM 인스턴스로 푸시하기 시작합니다.

[!DNL Marketo Measure] Salesforce 패키지를 설치하지 않은 경우 [!DNL Marketo Measure]은(는) Salesforce 인스턴스에 데이터를 쓰지 않습니다.

![](assets/1-3.png)

기본적으로 [!DNL Marketo Measure]은(는) 작업이 데이터를 CRM으로 보낼 때마다 API 크레딧당 200개의 레코드를 내보냅니다. 대부분의 고객의 경우 [!DNL Marketo Measure]에서 사용하는 API 크레딧과 CRM의 CPU 리소스 요구 사항 간의 최적의 균형을 제공합니다. 그러나 워크플로우 및 트리거와 같이 복잡한 CRM 구성을 사용하는 고객의 경우 배치 크기를 줄이면 CRM 성능을 향상시키는 데 도움이 될 수 있습니다. 이를 위해 [!DNL Marketo Measure]에서 고객이 CRM 내보내기 일괄 처리 크기를 구성할 수 있습니다. 이 설정은 [!DNL Marketo Measure] 웹 애플리케이션의 [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] 페이지에서 사용할 수 있으며 고객은 배치 크기 200(기본값), 100, 50 또는 25 중에서 선택할 수 있습니다.

![](assets/how-bizible-and-salesforce-interact-2.png)

이 설정을 수정할 때는 배치 크기가 작을수록 CRM에서 더 많은 API 크레딧을 사용한다는 점을 유의하십시오. CRM에서 CPU 시간 초과 또는 높은 CPU 로드가 발생하는 경우에만 배치 크기를 줄이는 것이 좋습니다.

## Salesforce 연결된 사용자 권한 {#salesforce-connected-user-permissions}

**전용 사용자에 대한 Marketo Measure 관리자 권한 집합**: SFDC 관리자가 Marketo Measure 개체에 대해 CRUD 작업을 수행할 수 있도록 허용합니다.

**전환된 잠재 고객 사용 권한 집합 보기 및 편집**: 이렇게 하면 Marketo Measure에서 잠재 고객이 연락처로 전환된 후 잠재 고객을 꾸밀 수 있습니다.

**Salesforce 마케팅 사용자 확인란**: 사용자가 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다.
* Campaign &quot;만들기&quot;에 대한 추가 권한이 필요합니다.

**Marketo Measure 표준 사용자**: 사용자에게 Marketo Measure 개체에서 레코드를 읽을 수 있는 기능을 제공합니다.

## Salesforce 표준 개체 및 액세스 {#salesforce-standard-objects-and-access}

여기에는 [!DNL Marketo Measure]이(가) 상호 작용하는 [!DNL Salesforce] 표준 개체와 연결이 설정되고 [!DNL Marketo Measure] 패키지가 설치되면 이 개체에 추가하는 사용자 지정 필드가 나열됩니다. 기본적으로 [!DNL Marketo Measure]은(는) 표준 [!DNL Salesforce] 개체 필드에 쓰지 않습니다.

**리드**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>이메일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>상태</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>전환일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>웹 사이트</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>회사</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr>
 </tbody> 
</table>

**연락처**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>계정</td> 
   <td>표준</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>이메일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>만든 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
 </tbody> 
</table>

**사례**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>SuppliedEmail</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td>
  </tr> 
 </tbody> 
</table>

**계정**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>웹 사이트</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Engagement_Score__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**기회**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>이름</td> 
   <td>표준</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>계정</td> 
   <td>표준</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsWon</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>닫힘</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CloseDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>StageName</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>금액</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Opportunity_Amount__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**영업 기회 연락처 역할**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>영업 기회 ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>연락처 ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr>

<tr> 
   <td>Isprimary</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>역할</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
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
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>이메일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>상태</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>전환일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>웹 사이트</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>회사</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>유형</td> 
   <td>표준</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>이름</td> 
   <td>표준</td> 
   <td>x</td> 
   <td>x</td> 
  </tr>
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

**캠페인 구성원**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>마지막 수정 날짜</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>최초 응답일</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>HasResponded</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>연락처 ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>잠재 고객 ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>캠페인 ID</td> 
   <td>표준</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Touchpoint_Date__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Date__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Contact__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Leade__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Opportunity__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Salesforce 계정 내에서 삭제 이벤트를 캡처하는 Marketo Measure의 정확성을 보장하려면 아래 개체에 대해 복제 가능한 권한이 필요합니다. 복제 가능한 권한은 다음 개체와 함께 표준으로 제공됩니다.
>
>* 계정
>* Campaign
>* 캠페인 멤버
>* 연락처
>* 이벤트
>* 리드
>* 기회
>* 작업


## [!DNL Salesforce]의 사용자 지정 개체 [!DNL Marketo Measure]개 {#marketo-measure-custom-objects-in-salesforce}

SFDC의 표준 개체에 사용자 지정 필드를 만드는 것 외에도 [!DNL Marketo Measure] 패키지가 설치되면 두 개의 사용자 지정 개체가 만들어집니다. 다음은 이러한 사용자 지정 개체 목록과 [!DNL Marketo Measure]이(가) 쓸 필드를 나타내는 표입니다.

**Buyer Touchpoint**

Buyer Touchpoint은 연락처, 잠재 고객 및 서비스 케이스에 대한 마케팅 상호 작용을 캡슐화하는 [!DNL Marketo Measure] 사용자 지정 개체입니다.

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Person__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__SF_Campaign__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_Path__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Type__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Content__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_City__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Region__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Search_Phrase__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_First_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Lead_Creation_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_U_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

**[!DNL Marketo Measure]명**

[!DNL Marketo Measure]명은 잠재 고객, 연락처 및 사례 개체 모두와 관련된 [!DNL Marketo Measure] 사용자 지정 개체입니다.

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Lead__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Buyer Attribution Touchpoint은 Opportunity에 대한 마케팅의 영향을 캡슐화하기 위한 [!DNL Marketo Measure] 사용자 지정 개체입니다.

**Buyer Attribution Touchpoint**

<table> 
 <tbody> 
  <tr> 
   <th>필드</th> 
   <th>Standard/Custom</th> 
   <th>읽기</th> 
   <th>쓰기</th> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__SF_Campaign__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Opportunity__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_Path__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Type__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Content__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_City__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Region__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Id__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Search_Phrase__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_First_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Lead_Conversion_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_U_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_W_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Custom_Model__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Custom_Model_2__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_First_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Lead_Creation_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_U_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_W_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Custom_Model__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Custom_Model_2__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_First_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Lead_Creation_Touch__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_U_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_W_Shaped__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Custom_Model__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Custom_Model_2__c</td> 
   <td>맞춤형</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>[통합 권한 개요](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
