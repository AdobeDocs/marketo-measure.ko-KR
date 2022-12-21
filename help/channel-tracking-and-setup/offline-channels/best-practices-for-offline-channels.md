---
description: 오프라인 채널에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 오프라인 채널에 대한 우수 사례
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# 오프라인 채널에 대한 우수 사례 {#best-practices-for-offline-channels}

## 개요 {#overview}

정확하려면 [!DNL Marketo Measure] 보고 시 마케팅 채널을 올바로 설정해야 합니다. &#39;[!UICONTROL Marketing Channel]&#39; 필드에는 터치포인트가 속한 가장 높은 수준의 마케팅 전술 그룹(예: 이벤트, 웨비나, 컨텐츠 신디케이션 등)이 표시됩니다.

마케팅 채널 설정에는 두 가지 측면이 있습니다. 온라인 및 오프라인. 이 문서는 [!DNL Marketo Measure] 오프라인 채널을 설정 및 유지 관리하고, 이를 와 동기화하는 방법에 대한 우수 사례 권장 사항 [!DNL Marketo Measure] CRM 캠페인 사용.

오프라인 채널에는 두 가지 주요 측면이 있습니다.

1. 을 지시하는 프레임워크인 오프라인 채널 매핑 [!DNL Marketo Measure] 오프라인 터치포인트가 속한 채널 및 하위 채널
1. 오프라인 터치포인트를 만드는 오프라인 캠페인 동기화

오프라인 터치포인트는 CRM 캠페인에서 만들어지고, 를 통해 디지털 방식으로 추적할 수 없는 모든 마케팅 상호 작용을 추적하기 위한 것입니다 [!DNL Marketo Measure] 웹 사이트의 페이지에 구현된 JavaScript입니다. CRM 캠페인이 [!DNL Marketo Measure], 터치포인트는 캠페인 내에서 정의된 캠페인 구성원에 대해 만들어집니다.

이러한 터치포인트에 대한 &#39;마케팅 채널&#39; 값은 캠페인의 &#39;유형&#39; 필드를 기반으로 합니다. &#39;CRM 캠페인 유형&#39;을 &#39;마케팅 채널&#39; 및 &#39;하위 채널&#39;에 매핑하는 작업은 사용자의 &#39;오프라인 채널&#39; 탭에서 관리합니다 [!DNL Marketo Measure] 계정 설정. 오프라인 채널 매핑이 정확한지 및 최신 상태인지 확인하면 오프라인 터치 포인트 데이터가 사용자 내의 올바른 마케팅 채널 및 하위 채널에 귀속됩니다 [!DNL Marketo Measure] 보고.

## 우수 사례 | 오프라인 채널 매핑 {#best-practice-offline-channel-mapping}

오프라인 채널을 처음 매핑하거나 검토하여 정확성을 확인하는지 여부에 관계없이 다음 우수 사례를 기억하십시오.

* 오프라인 채널에서 의도한 프레임워크를 만듭니다
   * 마케팅 캠페인의 구성과 마케팅 캠페인이 [!DNL Marketo Measure] 프레임워크. 오프라인 채널에서 어떤 채널과 하위 채널을 표시해야 하는지 및 CRM 캠페인 유형이 서로 구분하는지 결정합니다
* 현재 CRM 캠페인 &#39;유형&#39; 값을 먼저 활용하십시오
   * 오프라인 채널은 CRM 캠페인 &#39;유형&#39;에 의해 정의되지만 이상적인 오프라인 채널 및 하위 채널 값을 수용하려면 사용자 지정 CRM 캠페인 &#39;유형&#39; 값을 만들어야 할 수 있습니다. 이상적인 사용자 지정 CRM 캠페인 &#39;유형&#39; 값에는 아래에 표시된 이름 지정 규칙이 적용됩니다.
      * 채널 - 하위 채널
      * 예: 이벤트 - 트레이드방법
      * 이렇게 하면 하위 채널 수준에 대한 매핑이 최대한 쉽고 깨끗해집니다
* 하나의 하위 채널만 하나의 CRM 캠페인 &#39;Type&#39;에 매핑할 수 있습니다
   * 여러 CRM 캠페인 &#39;유형&#39;을 단일 채널에 매핑할 수 있지만 하나의 CRM 캠페인 &#39;Type&#39;만 각 채널 내의 각 하위 채널에 매핑할 수 있습니다
* 오프라인 캠페인만 과 동기화되려면 오프라인 CRM 캠페인 &#39;유형&#39;만 오프라인 채널에 매핑해야 합니다 [!DNL Marketo Measure] 터치포인트를 만드는 방법은 다음과 같습니다.
   * 온라인 CRM 캠페인 &#39;유형&#39;은 [!UICONTROL Marketing Channel] = &quot;NULL&quot;. 이 값은 오프라인 채널이 검토되었고 &quot;NULL&quot;에 매핑된 모든 CRM 캠페인 &#39;Type&#39;이 온라인 &#39;Type&#39;이므로 와 동기화하면 안 됩니다. [!DNL Marketo Measure]. 온라인 CRM 캠페인 &#39;유형&#39;과 관련된 터치포인트는 를 통해 이미 추적됩니다 [!DNL Marketo Measure] 온라인 기능 및 채널. 이러한 캠페인을 동기화하면 &quot;중복&quot; 터치포인트/이중 카운팅의 위험이 발생합니다

