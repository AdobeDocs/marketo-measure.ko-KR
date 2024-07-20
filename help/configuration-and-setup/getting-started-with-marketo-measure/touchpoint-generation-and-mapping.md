---
unique-page-id: 18874554
description: 접점 생성 및 매핑 - [!DNL Marketo Measure]
title: 접점 생성 및 매핑
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# 접점 생성 및 매핑 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 기여도 분석 스토리는 다음 두 가지 프로세스에 영향을 미칩니다.

* 접점 생성: 마케팅 및 판매 활동에 대한 개인의 상호 작용을 나타내는 접점을 생성합니다.
* 터치포인트를 적절한 채널 및 하위 채널에 크레딧하는 터치포인트 매핑

[!DNL Marketo Measure]을(를) 최대한 활용하려면 [!DNL Marketo Measure] 담당자와 함께 조직의 요구 사항에 맞게 두 프로세스를 사용자 정의해야 합니다.

접점 생성 메서드

접점 생성 프로세스는 &quot;이 문제가 발생했음을 [!DNL Marketo Measure]이(가) 어떻게 알 수 있습니까?&quot;라는 질문에 답합니다. 기능 집합 및 잠재 고객이 가질 수 있는 상호 작용 유형에 따라 [!DNL Marketo Measure]에서 상호 작용을 선택하고 터치포인트를 만들어 나타낼 수 있는 방법은 최대 세 가지입니다.

>[!IMPORTANT]
>
>[!DNL Marketo Measure]은(는) 세션당 하나의 터치포인트만 생성합니다. 두 개 이상의 양식을 작성한 경우 첫 번째 양식 작성만 캡처됩니다.

| **상호 작용 유형** | **예** | **접점 생성 메서드** |
|---|---|---|
| 온라인, 사이트에서 | 양식 채우기 | [!DNL Marketo Measure] JavaScript |
| 오프라인, 사이트에서 온라인이 아님 | 박람회; 컨텐츠 신디케이션 파트너가 컨텐츠 참여자 목록을 전달합니다. | CRM 캠페인 멤버십이 캠페인에서 직접 캠페인 동기화 유형을 설정하거나 [!DNL Marketo Measure]의 캠페인 페이지에서 규칙을 설정하여 [!DNL Marketo Measure]에 동기화되었습니다. |
| 영업 활동 | SDR에 의한 아웃바운드 호출 | CRM 활동(작업 또는 이벤트) 레코드가 [!DNL Marketo Measure]의 [!UICONTROL Activities] 페이지에서 논리를 통해 [!DNL Marketo Measure]에 동기화됨 |

접점 매핑 메서드

접점 매핑 프로세스는 &quot;이 접점이 만들어지면 [!DNL Marketo Measure]이(가) 해당 접점이 속한 채널과 하위 채널을 어떻게 알 수 있습니까?&quot;라는 질문에 답합니다. 접점 생성의 각 방법에는 고유한 접점 매핑 방법이 있습니다.

| **상호 작용 유형** | **생성 메서드** | **매핑 메서드** |
|---|---|---|
| 온라인, 사이트에서 | [!DNL Marketo Measure] JavaScript | UTM 값, 랜딩 페이지 및 참조 페이지 정보를 참조하여 [!DNL Marketo Measure]의 [!DNL Online Channels] 페이지를 통해 |
| 오프라인, 사이트가 아닌 온라인 | CRM Campaign 구성원 동기화 | [!DNL Marketo Measure]의 [!UICONTROL Offline Channels] 페이지를 통해 캠페인 유형 참조 |
| 영업 활동 | CRM 활동 동기화 | [!DNL Marketo Measure]의 [!UICONTROL Online Channels] 페이지에서 [!UICONTROL Activities] 페이지에 지정된 캠페인 이름을 참조하도록 합니다. |

>[!MORELIKETHIS]
>
>* [온라인 터치포인트를  [!DNL Marketo Measure] 채널/하위 채널에 매핑](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [SFDC 내에서 CRM 캠페인 동기화](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [CRM 캠페인을  [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 내에서 동기화 중
>* [CRM 캠페인을  [!DNL Marketo Measure] 채널/하위 채널에 매핑](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [판매 활동에서 접점 만들기](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [채널/하위 채널에 대한 활동 FAQ 및 활동 터치포인트 매핑](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

