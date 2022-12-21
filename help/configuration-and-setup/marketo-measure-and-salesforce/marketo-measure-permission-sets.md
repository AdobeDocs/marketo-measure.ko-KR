---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] 권한 집합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 권한 집합"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# [!DNL Marketo Measure] 권한 집합 {#marketo-measure-permission-sets}

액세스 및 할당 방법을 알아봅니다. [!DNL Marketo Measure] Salesforce의 권한 집합입니다.

## [!DNL Marketo Measure] 권한 집합 {#marketo-measure-permission-sets-1}

세 개의 권한 세트가 [!DNL Marketo Measure] Salesforce 패키지 이러한 권한 집합에는 [!DNL Marketo Measure] 관리자, 마케터 및 표준 사용자용.

Salesforce에서 권한 집합에 액세스하여 할당하려면 다음을 수행합니다.

1. 클릭 **[!UICONTROL Setup]**.
1. 왼쪽 여백에 있는 **[!UICONTROL Users]**, 그런 다음 **[!UICONTROL Permission Sets]**.
1. 을(를) 선택합니다 [!DNL Marketo Measure] 권한 집합을 지정할 수 있습니다.
1. 클릭 **[!UICONTROL Manage Assignments]**, 그런 다음 **[!UICONTROL Add Assignments]**.
1. 권한 집합에 대한 사용자를 선택하고 을(를) 클릭합니다 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 사용 권한 집합 설명 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 관리자</strong></span></td> 
   <td><span>SFDC 관리자에게 레코드를 작성, 읽기, 쓰기, 삭제할 수 있는 기능을 제공합니다. [!DNL Marketo Measure] 개체. 사용 중인 라이선스 [!DNL Marketo Measure] sfdc로 데이터를 푸시하려면 이 권한 세트가 활성화되어 있어야 합니다. 또한 이 라이센스에는 이전에 리드가 전환되는 시나리오에서 변환된 리드를 편집할 수 있는 기능이 있는 것이 좋습니다 [!DNL Marketo Measure] 레코드에 데이터 적용 이렇게 하면 Salesforce와 Salesforce 간 보고의 정확성이 보장됩니다 [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">자세한 내용은 여기 를 참조하십시오</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 마케팅 사용자</strong></span></td> 
   <td><span>마케팅 사용자에게 [!DNL Marketo Measure] 개체. 마케팅 팀의 모든 구성원에게 [!DNL Marketo Measure] 마케팅 사용자 권한 세트가 활성화되었습니다. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 표준 사용자</strong></span></td> 
   <td><span>사용자에게 [!DNL Marketo Measure] 개체.</span></td> 
  </tr> 
 </tbody> 
</table>

인바운드 영업 개발 팀 및 계정 관리자는 [!DNL Marketo Measure] 데이터. 이러한 역할을 사용하려면 [!DNL Marketo Measure] 보고에서 데이터를 사용 [!DNL Marketo Measure] 표준 사용자 권한 집합입니다.

>[!NOTE]
>
>또한 을 통해 연결된 사용자는 &quot;마케팅 사용자&quot;가 있어야 합니다 [!DNL Salesforce] 프로필이 사용자 수준에서 활성화되어 Campaign 개체에 액세스할 수 있습니다. 이를 확인하려면 **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **할당된 사용자**.
