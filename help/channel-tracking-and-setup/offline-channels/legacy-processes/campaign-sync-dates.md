---
description: Marketo Measure 사용자를 위한 Campaign 동기화 날짜 지침
title: Campaign 동기화 날짜
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Campaign 동기화 날짜 {#campaign-sync-dates}

Campaign 동기화 날짜 기능이 수행하는 작업을 알아보고 이 기능에 대한 사용 사례를 제공합니다.

>[!NOTE]
>
>이 문서에서는 오래된 프로세스를 다룹니다. 사용자가 [새롭고 개선된 인앱 프로세스](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}를 사용하는 것이 좋습니다.

**[!DNL Marketo Measure]패키지 필요: 6.9 이상**

이 기능은 [!DNL Salesforce] Campaign 개체에 있는 두 개의 간단한 날짜 필드로 구성됩니다.

* 접점 시작일
* 접점 종료 날짜

특정 캠페인에서 구매자 터치포인트를 활성화하면 캠페인 동기화 날짜를 사용하여 개별 캠페인에서 터치포인트 날짜 매개 변수를 설정할 수 있습니다. 따라서 터치포인트 종료 날짜를 2017년 3월 1일로 추가하는 경우 [!DNL Marketo Measure]은(는) 해당 날짜 이전에 캠페인에 추가된 캠페인 멤버에만 터치포인트를 만듭니다. [!DNL Marketo Measure]은(는) 2017년 3월 1일 이후에 추가된 캠페인 멤버에 대한 터치포인트를 만들지 않습니다.

![](assets/legacy-processes-3.gif)

마찬가지로, 캠페인에 터치포인트 시작 날짜를 추가하는 경우(2017년 1월 1일) [!DNL Marketo Measure]은(는) 2017년 1월 1일 이전에 캠페인에 추가된 캠페인 멤버에 터치포인트를 만들지 않습니다. 접점 종료 날짜를 추가하거나 그 반대로 터치포인트 시작 날짜를 추가할 필요가 없습니다.

## 사용 사례 {#use-cases}

**다시 채우기 터치포인트**

마케팅 팀이 특정 마케팅 활동에 utm 매개 변수를 추가하지 못할 수 있습니다. 캠페인 동기화 날짜를 사용하면 (온라인 활동에 SFDC 캠페인을 사용하는 경우) 누락된 데이터를 다시 채울 수 있습니다. 5월 1일에 시작된 이메일 캠페인을 실행 중이지만 팀이 5월 15일까지 해당 이메일 캠페인에 utm 매개 변수를 추가하지 않았다고 가정해 보겠습니다. SFDC Campaign을 통해 이메일 전환을 추적하는 경우, 해당 캠페인에 대한 터치포인트 종료 날짜를 5월 15일로 설정하고 캠페인의 &#39;응답된&#39; 멤버에 대한 터치포인트를 활성화할 수 있습니다. 이 작업은 [!DNL Marketo Measure]에게 5월 15일까지 해당 모든 응답에 대한 터치포인트를 만들도록 지시합니다.

**소급 캠페인 멤버십 터치포인트**

새 [!DNL Marketo Measure] 고객인 경우 SFDC 캠페인을 통해 추적한 마케팅 데이터를 가져오는 데 관심이 있을 수 있습니다. 그러나 온라인 SFDC 캠페인에 터치포인트를 활성화하려면 [!DNL Marketo Measure]에서 온라인 마케팅 활동에 대한 터치포인트를 자동으로 만들기 때문에 속성 이중 계산 문제가 발생할 수 있습니다. 데이터를 두 번 계산하지 않도록 하기 위해 캠페인 접점 종료 날짜를 사용하여 SFDC 캠페인에서 [!DNL Marketo Measure]이(가) 만든 접점 날짜에 대한 제한을 설정할 수 있습니다. 예를 들어, SFDC에서 추적한 Social Campaign에 대해 소급 전환을 추가하려 하지만 7월 1일에 [!DNL Marketo Measure] JavaScript(온라인 터치포인트를 만드는 중)를 추가했음을 알고 있는 경우, 7월 1일과 동일한 터치포인트 종료 날짜를 포함하도록 Social SFDC 캠페인을 편집하고 해당 캠페인에 대한 구매자 터치포인트를 활성화할 수 있습니다.

터치포인트 종료 날짜에 대한 다른 사용 사례가 많을 수 있습니다. 특정 상황을 파악하는 데 도움이 필요하면 언제든지 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하십시오.
