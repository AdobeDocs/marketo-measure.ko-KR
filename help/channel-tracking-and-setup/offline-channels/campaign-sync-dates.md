---
unique-page-id: 18874684
description: 캠페인 동기화 날짜 - [!DNL Marketo Measure] - 제품 설명서
title: 캠페인 동기화 날짜
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# 캠페인 동기화 날짜 {#campaign-sync-dates}

캠페인 동기화 날짜 기능의 기능을 알아보고 이 기능에 대한 일부 사용 사례를 제공합니다.

**[!DNL Marketo Measure]필요한 패키지: 6.9 이상**

이 기능은 [!DNL Salesforce] Campaign 개체:

* 터치 포인트 시작 날짜
* 터치 포인트 종료 날짜

구매자 터치포인트가 특정 캠페인에 활성화되면 캠페인 동기화 날짜를 통해 개별 캠페인에서 터치 포인트 날짜 매개 변수를 설정할 수 있습니다. 따라서 2017년 3월 1일의 터치포인트 종료 날짜를 추가하려면 [!DNL Marketo Measure] 은 해당 날짜 이전에 캠페인에 추가된 캠페인 구성원에 대해서만 터치포인트를 만듭니다. [!DNL Marketo Measure] 2017년 3월 1일 이후에 추가된 캠페인 구성원에 대한 터치포인트를 만들지 않습니다.

![](assets/1.gif)

마찬가지로, 캠페인(예: 2017년 1월 1일)에 터치포인트 시작 날짜를 추가하려 했다면 [!DNL Marketo Measure] 2017년 1월 1일 이전에 캠페인에 추가된 캠페인 구성원에 대해서는 터치포인트를 만들지 않습니다. 터치 포인트 종료 날짜를 추가할 경우 터치 포인트 시작 날짜를 추가할 필요가 없고 그 반대의 경우도 마찬가지입니다.

## 사용 사례 {#use-cases}

**터치포인트 다시 채우기**

마케팅 팀이 특정 마케팅 노력에 utm 매개 변수를 추가하지 않을 수 있는 경우가 있을 수 있습니다. 캠페인 동기화 날짜를 사용하면 일부 누락된 데이터를 (온라인 활동에 SFDC 캠페인을 사용하는 경우) 다시 채울 수 있습니다. 5월 1일부터 시작된 이메일 캠페인을 실행하고 있지만 팀이 5월 15일까지 해당 이메일 캠페인에 utm 매개 변수를 추가하지 않았다고 가정해 보겠습니다. SFDC Campaign을 통해 이메일 전환을 추적하는 경우, 해당 캠페인에 대해 5월 15일의 터치포인트 종료 날짜를 설정하고, 캠페인의 &#39;응답한&#39; 구성원에 대한 터치포인트를 활성화할 수 있습니다. 이 작업은 [!DNL Marketo Measure] 5월 15일까지 모든 응답에 대한 터치포인트를 만들려면

**소급 캠페인 멤버십 터치포인트**

새로운 사람이면 [!DNL Marketo Measure] 고객은 SFDC Campaign을 통해 추적한 마케팅 데이터 중 일부를 가져오는 데 관심이 있을 수 있습니다. 그러나 온라인 SFDC 캠페인에 터치포인트를 사용하려는 경우 다음 기간 동안 속성 이중 계산 문제를 해결할 수 있습니다 [!DNL Marketo Measure] 은 온라인 마케팅 활동을 위해 터치포인트를 자동으로 만듭니다. 데이터 두 번 카운팅을 방지하기 위해, 캠페인 터치포인트 종료 날짜를 사용하여 만든 터치 포인트 날짜에 제한을 설정할 수 있습니다. [!DNL Marketo Measure] ( SFDC 캠페인) 아래에 그룹화됩니다. 예를 들어, SFDC에서 추적한 소셜 캠페인에 대해 소급 전환을 추가하려 하지만, 다음을 추가했다는 것을 알고 있습니다 [!DNL Marketo Measure] 7월 1일(온라인 터치포인트를 만드는) JavaScript를 통해 7월 1일과 같은 터치포인트 종료 날짜를 포함하도록 Social SFDC 캠페인을 편집하고 해당 캠페인에 대해 Buyer Touchpoint를 활성화할 수 있습니다.

터치 포인트 종료 날짜에 대한 다른 사용 사례가 많이 있을 수 있습니다. 특정 상황을 파악하는 데 도움이 필요하면 주저하지 말고 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학: 캠페인 및 캠페인 구성원 필드](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
