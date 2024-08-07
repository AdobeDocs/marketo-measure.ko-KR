---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] 매개 변수 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 매개 변수"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# [!DNL Marketo Measure] 매개 변수 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 매개 변수 설명 {#marketo-measure-parameters-explained}

UTM을 사용하여 더 많은 통찰력을 얻기 위해 [!DNL Marketo Measure]은(는) [!DNL Google] AdWords, Bing Ads 및 [!DNL Facebook] Ads의 광고에 사용자 지정 매개 변수를 추가합니다. [!DNL Marketo Measure]은(는) 이러한 플랫폼과 통합되어 대부분의 설정 프로세스를 자동화합니다. 자동 태그 지정을 사용하도록 선택하면 [!DNL Marketo Measure]이(가) 광고 URL에 매개 변수를 자동으로 추가합니다. [!DNL Marketo Measure]은(는) 플랫폼에서 마케팅 비용을 자동으로 다운로드하고 [!DNL Marketo Measure] 앱에 로드합니다.

매개 변수가 없는 URL의 예:

`http://adobe.com/landing-page?myParam=foo`

[!DNL Marketo Measure] 매개 변수가 있는 URL의 예:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords 매개변수 {#adwords-parameters}

* `_bk={keyword}`
   * 검색 엔진에서 개인이 사용한 키워드를 나타냅니다.
   * 이는 UTM 용어 매개 변수와 유사합니다.

* `_bt={creative}`
   * 크리에이티브 ID 또는 이름을 나타냅니다.
   * 이는 UTM 콘텐츠 매개 변수와 유사합니다.

* `_bm={matchtype}`
   * 키워드가 얼마나 가깝게 일치했는지 나타냅니다.
   * 키워드 일치 유형은 광고를 트리거하는 검색을 제어하는 데 도움이 됩니다. 예를 들어 광범위한 일치 를 사용하여 광고를 광범위한 대상자에게 표시하거나 정확한 일치 를 사용하여 특정 고객 그룹에 대해 경고할 수 있습니다.
   * 세 가지 일치 유형은 넓음, 흐릿함 및 정확함입니다.

>[!TIP]
>
>일치 유형에 대한 자세한 내용은 [관련 AdWords 문서를 참조하십시오](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * 광고 네트워크 유형([디스플레이 또는 검색](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"})을 나타냅니다.
   * 이는 UTM Source 매개 변수와 유사합니다.

* `_bg={adgroupID}`
   * 광고가 속한 광고 그룹의 ID를 나타냅니다

>[!NOTE]
>
>리디렉션 URL 매개 변수는 지원되지 않습니다.

## Bing Ads 매개 변수 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook 매개 변수 {#facebook-parameters}

* `_bf ={creative}`
   * 크리에이티브 ID 또는 이름을 나타냅니다
