---
unique-page-id: 18874672
description: 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 - Marketo Measure - 제품 설명서
title: 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 19%

---

# 방법 [!DNL Marketo Measure] 및 [!DNL Salesforce] 상호 작용 {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

그 사이의 관계를 좀 더 자세히 살펴보자 [!DNL Marketo Measure] 및 Salesforce.

## Salesforce 및 [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

한 번 [!DNL Marketo Measure] 계정이 만들어지고 [!DNL Salesforce] 연결되었습니다. [!DNL Marketo Measure] 는 마케팅 데이터를 CRM 인스턴스에 푸시하기 시작합니다. [!DNL Marketo Measure] 관리 패키지가 설치되고 [!DNL Marketo Measure] Salesforce 사용자는 편집 권한이 있습니다.

설치하지 않은 경우 [!DNL Marketo Measure] Salesforce 패키지, [!DNL Marketo Measure] 은(는) Salesforce 인스턴스에 데이터를 쓰지 않습니다.

![](assets/1-3.png)

기본적으로, [!DNL Marketo Measure] 작업이 데이터를 CRM으로 보낼 때마다 API 크레딧당 200개의 레코드를 내보냅니다. 대부분의 고객은 이렇게 함으로써 사용한 API 크레딧 간의 최적의 균형을 확보할 수 있습니다. [!DNL Marketo Measure] 및 CRM의 CPU 리소스 요구 사항입니다. 그러나 워크플로우 및 트리거와 같이 복잡한 CRM 구성을 사용하는 고객의 경우 배치 크기를 줄이면 CRM 성능을 향상시키는 데 도움이 될 수 있습니다. 이를 위해, [!DNL Marketo Measure] 고객이 CRM 내보내기 일괄 처리 크기를 구성할 수 있습니다. 이 설정은 [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] 페이지의 [!DNL Marketo Measure] 웹 애플리케이션과 고객은 200(기본값), 100, 50 또는 25의 배치 크기 중에서 선택할 수 있습니다.

![](assets/how-bizible-and-salesforce-interact-2.png)

이 설정을 수정할 때는 배치 크기가 작을수록 CRM에서 더 많은 API 크레딧을 사용한다는 점을 유의하십시오. CRM에서 CPU 시간 초과 또는 높은 CPU 로드가 발생하는 경우에만 배치 크기를 줄이는 것이 좋습니다.

## Salesforce 표준 개체 및 액세스 {#salesforce-standard-objects-and-access}

다음 목록을 표시합니다. [!DNL Salesforce] 표준 개체 [!DNL Marketo Measure] 는 와 상호 작용하며, 연결이 설정되고 [!DNL Marketo Measure] 패키지가 설치되었습니다. 기본, [!DNL Marketo Measure] 는 어떤 표준에도 쓰지 않습니다. [!DNL Salesforce] 오브젝트 필드.

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

**영업 기회**

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

**캠페인 멤버**

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


## [!DNL Marketo Measure] 의 사용자 지정 개체 [!DNL Salesforce] {#marketo-measure-custom-objects-in-salesforce}

SFDC의 표준 오브젝트에서 사용자 정의 필드를 만드는 것 외에도 [!DNL Marketo Measure] 패키지가 설치되면 사용자 지정 개체 두 개가 만들어집니다. 다음은 이러한 사용자 지정 개체의 목록과 다음 필드를 나타내는 표입니다. [!DNL Marketo Measure] 에 씁니다.

**Buyer Touchpoint**

Buyer Touchpoint은 [!DNL Marketo Measure] 연락처, 잠재 고객 및 서비스 케이스에 대한 마케팅 상호 작용을 캡슐화하는 사용자 지정 개체입니다.

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

**[!DNL Marketo Measure]개인**

다음 [!DNL Marketo Measure] 개인이 [!DNL Marketo Measure] 잠재 고객, 연락처 및 사례 개체 모두와 관련된 사용자 지정 개체입니다.

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

Buyer Attribution Touchpoint은 [!DNL Marketo Measure] Opportunity에 대한 마케팅의 영향을 캡슐화하는 사용자 지정 개체입니다.

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
