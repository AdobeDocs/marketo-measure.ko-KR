---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] 권한 집합 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 사용 권한 집합"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# [!DNL Marketo Measure] 사용 권한 집합 {#marketo-measure-permission-sets}

액세스 및 할당 방법 알아보기 [!DNL Marketo Measure] Salesforce의 권한 집합.

## [!DNL Marketo Measure] 사용 권한 집합 {#marketo-measure-permission-sets-1}

에는 세 개의 권한 세트가 포함되어 있습니다. [!DNL Marketo Measure] Salesforce 패키지. 이러한 권한 집합은에 대한 액세스 권한을 제공합니다. [!DNL Marketo Measure] 관리자, 마케터 및 표준 사용자용

Salesforce에서 권한 집합에 액세스하고 할당하려면 다음을 수행하십시오.

1. 클릭 **[!UICONTROL Setup]**.
1. 왼쪽 여백에서 **[!UICONTROL Users]**, 그런 다음 **[!UICONTROL Permission Sets]**.
1. 다음 항목 선택 [!DNL Marketo Measure] 할당할 권한 집합입니다.
1. 클릭 **[!UICONTROL Manage Assignments]**, 그런 다음 **[!UICONTROL Add Assignments]**.
1. 사용 권한 집합의 사용자를 선택하고 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 권한 집합 설명 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 관리자</strong></span></td> 
   <td><span>SFDC 관리자는에서 레코드를 생성, 읽기, 쓰기 및 삭제할 수 있습니다. [!DNL Marketo Measure] 개체. 다음에 적용되는 라이선스 [!DNL Marketo Measure] 데이터를 SFDC로 푸시하려면 이 권한 집합을 활성화해야 합니다. 또한 이 라이센스에는 이전에 리드가 전환된 시나리오에서 전환된 리드를 편집할 수 있는 기능이 있는 것이 좋습니다 [!DNL Marketo Measure] 레코드에 데이터 적용. 이렇게 하면 Salesforce와 [!DNL Marketo Measure]. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">자세한 내용은 여기 를 참조하십시오.</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 마케팅 사용자</strong></span></td> 
   <td><span>마케팅 사용자에게 레코드를 읽고 쓸 수 있는 기능을 제공합니다. [!DNL Marketo Measure] 개체. 마케팅 팀의 모든 구성원에게는 [!DNL Marketo Measure] 마케팅 사용자 권한 집합을 사용할 수 있습니다. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 표준 사용자</strong></span></td> 
   <td><span>사용자에게 다음 위치에서 레코드를 읽을 수 있는 기능을 제공합니다. [!DNL Marketo Measure] 개체.</span></td> 
  </tr> 
 </tbody> 
</table>

인바운드 영업 개발 팀 및 계정 경영진은 다음과 같은 이점을 얻을 수 있습니다. [!DNL Marketo Measure] 데이터. 다음 역할이 을 사용하려는 경우 [!DNL Marketo Measure] 보고의 데이터, 활성화 [!DNL Marketo Measure] 표준 사용자 권한 집합입니다.

>[!NOTE]
>
>또한 연결된 사용자에게는 &quot;마케팅 사용자&quot;가 있어야 합니다. [!DNL Salesforce] 사용자 수준에서 Campaign 개체에 액세스할 수 있는 프로필입니다. 확인하려면 다음을 클릭하십시오. **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **할당된 사용자**.
