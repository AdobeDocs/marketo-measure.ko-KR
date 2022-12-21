---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] 매개 변수 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 매개 변수"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# [!DNL Marketo Measure] 매개 변수 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 매개 변수 설명 {#marketo-measure-parameters-explained}

UTM을 사용하여 보다 자세한 통찰력을 얻으려면 [!DNL Marketo Measure] 의 광고에 사용자 지정 매개 변수를 추가합니다. [!DNL Google] AdWords, Bing Ads 및 [!DNL Facebook] 광고. [!DNL Marketo Measure] 이러한 플랫폼과 통합되어 대부분의 설정 프로세스를 자동화합니다. 자동 태깅을 사용하도록 선택하면, [!DNL Marketo Measure] 은 자동으로 해당 매개 변수를 광고 URL에 추가합니다. [!DNL Marketo Measure] 또한 플랫폼에서 마케팅 비용을 자동으로 다운로드하여 [!DNL Marketo Measure] 앱.

매개 변수가 없는 URL의 예:

`http://adobe.com/landing-page?myParam=foo`

를 사용하는 URL의 예 [!DNL Marketo Measure] 매개 변수:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords 매개 변수 {#adwords-parameters}

* `_bk={keyword}`
   * 검색 엔진에서 사용되는 사람이 사용하는 키워드를 나타냅니다.
   * UTM 용어 매개 변수와 비슷합니다.

* `_bt={creative}`
   * 광고 ID 또는 이름을 나타냅니다.
   * UTM 컨텐츠 매개 변수와 유사합니다.

* `_bm={matchtype}`
   * 키워드와 일치하는 정도를 나타냅니다.
   * 키워드 일치 유형은 광고를 트리거하는 검색을 제어하는 데 도움이 됩니다. 예를 들어 광범위한 일치 기능을 사용하여 광범위한 대상에게 광고를 표시하거나 특정 고객 그룹에서 연결하는 데 정확한 일치 기능을 사용할 수 있습니다.
   * 세 가지 일치 유형은 다음과 같습니다. 광범위하고 퍼지있고 정확합니다.

>[!NOTE]
>
>일치 유형에 대한 자세한 내용은 [관련 AdWords 문서](https://support.google.com/adwords/answer/2497836?hl=en){target=&quot;_blank&quot;}.

* `_bn={network}`
   * 광고 네트워크 유형을 나타냅니다. [표시 또는 검색](https://support.google.com/adwords/answer/1752334?hl=en){target=&quot;_blank&quot;}.
   * 이는 UTM 소스 매개 변수와 유사합니다.

* `_bg={adgroupID}`
   * 광고가 속하는 광고 그룹의 ID를 나타냅니다

## Bing 광고 매개 변수 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook 매개 변수 {#facebook-parameters}

* `_bf ={creative}`
   * 광고 ID 또는 이름을 나타냅니다
