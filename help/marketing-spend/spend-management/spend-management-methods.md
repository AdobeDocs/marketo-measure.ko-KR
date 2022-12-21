---
description: 지출 관리 방법 - [!DNL Marketo Measure] - 제품 설명서
title: 지출 관리 방법
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# 지출 관리 방법 {#spend-management-methods}

ROI 보고의 성공에 있어 데이터 사용 [!DNL Marketo Measure]. 모든 채널 및 하위 채널에서 정확하고 포괄적인 ROI 보고를 수행하려면 적절한 지출 데이터를 가져와야 합니다 [!DNL Marketo Measure].

로 데이터를 전송하는 방법에는 세 가지가 있습니다 [!DNL Marketo Measure]. 각 방법은 특정 데이터 입력에서 비용 데이터를 가져오도록 설계되었습니다.

**1) API 연결된 계정**

연결된 모든 광고 계정 [!DNL Marketo Measure] API를 통해 자동으로 를 가져옵니다 [!DNL Marketo Measure] ROI 보고용 연결된 계정을 확인하고 따라서 비용을 줄이려면 [!DNL Marketo Measure] 앱을 선택하고 [!UICONTROL Connections] 아래의 탭 [!UICONTROL Integrations] 섹션을 참조하십시오. API 연결을 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하십시오 [통합 광고 플랫폼](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 문서.

**2) CRM 캠페인 비용 동기화**

모두 [!DNL Marketo Measure] 계정에는 [CRM 캠페인 비용 동기화](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). 기본적으로 이 기능 비트는 &quot;아니요&quot;로 설정되지만 언제든지 설정할 수 있습니다.

![](assets/spend-management-methods-1.png)

이 기능을 활성화하면 다음 기준을 충족하는 모든 CRM 캠페인/프로그램에서 비용을 자동으로 가져옵니다

나. [!DNL Marketo Measure] 먼저 캠페인/프로그램이 일치하는 터치포인트에서 터치포인트를 만들고 있는지 확인합니다 [Campaign 동기화 규칙](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 생성되었거나 일치하는 [프로그램 동기화 규칙](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) 생성되었거나 [구매자 터치포인트 값 활성화](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) 는 &quot;모든 캠페인 구성원 포함&quot; 또는 &quot;응답된 캠페인 구성원 포함&quot;입니다.

ii. 시작 날짜를 캠페인/프로그램에 채워야 합니다.

3. 종료 날짜는 캠페인/프로그램에서도 채워야 합니다

4. 마지막으로 실제 비용(SFDC의 캠페인) 또는 기간 비용(Marketo의 프로그램)을 지정해야 합니다.

**3) 수동 원가 업로드**

이 메서드를 사용하면 다음 작업을 수행할 수 있습니다 [지출 데이터 업로드](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) API 연결된 계정 또는 CRM 캠페인 비용 동기화에서 적용되지 않는 채널 및 하위 채널에 대해 설명합니다. 마케팅 지출 섹션으로 이동하여 [!DNL Marketo Measure] 설정, 채널에 대한 CSV 파일을 통해 비용 데이터를 업로드할 수 있습니다.

고객은 이러한 세 가지 방법을 모두 결합하여 비용을 관리할 수 있으며()의 특정 설정에 따라 달라집니다 [!DNL Marketo Measure]. 다음 세 가지 방법으로 지출액을 가져올 수 있기 때문입니다 [!DNL Marketo Measure], Discover에 있는 마케팅 비용 보드를 활용하여 모든 지출 데이터를 종합적으로 파악하는 것이 좋습니다. 이 보드는 모든 채널과 관련 비용을 확인할 수 있는 유일한 장소입니다. 마케팅 비용 보드를 사용하면 지출 데이터에 차이가 있을 수 있는 위치와 ROI 보고를 향상시키는 방법을 신속하게 파악할 수 있습니다.
