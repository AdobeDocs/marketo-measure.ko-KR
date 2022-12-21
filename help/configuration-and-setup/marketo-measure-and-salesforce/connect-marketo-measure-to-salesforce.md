---
unique-page-id: 18874580
description: Salesforce에 Marketo 측정 연결 - [!DNL Marketo Measure] - 제품 설명서
title: Salesforce에 Marketo 측정 연결
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Salesforce에 Marketo 측정 연결 {#connect-marketo-measure-to-salesforce}

이 문서에서는 [!DNL Salesforce] 계정 [!DNL Marketo Measure] 계정이 필요합니다.

## 연결 중 [!DNL Marketo Measure] with [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 시크릿 브라우저를 사용하여 [!DNL Marketo Measure].

1. 화면 상단의 메뉴 막대에서 **[!UICONTROL My Account]** 을 클릭하고 [!UICONTROL Settings] 선택 사항입니다.

1. 왼쪽의 옵션 설정 열에서 [!UICONTROL Connections] 아래에 [!UICONTROL Integrations] 섹션을 참조하십시오.

   ![](assets/1.png)

1. 연결의 CRM 섹션에서 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/2.png)

1. CRM 연결 선택을 묻는 팝업 창이 나타납니다. 을(를) 클릭합니다. [!UICONTROL Connect] 버튼 옆에 있음 [!DNL Salesforce] 로고.

   ![](assets/3.png)

1. 마지막 팝업 창이 나타나고 사용자에게 [!DNL Salesforce] 자격 증명, 샌드박스 또는 프로덕션. 정보를 입력하고 **[!UICONTROL Authorize]** 계정을 [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] 하나에만 연결할 수 있습니다 [!DNL Salesforce] 한 번에 인스턴스입니다.
>
>* A [!DNL Marketo Measure] SFDC 프로덕션 인스턴스로 연결을 전환하기 전에 인스턴스를 SFDC 샌드박스 인스턴스에 연결하여 통합을 테스트할 수 있습니다.
>* SFDC Sandbox를 사용하여 먼저 테스트하는 경우, Lead, Contact, Account, Opportunity, Campaign 및 Case 객체의 필드 측면에서 SFDC 프로덕션 인스턴스의 정확한 복제본인 복제본으로 테스트하는 것이 좋습니다. Lead, Contact, Account, Opportunity, Campaign 및 Case 객체에 대한 업데이트 시 실행되는 프로덕션에서 활성 APEX 트리거가 있는 경우 샌드박스에서 활성화되도록 해야 합니다.
>* 테스트가 완료되면, [!DNL Marketo Measure] 프로덕션을 가리키도록 계정 [!DNL Salesforce] (샌드박스 대신) [!DNL Salesforce]). 통합이 빌드된 방식으로 인해, 한 번 [!DNL Marketo Measure] 계정이 프로덕션에 연결됨 [!DNL Salesforce]를 켜면 &quot;뒤로&quot; 이동하고 샌드박스에 연결할 수 없습니다 [!DNL Salesforce] org.


