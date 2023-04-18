---
unique-page-id: 18874554
description: 터치 포인트 생성 및 매핑 - [!DNL Marketo Measure] - 제품 설명서
title: 터치 포인트 생성 및 매핑
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
source-git-commit: 950dbfacf48cbb81acad9c40033c25a765287bee
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# 터치 포인트 생성 및 매핑 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 속성 스토리는 두 가지 프로세스에 따라 다릅니다.

* 마케팅 및 판매 활동으로 개인의 상호 작용을 나타내는 터치포인트를 만드는 터치포인트 생성
* 터치 포인트를 적절한 채널 및 하위 채널에 크레딧하는 터치 포인트 매핑

최대한 활용할 수 있도록 [!DNL Marketo Measure]와 함께 작업해야 합니다. [!DNL Marketo Measure] 조직의 요구 사항에 맞게 두 프로세스를 모두 사용자 정의할 수 있습니다.

터치 포인트 생성 방법

터치 포인트 생성 프로세스는 다음과 같은 질문에 답합니다. &quot;어떻게 [!DNL Marketo Measure] 이것이 일어났다는 것을 알고 싶습니까?&quot; 잠재 고객이 가질 수 있는 기능 세트와 상호 작용 유형에 따라 최대 3가지 방법이 있습니다 [!DNL Marketo Measure] 은 상호 작용을 선택하고 터치 포인트를 만들어 나타낼 수 있습니다.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] 세션당 하나의 터치포인트만 생성합니다. 두 개 이상의 양식이 작성되면 첫 번째 양식 채우기만 캡처됩니다.

| **상호 작용 유형** | **예** | **터치 포인트 생성 방법** |
|---|---|---|
| 온라인, 사이트에서 | 양식 채우기 | [!DNL Marketo Measure] JavaScript |
| 오프라인; 사이트에 온라인 상태가 아님 | 무역 박람회 컨텐츠 신디케이션 파트너는 사용자의 컨텐츠에 참여한 리드 목록을 제공합니다 | 에 동기화된 CRM 캠페인 멤버십 [!DNL Marketo Measure]를 설정하는 것이 좋습니다. [!DNL Marketo Measure] |
| 영업 활동 | SDR의 아웃바운드 호출 | 에 동기화된 CRM 활동(작업 또는 이벤트) 레코드 [!DNL Marketo Measure]에 대해 논리를 통해 [!UICONTROL Activities] 페이지 [!DNL Marketo Measure] |

터치 포인트 매핑 방법

터치 포인트 매핑 프로세스는 &quot;이 터치 포인트가 만들어지면, 어떻게 됩니까? [!DNL Marketo Measure] 어떤 채널과 하위 채널이 속해 있는지 알고 싶으십니까?&quot; 터치포인트 생성의 각 방법에는 터치 포인트 매핑의 자체 방법이 있습니다.

| **상호 작용 유형** | **생성 방법** | **매핑 방법** |
|---|---|---|
| 온라인, 사이트에서 | [!DNL Marketo Measure] JavaScript | 사용 [!DNL Online Channels] 페이지 [!DNL Marketo Measure]UTM 값, 랜딩 페이지 및 참조 페이지 정보를 참조하여 |
| 오프라인; 온라인, 사이트가 아님 | CRM 캠페인 멤버십 동기화 | 사용 [!UICONTROL Offline Channels] 페이지 [!DNL Marketo Measure], 캠페인 유형을 참조하여 |
| 영업 활동 | CRM 활동 동기화 | 사용 [!UICONTROL Online Channels] 페이지 [!DNL Marketo Measure]에 지정된 캠페인 이름을 참조하여 [!UICONTROL Activities] 페이지 |

>[!MORELIKETHIS]
>
>* [온라인 터치포인트를 [!DNL Marketo Measure] 채널/하위 채널](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [SFDC 내에서 CRM 캠페인 동기화](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [내에서 CRM 캠페인 동기화 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [CRM 캠페인을 [!DNL Marketo Measure] 채널/하위 채널](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [영업 활동에서 터치포인트 생성](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [활동 FAQ 및 활동 터치포인트를 채널/하위 채널에 매핑](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


