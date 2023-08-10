---
description: 오프라인 채널에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 오프라인 채널에 대한 우수 사례
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# 오프라인 채널에 대한 우수 사례 {#best-practices-for-offline-channels}

## 개요 {#overview}

정확하게 하려면 [!DNL Marketo Measure] 보고 기능을 사용하려면 마케팅 채널이 올바르게 설정되어야 합니다. &#39;[!UICONTROL Marketing Channel]&#39; 필드에는 터치포인트가 속할 수 있는 가장 높은 수준의 마케팅 전략 그룹(예: 이벤트, 웨비나, 콘텐츠 신디케이션 등)이 표시됩니다.

마케팅 채널을 설정하는 방법에는 온라인과 오프라인의 두 가지 측면이 있습니다. 이 문서는 다음에 중점을 둡니다. [!DNL Marketo Measure] 오프라인 채널 설정 및 유지 관리에 대한 모범 사례 권장 사항 및 와 동기화하는 방법 [!DNL Marketo Measure] crm 캠페인을 통해.

오프라인 채널에는 두 가지 주요 측면이 있습니다.

1. 를 알리는 프레임워크인 오프라인 채널 매핑 [!DNL Marketo Measure] 오프라인 터치포인트가 속한 채널 및 하위 채널
1. 오프라인 터치포인트 만들기인 오프라인 캠페인 동기화

오프라인 터치포인트는 CRM Campaign에서 생성되며, 을 통해 디지털로 추적할 수 없는 모든 마케팅 상호 작용을 추적하기 위한 것입니다. [!DNL Marketo Measure] 웹 사이트의 페이지에 구현된 JavaScript. CRM 캠페인이 와 동기화되는 경우 [!DNL Marketo Measure], 터치포인트가 캠페인 내에서 정의된 캠페인 멤버에 대해 생성됩니다.

이러한 터치포인트에 대한 &#39;마케팅 채널&#39; 값은 캠페인의 &#39;유형&#39; 필드를 기반으로 합니다. &#39;CRM 캠페인 유형&#39;을 &#39;마케팅 채널&#39; 및 &#39;하위 채널&#39;에 매핑하면 의 &#39;오프라인 채널&#39; 탭에서 관리됩니다. [!DNL Marketo Measure] 계정 설정. 오프라인 채널 매핑이 정확하고 최신 상태인지 확인하면 오프라인 터치포인트 데이터가 내의 올바른 마케팅 채널 및 하위 채널에 귀속됩니다 [!DNL Marketo Measure] 보고.

## 우수 사례 | 오프라인 채널 매핑 {#best-practice-offline-channel-mapping}

오프라인 채널을 처음 매핑하거나 검토하여 정확성을 확인하는 경우에도 다음 모범 사례를 염두에 두십시오.

* 오프라인 채널을 위한 숙고된 프레임워크 만들기
   * 마케팅 캠페인의 구성과 마케팅 캠페인이 [!DNL Marketo Measure] 프레임워크. 오프라인 채널에 표시해야 하는 채널과 하위 채널 및 이러한 채널을 서로 구별하는 CRM Campaign 유형을 결정합니다
* 현재 CRM 캠페인 &#39;유형&#39; 값을 먼저 활용하도록 작업
   * 오프라인 채널은 CRM Campaign &#39;Type&#39;에 의해 정의되지만, 이상적인 오프라인 채널 및 하위 채널 값을 수용하도록 사용자 지정 CRM Campaign &#39;Type&#39; 값을 만들어야 할 수 있습니다. 이상적인 사용자 지정 CRM 캠페인 &#39;유형&#39; 값에는 아래에 표시된 명명 규칙이 적용되어야 합니다.
      * 채널 - 서브채널
      * 예: Event - Tradeshow
      * 이렇게 하면 서브채널 수준에 대한 매핑이 가능한 한 쉽고 깔끔하게 됩니다
* 하나의 하위 채널만 하나의 CRM 캠페인 &#39;유형&#39;에 매핑될 수 있음
   * 여러 CRM 캠페인 &#39;유형&#39;을 단일 채널에 매핑할 수 있지만 각 채널 내의 각 하위 채널에는 하나의 CRM 캠페인 &#39;유형&#39;만 매핑할 수 있습니다
* 오프라인 캠페인만 동기화되려면 오프라인 CRM 캠페인 &#39;유형&#39;만 오프라인 채널에 매핑해야 합니다. [!DNL Marketo Measure] 터치포인트를 만들려면:
   * 온라인 CRM 캠페인 &#39;유형&#39;을 [!UICONTROL Marketing Channel] = &quot;NULL&quot;. 이 값은 오프라인 채널이 검토되었음을 나타내는 &#39;빨간색 플래그&#39; 역할을 하며 &quot;NULL&quot;에 매핑된 CRM 캠페인 &#39;유형&#39;이 ONLINE &#39;유형&#39;이므로 동기화해서는 안 됩니다. [!DNL Marketo Measure]. 온라인 CRM 캠페인 &#39;유형&#39;과 관련된 터치포인트는 다음을 통해 이미 추적됩니다. [!DNL Marketo Measure] 온라인 기능 및 채널. 이러한 캠페인을 동기화하면 &quot;중복&quot; 터치포인트/더블 카운트가 발생할 수 있습니다.

