---
unique-page-id: 18874765
description: Salesforce 샌드박스와 Marketo Measure 통합 테스트 - [!DNL Marketo Measure]
title: Salesforce 샌드박스와 Marketo Measure 통합 테스트
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 1%

---

# Salesforce 샌드박스와 Marketo Measure 통합 테스트 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure] 핵심 기능 중 하나는 웹 사이트에서의 작업을 통해 디지털 마케팅 노력을 추적한 다음 리드 및 연락처를 통해 해당 데이터를 프로덕션 [!DNL Salesforce org]에 푸시하는 기능입니다. 그러나 일반적으로 샌드박스 통합 내에는 웹 사이트에서 생성된 인바운드 리드가 없으므로 데이터에 대한 초점은 완전히 오프라인 관점에서 비롯됩니다.

다음은 테스트의 두 단계에 대해 참조되는 두 가지 소스입니다. [1~4](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&language=en_US&type=5)단계 및 [5~6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)단계. 이러한 문서는 일부 영역에서 보다 자세한 정보를 제공하므로 검토하는 것이 좋습니다.

1. Campaign에 업로드할 수 있도록 CSV로 몇 가지 잠재 고객을 만들어야 합니다. 이렇게 하는 방법은 프로덕션 Salesforce에서 보고서를 통해 일부 Lead 를 내보내는 것입니다. 그렇지 않으면 Excel 파일에서 리드를 수동으로 만든 다음 가져오기를 위해 CSV로 저장할 수 있습니다. 약 20개의 레코드만 있으면 됩니다. 파일에는 다음 열이 있어야 합니다.

   1. 이메일
   1. 회사
   1. 성
   1. 이름(선택 사항이지만 권장됨)

1. 샌드박스 환경에 로그인합니다.
1. 테스트 캠페인을 만듭니다. 이벤트 또는 뉴스레터와 같은 캠페인 유형을 사용합니다.
1. 캠페인이 만들어지면 **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**&#x200B;을(를) 선택하여 리드를 캠페인 멤버로 업로드합니다.
1. 완료되면 캠페인 페이지 레이아웃으로 돌아가 선택 목록 필드인 &quot;구매자 터치포인트 활성화&quot;를 확인할 수 있습니다. 값을 선택하십시오. **[!UICONTROL Include All Campaign Members]**.

이 작업이 완료되면 [!DNL Marketo Measure]과(와) [!DNL Salesforce] 간의 동기화가 시작되고 Lead 레코드에 터치포인트가 적용됩니다. 보고서 탭의 [!UICONTROL Buyer Touchpoints Reports] 폴더에 있는 &quot;잠재 고객의 Buyer Touchpoint&quot;라는 보고서를 통해 다음날 다시 확인하는 것이 좋습니다. 보고서가 각 리드에 대한 터치포인트를 채우는 경우 성공의 표시입니다.
