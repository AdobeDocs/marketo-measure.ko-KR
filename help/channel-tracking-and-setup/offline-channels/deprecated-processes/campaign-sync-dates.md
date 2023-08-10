---
unique-page-id: 18874684
description: Campaign 동기화 날짜 - [!DNL Marketo Measure] - 제품 설명서
title: Campaign 동기화 날짜
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 31ffb58f5318b71d478056f9b914eb1d42c7719a
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Campaign 동기화 날짜 {#campaign-sync-dates}

Campaign 동기화 날짜 기능이 수행하는 작업을 알아보고 이 기능에 대한 사용 사례를 제공합니다.

**[!DNL Marketo Measure]패키지 필요: 6.9 이상**

이 기능은 의 두 단순 날짜 필드로 구성됩니다. [!DNL Salesforce] Campaign 개체:

* 접점 시작일
* 접점 종료 날짜

특정 캠페인에서 구매자 터치포인트를 활성화하면 캠페인 동기화 날짜를 사용하여 개별 캠페인에서 터치포인트 날짜 매개 변수를 설정할 수 있습니다. 따라서 터치포인트 종료 날짜를 2017년 3월 1일로 추가하는 경우 [!DNL Marketo Measure] 은 해당 날짜 이전에 Campaign에 추가된 캠페인 멤버에만 터치포인트를 만듭니다. [!DNL Marketo Measure] 은 2017년 3월 1일 이후에 추가된 캠페인 멤버에 대한 터치포인트를 만들지 않습니다.

![](assets/1.gif)

마찬가지로 캠페인(2017년 1월 1일)에 터치포인트 시작 날짜를 추가하는 경우 [!DNL Marketo Measure] 은 2017년 1월 1일 이전에 Campaign에 추가된 캠페인 멤버에게 터치포인트를 생성하지 않습니다. 접점 종료 날짜를 추가하거나 그 반대로 터치포인트 시작 날짜를 추가할 필요가 없습니다.

## 사용 사례 {#use-cases}

**다시 채우기 터치포인트**

마케팅 팀이 특정 마케팅 활동에 utm 매개 변수를 추가하지 못할 수 있습니다. 캠페인 동기화 날짜를 사용하면 (온라인 작업에 SFDC 캠페인을 사용하는 경우) 누락된 데이터를 다시 채울 수 있습니다. 5월 1일에 시작된 이메일 캠페인을 실행 중이지만 팀이 5월 15일까지 해당 이메일 캠페인에 utm 매개 변수를 추가하지 않았다고 가정해 보겠습니다. SFDC Campaign을 통해 이메일 전환을 추적하는 경우 해당 캠페인에 대한 터치포인트 종료 날짜를 5월 15일로 설정하고 캠페인의 &#39;응답됨&#39; 멤버에 대한 터치포인트를 활성화할 수 있습니다. 이 작업을 수행하면 다음이 표시됩니다. [!DNL Marketo Measure] 5월 15일까지의 모든 응답에 대한 터치포인트를 만들려면.

**소급 캠페인 멤버십 접점**

새 사람인 경우 [!DNL Marketo Measure] 고객: SFDC 캠페인을 통해 추적한 마케팅 데이터 중 일부를 가져오는 데 관심이 있을 수 있습니다. 그러나 온라인 SFDC 캠페인에 터치포인트를 활성화해야 하는 경우 이후 이중 계산 속성 문제가 발생할 수 있습니다. [!DNL Marketo Measure] 은 온라인 마케팅 활동에 대한 터치포인트를 자동으로 생성합니다. 데이터를 두 번 카운트하지 않도록 하기 위해 캠페인 접점 종료 날짜 를 사용하여 만든 접점 날짜에 대한 제한을 설정할 수 있습니다. [!DNL Marketo Measure] SFDC 캠페인에 사용할 수 있습니다. 예를 들어, Social Campaign에 대한 소급 전환을 추가하려는 경우 SFDC에서 추적해 왔지만, 다음을 추가했음을 알고 있습니다. [!DNL Marketo Measure] 7월 1일에 JavaScript(온라인 터치포인트를 생성 중)를 사용하면 7월 1일과 동일한 터치포인트 종료 날짜를 포함하도록 Social SFDC 캠페인을 편집하고 해당 캠페인에 대한 구매자 터치포인트를 활성화할 수 있습니다.

터치포인트 종료 날짜에 대한 다른 사용 사례가 많을 수 있습니다. 특정 상황을 파악하는 데 도움이 필요하면 언제든지 연락하십시오. [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학: Campaign 및 Campaign 멤버 필드](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