## 우수 사례 | 오프라인 Campaign 동기화 {#best-practice-offline-campaign-sync}

* &#39;유형&#39; 필드가 각 CRM 캠페인에 대해 정확한지 확인합니다.
   * &#39;유형&#39;은 동기화된 후 캠페인에서 가져온 모든 터치포인트에 대한 마케팅 채널 및 하위 채널을 결정합니다
* CRM 기반 캠페인 동기화 방법(구매자 터치포인트 활성화) 또는 [!DNL Marketo Measure] 앱 기반 동기화 메서드 (내 사용자 지정 캠페인 동기화)[!UICONTROL Campaigns]의 &#39; 탭 [!UICONTROL Marketo Measure] 계정 설정), 오프라인 터치포인트는 캠페인 구성원이 캠페인 및 브랜드와 실제 오프라인 계약을 맺은 경우에만 만들어야 합니다.
   * 이벤트 또는 웨비나와 같은 오프라인 채널의 경우: &quot;등록&quot;은 일반적으로 웹 사이트 및 [!DNL Marketo Measure] 온라인 기능. 따라서 &quot;등록됨&quot; 상태의 캠페인 멤버는 이중 계산을 방지하기 위해 Campaign에서 오프라인 터치포인트를 받지 않아야 합니다. 오프라인 터치포인트는 이벤트 또는 웨비나에 대한 &quot;출석&quot;만 나타냅니다.
   * 콘텐츠 신디케이션과 같은 일부 오프라인 채널은 일반적으로 더 간단합니다. 모든 캠페인 멤버가 실제로 캠페인에 반응했음을 나타내는 동일한 &#39;응답됨&#39; 상태를 갖습니다. 이 경우 타사 사이트의 콘텐츠를 다운로드하므로 오프라인 터치포인트를 받아야 합니다
* 에서 사용자 지정 Campaign 동기화 방법을 사용하는 경우 [!DNL Marketo Measure] 앱에서 &#39;접점 날짜&#39; 필드는 접점 상호 작용이 실제로 발생한 시기를 가장 잘 나타내는 Campaign 또는 캠페인 멤버의 날짜 필드를 기반으로 하는지 확인하십시오
* CRM Campaign에서 가져온 오프라인 터치포인트에 대한 &#39;터치포인트 날짜&#39;를 재정의해야 하는 경우 &#39;터치포인트 날짜 벌크 업데이트&#39; 버튼을 활용하십시오. 접점은 가능한 한 정확해야 가장 정확한 &#39;접점 위치&#39;와 이에 따른 적절한 속성 크레딧을 유지할 수 있습니다

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

처음에 설정되면 오프라인 채널 설정은 그에 따라 오프라인 터치포인트를 계속 만듭니다. 가장 좋은 방법은 적어도 1년에 두 번 오프라인 설정을 검토하는 것입니다. 이를 통해 깨끗하고 정확한 구매자 터치포인트 데이터를 보장합니다.

또한 캠페인 관리 또는 프로세스를 변경하는 경우 [!DNL Marketo Measure] 오프라인 채널 매핑 및/또는 동기화 프로세스.

의 오프라인 채널 설정을 업데이트하도록 팀을 트리거할 수 있는 변경 사항입니다. [!DNL Marketo Measure] 포함할 수 있는 항목:

* CRM 캠페인 &#39;유형&#39;이 생성되거나 편집됨
* 캠페인 멤버 &#39;상태&#39;가 생성되거나 편집됨
* &#39;구매자 접점 활성화&#39; 필드를 통해 CRM Campaign 동기화 방법을 사용하는 경우, 생성된 모든 CRM Campaign에 대해 이 필드를 검토하고 업데이트해야 합니다. 이 필드를 무시하면 관련된 오프라인 터치포인트 데이터가 없습니다.
* CRM Campaign에서 온라인 접점으로 보이는 오프라인 접점을 발견하는 경우(마케팅 채널 = NULL), 관련 CRM Campaign이 검토되고 동기화가 비활성화되었는지 확인하십시오

최근 팀이 위 중 하나를 경험한 경우 [!DNL Marketo Measure] 는 오프라인 채널 매핑 및 오프라인 캠페인을 검토하여 적절하게 변경하고 올바르게 동기화하도록 권장합니다.

>[!MORELIKETHIS]
>
>* [오프라인 채널 설정](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [사용자 지정 캠페인 동기화 - 앱 동기화](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [오프라인 캠페인 동기화 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md)
>* [오프라인 캠페인 및 캠페인 멤버 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/campaigns-and-campaign-members.md)
>* [Campaign 동기화 날짜 - CRM 동기화](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/campaign-sync-dates.md)
>* [여러 캠페인 레코드 유형에 대한 구성](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [캠페인 목록 보기 만들기](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [이전 데이터 동기화](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-historical-data.md)
