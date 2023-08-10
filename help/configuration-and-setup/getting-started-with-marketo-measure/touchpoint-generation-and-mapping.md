---
unique-page-id: 18874554
description: 접점 생성 및 매핑 - [!DNL Marketo Measure] - 제품 설명서
title: 접점 생성 및 매핑
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# 접점 생성 및 매핑 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 기여도 분석 스토리는 다음 두 가지 프로세스에 따라 달라집니다.

* 접점 생성: 마케팅 및 판매 활동에 대한 개인의 상호 작용을 나타내는 접점을 생성합니다.
* 터치포인트를 적절한 채널 및 하위 채널에 크레딧하는 터치포인트 매핑

을 최대한 활용하기 위해 [!DNL Marketo Measure], 다음과 같이 작업해야 합니다. [!DNL Marketo Measure] 조직의 요구 사항에 맞게 두 프로세스를 사용자 정의할 수 있습니다.

접점 생성 메서드

접점 생성 프로세스는 &quot;은(는) 어떻게 됩니까?&quot;라는 질문에 답합니다. [!DNL Marketo Measure] 이런 일이 일어났다는 것을 알게 될 것인가?&quot; 기능 세트와 잠재 고객이 가질 수 있는 상호 작용 유형에 따라 최대 3가지 방법이 있습니다 [!DNL Marketo Measure] 은 상호 작용을 선택하고 터치 포인트를 만들어 나타낼 수 있습니다.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] 은 세션당 하나의 터치포인트만 생성합니다. 두 개 이상의 양식을 작성한 경우 첫 번째 양식 작성만 캡처됩니다.

| **인터랙션 유형** | **예** | **접점 생성 방법** |
|---|---|---|
| 온라인, 사이트에서 | 양식 채우기 | [!DNL Marketo Measure] JavaScript |
| 오프라인, 온라인이 사이트에 없음 | 박람회, 컨텐츠 신디케이션 파트너가 컨텐츠 참여 잠재 고객 목록을 제공합니다. | CRM 캠페인 멤버십이 (으)로 동기화됨 [!DNL Marketo Measure], 캠페인에서 직접 캠페인 동기화 유형 을 설정하거나 의 캠페인 페이지에서 규칙을 설정하여 [!DNL Marketo Measure] |
| 영업 활동 | SDR에 의한 아웃바운드 호출 | CRM 활동(작업 또는 이벤트) 레코드가에 동기화됨 [!DNL Marketo Measure], 다음에 대한 논리를 통해 [!UICONTROL Activities] 페이지 위치 [!DNL Marketo Measure] |

접점 매핑 메서드

접점 매핑 프로세스는 &quot;이 접점이 생성되면 어떻게 합니까?&quot;라는 질문에 대한 답을 제공합니다. [!DNL Marketo Measure] 어떤 채널과 하위 채널에 속하는지 알 수 있습니까?&quot; 접점 생성의 각 방법에는 고유한 접점 매핑 방법이 있습니다.

| **인터랙션 유형** | **생성 방법** | **매핑 방법** |
|---|---|---|
| 온라인, 사이트에서 | [!DNL Marketo Measure] JavaScript | 다음을 통해 [!DNL Online Channels] 페이지 위치 [!DNL Marketo Measure], UTM 값, 랜딩 페이지 및 참조 페이지 정보 참조 |
| 오프라인, 사이트가 아닌 온라인 | CRM Campaign 구성원 동기화 | 다음을 통해 [!UICONTROL Offline Channels] 페이지 위치 [!DNL Marketo Measure], 캠페인 유형 참조 |
| 영업 활동 | CRM 활동 동기화 | 다음을 통해 [!UICONTROL Online Channels] 페이지 위치 [!DNL Marketo Measure]에 할당된 캠페인 이름 을 참조하여 [!UICONTROL Activities] 페이지 |

>[!MORELIKETHIS]
>
>* [온라인 터치포인트 매핑 대상 [!DNL Marketo Measure] 채널/하위 채널](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [SFDC 내에서 CRM 캠페인 동기화](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [내에서 CRM 캠페인 동기화 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [CRM 캠페인 매핑 [!DNL Marketo Measure] 채널/하위 채널](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [판매 활동에서 접점 만들기](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [활동 FAQ 및 채널/하위 채널에 활동 접점 매핑](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

