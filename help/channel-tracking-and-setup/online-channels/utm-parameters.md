---
unique-page-id: 18874606
description: UTM 매개 변수 - [!DNL Marketo Measure] - 제품 설명서
title: UTM 매개 변수
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# UTM 매개 변수 {#utm-parameters}

URL 태깅은 디지털 마케팅 활동에 대한 데이터를 캡처하는 간단하고 효과적인 방법입니다. 데이터를 수집하고 기록하는 URL 끝에 매개 변수를 추가하는 프로세스입니다. 가장 일반적으로 사용되는 매개 변수는 Google에서 지원하는 UTM(Urchin Tracking Module)입니다. 사용할 수 있는 기본 UTM 매개 변수는 5개입니다. 미디어, 소스, 캠페인, 컨텐츠 및 용어. 이러한 내용은 다음 섹션에서 자세히 설명합니다.

UTM 매개 변수는 URL에 수동으로 추가하거나 예를 들어 AdWords와 같은 특정 플랫폼과 함께 자동 태깅을 통해 추가할 수 있습니다. 자동 태깅은 URL에 매개 변수를 추가하는 프로세스를 자동화합니다. 다음 옵션을 사용할 수도 있습니다 [URL 빌더](https://ga-dev-tools.appspot.com/campaign-url-builder/){target=&quot;_blank&quot;} 를 사용하여 수동으로 URL 태깅 속도를 높일 수 있습니다. URL 빌더를 사용하면 각 매개 변수에 사용할 값을 지정해야 하며 빌더에 URL 형식이 지정됩니다.

## UTM 매개 변수란 무엇입니까? {#what-are-utm-parameters}

UTM 매개 변수의 작동 방식을 이해하려면 UTM이 없는 일반적인 URL을 살펴보겠습니다.

`http://www.adobe.com`

이제 UTM이 있는 URL을 확인하겠습니다.

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

보시다시피 두 번째 링크에 더 많은 텍스트가 포함되어 있습니다. UTM 매개 변수는 항상 최상위 도메인( 이 예에서 .com) 뒤에 이동한 다음 물음표로 시작합니다. 그런 다음 매개 변수의 순서는 문제가 되지 않지만 일관된 명명 규칙을 따르는 것이 좋습니다. 각 UTM을 구분하려면 각 매개 변수 사이에 앰퍼샌드를 배치해야 합니다. 이제 각 매개 변수가 나타내는 사항에 대해 자세히 살펴보겠습니다.

알아보기 [utm 매개 변수 설정에 대한 우수 사례](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* 매체 는 회사를 마케팅하는 데 사용하는 차량을 식별합니다.
* 그것은 질문에 답합니다. &quot;그들은 당신에게 어떻게 다가가고 있습니까?&quot;
* 최상위 채널을 나타냅니다.
* 소셜 미디어, 이메일, 유기 검색 및 유료 검색은 모두 잠재적 미디어 값의 예입니다.
* 이 매개 변수는 데이터를 [!DNL Marketo Measure] &#39;Medium&#39; 필드.
* _[!DNL Marketo Measure]우수 사례:_ 이 필드를 사용하여 하위 채널을 호출하지 마십시오. 그렇지 않으면 실제 채널에 대한 보고서를 생성하지 못할 수 있습니다. 마케팅 차량 또는 채널을 식별하는 데 사용합니다. 예를 들어 이메일을 사용하여 제품을 마케팅하려면 매체가 이메일입니다.

**utm_source**

* 소스는 트래픽의 소스인 하위 채널을 식별합니다.
* 그것은 질문에 답합니다. &quot;이 사람은 어디서 온 걸까요?&quot;
* 소셜 미디어 예에서 트래픽 소스는 사용 중인 소셜 미디어 플랫폼입니다.
   * 이 예제에서는 [!DNL Facebook] 은 소스 값입니다. twitter 및 Instagram이 그 예입니다. UTM 미디어가 [!DNL Paid Search]반면에 UTM 소스는 AdWords 또는 BingAds일 수 있습니다.

* 이 매개 변수는 [!DNL Marketo Measure] SFDC의 &#39;터치 포인트 소스&#39; 필드입니다.
* _[!DNL Marketo Measure]우수 사례:_ 이 매개 변수는 트래픽 소스를 추적하므로 광고 유형(예: 재타겟팅, 스폰서 등)을 나타내는 데 사용하기에는 적합하지 않습니다. 높은 수준의 하위 채널을 추적하는 데 가장 잘 사용됩니다. 기억하십시오, 당신은 &quot;내 교통은 어디에서 오는 것입니까?&quot;라는 질문에 답하고 있습니다. 레퍼러를 찾고 있습니다. 이 예에서 UTM 소스는 광고가 있는 곳(실제 웹 페이지가 아니라 태그 외부에서 자동으로 추적됨)입니다. 드립 이메일 캠페인을 추적하는 경우 드립 이메일이 소스입니다.

**utm_campaign**

* 캠페인은 특정 마케팅 캠페인을 식별하는 데 사용됩니다.
* 그것은 질문에 답합니다. &quot;왜 그들이 당신에게 오나요?&quot;
* 이 태그를 사용하여에 있는 광고 캠페인의 이름을 나타냅니다 [!DNL Google AdWords] 또는 [!DNL BingAds]또는 캠페인을 내부적으로 식별하는 이름을 지정합니다. 이 태그를 사용하여 지리적 위치나 광고 네트워크 유형과 같은 다른 정보를 지정할 수도 있습니다.
* 이 매개 변수는 [!DNL Marketo Measure] SFDC의 &#39;광고 캠페인 이름 필드&#39;
* _[!DNL Marketo Measure]우수 사례_: 캠페인 이름을 결정할 때 구두점 또는 단어 사이에 빈 공백을 사용하지 마십시오. 구두점 표시를 사용하면 브라우저 인코딩 오류가 발생할 수 있습니다. 최상의 결과를 얻으려면 밑줄을 대신 사용하십시오.

**utm_content**

* 단일 웹 페이지에 있는 두 개 이상의 마케팅 조각을 추적하려면 UTM 컨텐츠 매개 변수를 사용하십시오. 예를 들어 &quot;데모 요청&quot; 단추와 &quot;주별 뉴스레터 등록&quot; 단추가 있고, 가장 많은 트래픽을 생성하는 사용자를 알고 싶다면 각 사이트의 이름을 지정하고 UTM 컨텐츠 태그를 사용하여 추적합니다. 각 &quot;컨텐츠&quot;의 이름은 태그의 값입니다.
* 이 매개 변수는 [!DNL Marketo Measure] SFDC의 &#39;광고 컨텐츠&#39; 필드입니다.
* _[!DNL Marketo Measure]우수 사례_: 선택적인 값이지만 [!DNL Marketo Measure] 권장 사항. 이 태그는 추적하려는 광고 또는 마케팅 부분의 제목과 연결됩니다. 이미지 광고를 사용하는 경우 제목에 이미지 크기를 작성해야 합니다.

**utm_term**

* 용어는 UTM 컨텐츠 매개 변수와 유사합니다. 용어는 유료 캠페인에 대한 광고에서 키워드를 식별하는 데 유용합니다. 자동 태깅 기능을 사용하는 경우 자동으로 수행됩니다. 광고 플랫폼의 자동 태그 지정 기능을 사용하지 않는 경우 추적할 모든 키워드를 신중하게 추가해야 합니다.
* 이 매개 변수는 [!DNL Marketo Measure] SFDC의 &#39;키워드 텍스트&#39; 필드입니다.
* _[!DNL Marketo Measure]우수 사례_: UTM 용어 태그는 선택 사항이지만 키워드를 추적하는 데 유용합니다. 철자를 다시 확인하고 특수 문자를 사용하지 마십시오. 두 개 이상의 단어가 필요한 경우 밑줄을 사용하거나 공백을 전혀 사용하지 마십시오.

각 매개 변수는 지정된 값과 관련된 정보를 수집합니다. 각 태그의 값을 사용하면 모든 디지털 캠페인을 추적 및 정렬하고 질문에 답변할 수 있습니다. 어디, 어떻게, 왜?

다음은 UTM 매개 변수의 차트입니다 [!DNL Marketo Measure] 구문 분석 및 연결된 해당 터치 포인트 필드:

| **UTM 매개 변수** | **해당 [!DNL Marketo Measure] 필드** |
|---|---|
| utm_medium | 미디엄 |
| utm_source | 터치 포인트 소스 |
| utm_campaign | 광고 캠페인 이름 |
| utm_content | 광고 컨텐츠 |
| utm_term | 키워드 텍스트 |