## 우수 사례 | 오프라인 캠페인 동기화 {#best-practice-offline-campaign-sync}

* 각 CRM 캠페인에서 &#39;유형&#39; 필드가 정확한지 확인합니다
   * &#39;유형&#39;은 동기화되면 캠페인에서 가져온 모든 터치포인트에 대해 마케팅 채널 및 하위 채널을 결정합니다
* CRM 기반 캠페인 동기화 방법 사용(구매자 터치포인트 사용) 또는 [!DNL Marketo Measure] 앱 기반 동기화 메서드 (&#39; 내에서 사용자 지정 캠페인 동기화[!UICONTROL Campaigns]&#39; 탭 [!UICONTROL Marketo Measure] 계정 설정), 오프라인 터치포인트는 캠페인 구성원이 캠페인 및 브랜드와 실제 오프라인 계약을 가진 경우에만 만들어야 합니다.
   * 이벤트 또는 웨비나와 같은 오프라인 채널의 경우: &quot;등록&quot;은 일반적으로 웹 사이트에서 양식 제출을 통해 추적되며 [!DNL Marketo Measure] 온라인 기능입니다. 따라서 상태가 &quot;등록됨&quot;인 캠페인 구성원은 이중 계산을 방지하기 위해 캠페인에서 오프라인 터치포인트를 수신하지 않아야 합니다. 오프라인 접점은 이벤트 또는 웨비나에 대한 &quot;참석&quot;만 대표해야 합니다.
   * 컨텐츠 신디케이션과 같은 일부 오프라인 채널은 일반적으로 모든 캠페인 구성원이 캠페인에 실제로 응답했음을 나타내는 동일한 &#39;응답됨&#39; 상태를 가지고 있으므로, 타사 사이트에서 컨텐츠를 다운로드하므로 오프라인 터치포인트를 수신해야 합니다
* 에서 사용자 지정 캠페인 동기화 방법을 사용하는 경우 [!DNL Marketo Measure] 앱에서는 &#39;터치포인트 날짜&#39; 필드가 캠페인이나 캠페인 구성원의 날짜 필드를 기반으로 하며 터치포인트 상호 작용이 실제로 발생하는 시기를 가장 잘 나타냅니다
* CRM 캠페인에서 가져온 오프라인 접점에 대해 &#39;터치포인트 날짜&#39;를 무시해야 하는 경우 &#39;대량 업데이트 터치 포인트 날짜&#39; 단추를 활용하십시오. 터치 포인트 날짜가 가능한 한 정확해야 터치 포인트가 가장 정확한 &#39;터치 포인트 위치&#39;를 보유하여 적절한 기여도 분석 크레딧의 양을 확보할 수 있습니다

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

처음에 설정되면, 오프라인 채널 설정은 계속해서 오프라인 접점을 그에 따라 만듭니다. 우수 사례로서, 1년에 두 번 이상 오프라인 설정을 검토하는 것이 좋습니다. 이렇게 하면 깨끗하고 정확한 구매자 터치 포인트 데이터가 보장됩니다.

또한 Campaign 관리 또는 프로세스를 변경하는 경우 업데이트를 해야 합니다 [!DNL Marketo Measure] 오프라인 채널 매핑 및/또는 동기화 프로세스.

팀에서 의 오프라인 채널 설정을 업데이트하도록 트리거할 수 있는 변경 사항 [!DNL Marketo Measure] 에는 다음이 포함되어 있습니다.

* CRM 캠페인 &#39;유형&#39;을 만들거나 편집했습니다
* 캠페인 구성원 &#39;상태&#39;가 만들어지거나 편집되었습니다.
* &#39;구매자 터치포인트 활성화&#39; 필드를 통해 CRM 캠페인 동기화 방법을 사용하는 경우, 이 필드가 만들어지는 모든 CRM 캠페인에 대해 검토되고 업데이트되는지 확인하십시오. 이 필드가 무시되면 관련 오프라인 접점 데이터가 없습니다
* 온라인 터치포인트(마케팅 채널 = NULL)로 보이는 CRM 캠페인에서 오프라인 터치포인트를 가져오는 경우, 관련 CRM 캠페인이 검토되고 동기화가 비활성화되었는지 확인하십시오

만약 당신의 팀이 최근에 위의 어떤 것을 경험했다면, [!DNL Marketo Measure] 는 오프라인 채널 매핑 및 오프라인 캠페인을 검토하여 적절한 변경 작업을 수행하고 이 매핑이 제대로 동기화되는지를 확인할 것을 권장합니다.

>[!MORELIKETHIS]
>
>* [오프라인 채널 설정](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [사용자 지정 캠페인 동기화 - 앱 동기화](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [오프라인 캠페인 동기화 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [오프라인 캠페인 및 캠페인 구성원 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [캠페인 동기화 날짜 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [여러 캠페인 레코드 유형에 대한 구성](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [캠페인 목록 보기 만들기](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [이전 데이터 동기화](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

