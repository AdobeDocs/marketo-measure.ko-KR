---
unique-page-id: 18874580
description: Marketo Measure을 Salesforce에 연결 - [!DNL Marketo Measure]
title: Marketo Measure을 Salesforce에 연결
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Marketo Measure을 Salesforce에 연결 {#connect-marketo-measure-to-salesforce}

이 문서에서는 [!DNL Salesforce] 계정을 [!DNL Marketo Measure] 계정에 연결하는 방법에 대한 개요를 제공합니다.

## [!DNL Salesforce]과(와) [!DNL Marketo Measure] 연결 중 {#connecting-marketo-measure-with-salesforce}

1. 시크릿 브라우저를 사용하여 [!DNL Marketo Measure]에 로그인합니다.

1. 화면 상단의 메뉴 모음에서 **[!UICONTROL My Account]**(으)로 이동하여 **[!UICONTROL Settings]** 옵션을 클릭합니다.

1. 왼쪽의 설정 옵션 열에서 [!UICONTROL Integrations] 섹션 아래에 있는 **[!UICONTROL Connections]**&#x200B;을(를) 클릭합니다.

   ![](assets/connect-marketo-measure-to-salesforce-1.png)

1. 연결의 CRM 섹션 아래에서 **[!UICONTROL Set Up New CRM Connection]**&#x200B;을(를) 클릭합니다.

   ![](assets/connect-marketo-measure-to-salesforce-2.png)

1. CRM 연결을 선택하라는 팝업 창이 나타납니다. [!DNL Salesforce] 로고 옆의 **[!UICONTROL Connect]**&#x200B;을(를) 클릭합니다.

   ![](assets/connect-marketo-measure-to-salesforce-3.png)

1. [!DNL Salesforce] 자격 증명, 샌드박스 또는 프로덕션을 묻는 마지막 팝업 창이 나타납니다. 정보를 입력하고 **[!UICONTROL Authorize]**&#x200B;을(를) 클릭하여 계정을 [!DNL Marketo Measure]에 연결합니다.

>[!NOTE]
>
>[!DNL Marketo Measure]은(는) 한 번에 하나의 [!DNL Salesforce] 인스턴스에만 연결할 수 있습니다.
>
>* SFDC 프로덕션 인스턴스로 연결을 전환하기 전에 [!DNL Marketo Measure] 인스턴스를 SFDC 샌드박스 인스턴스에 연결하여 통합을 테스트할 수 있습니다.
>* SFDC 샌드박스를 사용하여 먼저 테스트하는 경우 Lead, Contact, Account, Opportunity, Campaign 및 Case 객체의 필드 측면에서 SFDC 프로덕션 인스턴스의 정확한 복제본인 로 테스트하는 것이 좋습니다. Lead, Contact, Account, Opportunity, Campaign 및 Case 객체에 대한 업데이트를 실행하는 프로덕션에 활성 APEX 트리거가 있는 경우 샌드박스에서 해당 트리거를 활성화해야 합니다.
>* 테스트가 완료되면 [!DNL Marketo Measure] 계정이 [!DNL Salesforce] 샌드박스 대신 [!DNL Salesforce] 프로덕션을 가리키도록 업데이트됩니다. 통합이 빌드된 방식으로 인해 [!DNL Marketo Measure] 계정이 프로덕션 [!DNL Salesforce]에 연결되면 &quot;뒤로&quot;로 이동하여 샌드박스 [!DNL Salesforce] 조직에 연결할 수 없습니다.

## API 크레딧 사용 {#api-credits-usage}

Marketo Measure은 CRM 통합 작업을 사용하여 통합 사용자를 통해 클라이언트의 Salesforce와 상호 작용합니다. 이 사용자를 통한 모든 데이터 교환은 Salesforce API 크레딧을 사용합니다. 통합 사용자에게 크레딧 할당량을 할당할 수 있는 기능이 있으며, 이는 과도한 API 호출을 규제하는 역할을 합니다. 이 할당량 또는 제한은 24시간마다 재설정됩니다.

**내 계정** > **설정** > **CRM** > **일반** > **일별 CRM API 제한**&#x200B;을 통해 Marketo Measure에서 이 제한에 액세스하고 테넌트에 대해 이 제한을 구성할 수 있습니다.

![](assets/connect-marketo-measure-to-salesforce-4.png)

### API 크레딧 제한 설정 {#setting-a-limit-for-api-credits}

1. **내 계정** > **설정**(으)로 이동합니다.

1. CRM에서 **일반**&#x200B;을 클릭합니다. **일별 CRM API 제한** 옵션이 표시됩니다.

1. 편집하려면 잠금 아이콘을 클릭하십시오.

   ![](assets/connect-marketo-measure-to-salesforce-5.png)

1. 원하는 제한을 100,000보다 크거나 같게 입력합니다. 완료되면 **저장**&#x200B;을 클릭합니다.

   ![](assets/connect-marketo-measure-to-salesforce-6.png)

>[!NOTE]
>
>연결된 솔루션에 사용 가능한 Salesforce API 크레딧을 늘리려면 Salesforce 관리자에게 문의하고 [이 Salesforce 문서](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}를 참조하십시오.

>[!MORELIKETHIS]
>
>[오류 알림](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
