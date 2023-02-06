---
unique-page-id: 18874765
description: Salesforce 샌드박스와 Marketo Measure 통합 테스트 - [!DNL Marketo Measure] - 제품 설명서
title: Salesforce 샌드박스와 Marketo Measure 통합 테스트
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# Salesforce 샌드박스와 Marketo Measure 통합 테스트 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

다음 중 하나 [!DNL Marketo Measure] 핵심 기능은 웹 사이트에서 작업을 통해 디지털 마케팅 활동을 추적한 다음 해당 데이터를 프로덕션에 푸시할 수 있는 기능입니다 [!DNL Salesforce org] Lead 및 Contacts를 통해 Lead 및 Contact 를 참조하십시오. 그러나 일반적으로 Sandbox 통합 내에 웹 사이트에서 생성된 인바운드 리드는 없으므로 데이터에 대한 초점은 순전히 오프라인 관점에서 비롯됩니다.

다음은 테스트의 두 단계에 대해 참조되는 두 개의 소스입니다. [1-4단계](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) 및 [5-6단계](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md). 일부 영역에서 보다 자세한 내용을 제공하므로 이러한 문서를 검토하는 것이 좋습니다.

1. Campaign에 업로드할 수 있도록 CSV로 일부 리드를 만들어야 합니다. 이를 수행하는 방법은 프로덕션 Salesforce에서 보고서를 통해 일부 Lead 를 내보내는 것입니다. 그렇지 않으면 Excel 파일에서 리드를 수동으로 만든 다음 가져올 CSV로 저장할 수 있습니다. 약 20개의 레코드만 있으면 됩니다. 파일에는 다음 열이 있어야 합니다.

   1. 이메일
   1. 회사
   1. 성
   1. 이름(선택 사항이지만 권장됨)

1. 샌드박스 환경에 로그인합니다.
1. 먼저 테스트 캠페인을 만듭니다. 이벤트 또는 뉴스레터와 같은 캠페인 유형을 사용하는 것이 좋습니다.
1. 캠페인이 만들어지면 을(를) 선택하여 리드를 캠페인 구성원으로 업로드합니다 **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**.
1. 완료되면, 캠페인 페이지 레이아웃으로 다시 돌아가 선택 목록 필드인 &quot;구매자 터치포인트 활성화&quot;를 수행합니다. 값을 선택합니다. **[!UICONTROL Include All Campaign Members]**.

이 작업이 완료되면 이 작업 간의 동기화가 시작됩니다 [!DNL Marketo Measure] 및 [!DNL Salesforce] 및 를 리드 레코드에 적용합니다. 다음 날 이라는 보고서를 통해 다시 확인하는 것이 좋습니다. &quot;Buyer Touchpoint on Leads&quot;( [!UICONTROL Buyer Touchpoints Reports] 폴더 아래에 표시됩니다. 보고서가 각 리드에 대해 터치포인트를 채우는 경우 성공의 징후입니다.
