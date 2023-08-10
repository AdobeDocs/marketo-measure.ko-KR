---
unique-page-id: 18874580
description: Marketo Measure을 Salesforce에 연결 - [!DNL Marketo Measure] - 제품 설명서
title: Marketo Measure을 Salesforce에 연결
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Marketo Measure을 Salesforce에 연결 {#connect-marketo-measure-to-salesforce}

이 문서에서는 연결 방법에 대한 개요를 제공합니다. [!DNL Salesforce] 계정 대상: [!DNL Marketo Measure] 계정입니다.

## 연결 중 [!DNL Marketo Measure] 포함 [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 시크릿 브라우저를 사용하여 다음으로 로그인 [!DNL Marketo Measure].

1. 화면 상단의 메뉴 표시줄에서 다음 위치로 이동합니다. **[!UICONTROL My Account]** 을(를) 클릭하고 [!UICONTROL Settings] 옵션을 선택합니다.

1. 왼쪽의 설정 옵션 열에서 [!UICONTROL Connections] 다음 아래에 위치: [!UICONTROL Integrations] 섹션.

   ![](assets/1.png)

1. 연결의 CRM 섹션에서 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/2.png)

1. CRM 연결을 선택하라는 팝업 창이 나타납니다. 다음을 클릭합니다. [!UICONTROL Connect] 단추 옆에 있는 [!DNL Salesforce] 로고.

   ![](assets/3.png)

1. 을(를) 묻는 마지막 팝업 창이 나타납니다. [!DNL Salesforce] 자격 증명, 샌드박스 또는 프로덕션 정보를 입력하고 **[!UICONTROL Authorize]** 계정을 연결할 대상 [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] 은(는) 한 개만 연결할 수 있습니다. [!DNL Salesforce] 인스턴스를 한 번에 만듭니다.
>
>* A [!DNL Marketo Measure] SFDC 프로덕션 인스턴스로 연결을 전환하기 전에 SFDC 샌드박스 인스턴스에 연결하여 통합을 테스트할 수 있습니다.
>* SFDC 샌드박스를 사용하여 먼저 테스트하는 경우 Lead, Contact, Account, Opportunity, Campaign 및 Case 객체의 필드 측면에서 SFDC 프로덕션 인스턴스의 정확한 복제본인 로 테스트하는 것이 좋습니다. Lead, Contact, Account, Opportunity, Campaign 및 Case 객체에 대한 업데이트를 실행하는 프로덕션에 활성 APEX 트리거가 있는 경우 샌드박스에서 해당 트리거를 활성화해야 합니다.
>* 테스트를 완료하면 [!DNL Marketo Measure] 프로덕션을 가리키는 계정 [!DNL Salesforce] (샌드박스 대신) [!DNL Salesforce]). 통합 빌드 방법으로 인해 [!DNL Marketo Measure] 계정이 프로덕션에 연결되어 있습니다. [!DNL Salesforce], &quot;뒤로&quot;로 이동하여 샌드박스에 연결할 수 없습니다 [!DNL Salesforce] org.

