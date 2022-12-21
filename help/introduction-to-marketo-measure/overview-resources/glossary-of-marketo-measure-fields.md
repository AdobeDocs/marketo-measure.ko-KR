---
unique-page-id: 18874586
description: Marketo 측정 단위 필드 용어집 - Marketo 측정 단위 - 제품 설명서
title: Marketo 측정 단위 필드 용어집
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
source-git-commit: 334dcd3dcbddacc4920d182d94908babd3cb8c89
workflow-type: tm+mt
source-wordcount: '3211'
ht-degree: 0%

---

# Marketo 측정 단위 필드 용어집 {#glossary-of-marketo-measure-fields}

이 문서에서는 Marketo Measurement 기본 패키지에서 Salesforce에 추가되는 모든 Marketo Measurement 필드에 대한 용어집을 제공합니다. 또한, 필드를 찾을 수 있는 개체 및 각 필드가 정보로 채워지는 방법에 대한 정보를 찾을 수 있습니다.

각 Marketo 측정 단위 필드가 관련된 맵의 경우 다음을 수행하십시오 [여기를 클릭하십시오.](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) ・ [B](#b) ・ [C](#c) ・ [D](#d) ・ [E](#e) ・ [F](#f) ・ [G](#g) ・ H ・ I ・ J ・ [K](#k) ・ [L](#l) ・ [M](#m) ・ N ・ [O](#o) ・ [P](#p) ・ 질문 ・ [R](#r) ・ [S](#s) ・ [T](#t) ・ [U](#u) ・ [V](#v) ・ W ・ X ・ Y ・ Z

## A {#a}

**계정** | Buyer Attribution Touchpoint에서 발견됨

이 필드는 BAT와 연결된 계정 이름으로 채워집니다.

**광고 캠페인 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint에서 발견됨

이 필드를 채울 수 있는 방법에는 세 가지가 있습니다.

`1)` 터치 포인트가 유료 검색 작업(AdWords 또는 BingAds)에서 발생하는 경우 광고 플랫폼의 광고 캠페인 ID가 여기에 표시됩니다.

`2)` 터치 포인트가 유료 검색에서 나오지 않았다면 랜딩 페이지 URL의 utm_campaign 값을 사용하여 필드가 채워집니다.

예 `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

이 예에서는 광고 캠페인 ID가 표시됩니다. __GAId__ 2014년 9월 마케팅 가상 이벤트

`3)` 터치포인트가 오프라인 Salesforce 캠페인(회의, 저녁 등)에서 가져오는 경우 광고 캠페인 Id는 Salesforce 캠페인 ID를 표시합니다

위의 필드가 없으면 이 필드는 비어 있습니다.

**광고 캠페인 이름** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색(AdWords/Bing Ads)에서 발생하면 광고 플랫폼의 광고 캠페인 이름이 여기에 표시됩니다.

`2)` 터치 포인트가 유료 검색에서 오지 않았고 랜딩 페이지 URL에 utm_campaign에 대한 값이 포함되어 있으면 해당 값이 여기에 채워집니다.

`3)` 터치포인트가 Salesforce 캠페인에서 발생하면 Salesforce 캠페인의 이름이 여기에 표시됩니다.

`4)` 이렇게 하면 Marketo 측정값 계정 내에 작성된 활동에서 생성된 터치포인트에 대해 정의된 캠페인 이름이 채워집니다.

위의 필드가 없으면 이 필드는 비어 있습니다.

**광고 캠페인 이름(FT)** | Buyer Touchpoint

이 필드는 광고 캠페인 이름과 동일한 방법으로 채워집니다. 하지만 이 필드는 첫 번째 터치 터치포인트를 생성한 광고 캠페인의 이름을 특히 보여줍니다.

**광고 캠페인 이름(LC)** | Buyer Touchpoint

이 필드는 광고 캠페인 이름과 동일한 방법으로 채워집니다. 하지만 이 필드는 특히 리드 생성 터치포인트를 생성한 광고 캠페인의 이름을 표시합니다.

**광고 컨텐츠** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색(AdWords/Bing Ads)에서 온 경우 필드에 광고 플랫폼의 전체 광고 사본이 표시됩니다.

`2)` 터치 포인트가 유료 검색에서 나오지 않으면 이 필드에 랜딩 페이지 URL의 utm_content 값이 표시됩니다.

`3)` 이렇게 하면 터치 포인트를 생성한 관련 활동의 제목 값으로 채워집니다.

위의 필드를 모두 기입하지 않은 경우 이 필드는 비어 있습니다.

**광고 대상 URL** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 오는 경우 이 필드에는 검색 엔진에서 광고를 클릭한 후 이동되는 URL 대상이 표시됩니다.

터치 포인트가 유료 검색에서 나오지 않으면 필드가 비어 있습니다.

**광고 그룹 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 나온 경우 AdWords/Bing 광고의 광고 그룹 ID가 여기에 표시됩니다.

터치 포인트가 유료 검색에서 오지 않으면 필드가 비어 있습니다.

**광고 그룹 이름** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 나온 경우 AdWords/Bing 광고의 광고 그룹 이름이 여기에 표시됩니다.

터치 포인트가 유료 검색에서 오지 않으면 필드가 비어 있습니다.

**광고 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 나온 경우 AdWords/Bing 광고의 광고 ID가 여기에 표시됩니다.

`2)` 터치 포인트가 CRM 활동에서 생성되는 경우 활동 외부 ID로 채워집니다.

터치 포인트가 유료 검색에서 오지 않으면 필드가 비어 있습니다.

**속성 % 사용자 지정 모델** | 구매자 기여도 분석 터치포인트

사용자 지정 속성 모델을 사용하는 경우, 이 필드에는 사용자 지정 모델에 설정된 값에 따라 터치포인트에 속하는 수입 비율이 표시됩니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**속성 % 첫 번째 터치** | 구매자 기여도 분석 터치포인트

이 필드는 첫 번째 터치 모델에 따라 터치 포인트에 속하는 수입 비율을 표시합니다.

**속성 % 전체** | 구매자 기여도 분석 터치포인트

이 필드는 전체 경로 모델에 따라 터치포인트에 속하는 매출액의 비율을 표시합니다.

**속성 % 리드 생성** | 구매자 기여도 분석 터치포인트

이 필드는 리드 생성 모델에 따라 터치포인트에 속하는 매출액의 비율을 표시합니다.

**속성 % U자형** | 구매자 기여도 분석 터치포인트

이 필드는 U자형 모델에 따라 터치포인트에 속하는 매출액의 비율을 표시합니다.

**속성 % W자형** | 구매자 기여도 분석 터치포인트

이 필드는 W자형 모델에 따라 터치포인트에 속하는 매출액의 비율을 표시합니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## B {#b}

**Marketo 측정 기회 금액** | Salesforce Opportunity

사용자 지정 금액 필드를 사용하여 Opportunity 수익을 보고하는 경우 Marketo Measurement에서 이러한 사용자 지정 금액 필드를 읽을 수 없습니다. Marketo 측정 기회 금액 은 Marketo Measurement가 Opportunity에서 사용자 정의 금액 필드를 읽을 수 있도록 하는 워크플로우를 만드는 데 사용되는 숨겨진 필드입니다.

**브라우저** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 웹 세션 중에 사용되는 웹 브라우저 유형(Chrome, Safari, Firefox 등)을 표시합니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## C {#c}

**연락처** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치 포인트가 속한 연락처 필드를 표시합니다.

**카운트 - 사용자 지정 모델** | 구매자 기여도 분석 터치포인트

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 값에 따라 터치포인트에 제공된 매출 크레딧의 백분율이 십진수 형태로 표시됩니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**카운트 - 사용자 지정 모델** | Buyer Touchpoint

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 값에 따라 터치포인트에 제공된 속성 크레딧의 백분율이 십진수 형태로 표시됩니다. 이 필드는 구매자 터치포인트 객체와 관련되므로 이것은 수익 크레딧의 반영이 아니며, 단순한 속성 크레딧입니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**카운트 - 첫 번째 터치** | 구매자 기여도 분석 터치포인트

이 필드는 첫 번째 터치 모델에 따라 터치 포인트에 제공된 매출 크레딧의 백분율을 십진수 형태로 보여줍니다.

**카운트 - 첫 번째 터치** | Buyer Touchpoint

이 필드는 첫 번째 터치 모델에 따라 터치 포인트에 제공된 속성 크레딧의 백분율을 십진수 형태로 보여줍니다. 터치 포인트가 첫 번째 터치인 경우 이 필드는 항상 1.0(100% 속성 크레딧을 나타남)입니다. 터치 포인트가 첫 번째 터치가 아닌 경우 이 필드는 항상 0(0% 속성 크레딧을 표시)입니다.

이 필드는 구매자 터치포인트 객체와 관련되므로 이것은 수익 크레딧의 반영이 아니며, 단순한 속성 크레딧입니다.

**개수 - 전체 경로** | 구매자 기여도 분석 터치포인트

이 필드는 전체 경로 모델에 따라 터치 포인트에 지정된 매출액의 백분율을 십진수 형태로 보여줍니다.

**카운트 - 리드 만들기 터치** | 구매자 기여도 분석 터치포인트

이 필드는 리드 생성 모델에 따라 터치포인트에 주어진 매출 크레딧의 백분율을 십진수 형태로 보여줍니다.

**카운트 - 리드 만들기 터치** | Buyer Touchpoint

이 필드는 리드 생성 모델에 따라 터치포인트에 제공된 속성 크레딧의 백분율을 십진수 형태로 표시합니다. 터치 포인트가 리드 생성 터치인 경우 이 필드는 항상 1.0(100% 속성 크레딧을 나타남)입니다. 터치 포인트가 리드 생성 터치가 아닌 경우 이 필드는 항상 0(0% 속성 크레딧을 표시)입니다.

이 필드는 구매자 터치포인트 객체와 관련되므로 이것은 수익 크레딧의 반영이 아니며, 단순한 속성 크레딧입니다.

**Count - U자형** | 구매자 기여도 분석 터치포인트

이 필드는 U자형 모델에 따라 터치포인트에 주어진 매출 크레딧의 백분율을 십진수 형식으로 표시합니다.

**Count - U자형** | Buyer Touchpoint

이 필드는 U자형 모델에 따라 터치포인트에 제공된 속성 크레딧의 백분율을 십진수 형태로 표시합니다. U자형 모델에서는 크레딧이 첫 번째 터치, 리드 생성 터치 및 첫 번째 터치 및 리드 생성 터치 사이에 발생한 중간 양식 제출 간에 나눠집니다.

이 필드는 구매자 터치포인트 객체와 관련되므로 이것은 수익 크레딧의 반영이 아니며, 단순한 속성 크레딧입니다.

**카운트 - W자형** | 구매자 기여도 분석 터치포인트

이 필드는 W자형 모델에 따라 터치 포인트에 제공된 크레딧의 백분율을 십진수 형태로 표시합니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## D {#d}

보고된 날짜 | Marketo Measure ABTest, Marketo 측정 이벤트

Marketo 측정 이벤트 - 사용자가 웹 사이트에서 특정 작업을 수행하여 이벤트를 활성화한 날짜입니다

Marketo 측정 ABTest - 사용자가 웹 사이트에서 A/B 테스트에 참여한 날짜입니다

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## E {#e}

**이벤트 이름** | Marketo 측정 이벤트

이 필드에는 이벤트를 트리거한 작업 이름(즉, 페이지 보기)이 표시됩니다.

**이벤트 값** | Marketo 측정 이벤트

이벤트에 대한 설명(즉, 홈 페이지)

**실험 이름** | Marketo 측정 ABTest

이 필드에는 실험 이름(예: 평가판 단추)이 표시됩니다

**실험 ID** |Marketo 측정 AB 테스트

각 실험에 대한 고유 식별 코드

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## F {#f}

양식 URL | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 양식 채우기가 발생한 페이지 URL의 단축된 버전이 표시됩니다(UTM 매개 변수 없음)

양식 URL - 원시 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 UTM 매개 변수를 포함하여 양식 채우기가 발생한 전체 페이지 URL이 표시됩니다

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## G {#g}

지역 도시 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 리드/연락처가 웹 사이트를 방문한 도시의 이름을 표시합니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

지역 국가 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 리드/연락처가 웹 사이트를 방문한 국가를 표시합니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

지역 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 리드/연락처가 웹 사이트를 방문한 지역 또는 상태가 표시됩니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## 천 {#k}

**키워드 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치 포인트가 유료 검색에서 오는 경우 이 필드에는 광고 플랫폼(Adwords/BingAds)의 키워드 ID가 표시됩니다.

이 터치포인트가 유료 검색에서 오지 않은 경우 이 필드는 비어 있습니다.

**키워드 일치 유형** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치 포인트가 유료 검색에서 오는 경우 이 필드에는 광고 플랫폼(Adwords/Bing)의 일치 유형이 표시됩니다.

**키워드 텍스트** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 오는 경우 이 필드는 광고 플랫폼의 키워드 텍스트(Adwords/BingAds)나 랜딩 페이지 URL에 있는 _bk 매개 변수의 값을 표시합니다.

예 `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` 터치 포인트가 유료 검색에서 나오지 않으면 이 필드에 랜딩 페이지 URL의 utm_term 값이 표시됩니다.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

터치 포인트가 유료 검색에서 오지 않았거나 utm_term 값이 없는 경우 이 필드는 비어 있습니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## L {#l}

**랜딩 페이지** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 웹 세션 중에 방문한 첫 번째 웹 페이지의 URL(UTM 매개 변수 없음)의 단축된 버전이 표시됩니다.

**랜딩 페이지 - 원시** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 웹 세션 중에 방문한 첫 번째 웹 페이지의 전체 URL(UTM 매개 변수 포함)을 표시합니다.

**리드** | Buyer Touchpoint, Marketo Measure Person

이 필드에는 터치 포인트가 속한 리드의 이름이 표시됩니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## 백만 {#m}

**마케팅 채널** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 터치포인트가 속한 마케팅 활동 또는 마케팅 채널의 일반 그룹(즉, 유료 검색, 직접, 소셜 등)을 보여줍니다. 터치포인트는 Marketo 측정 앱에서 채널이 설정된 방식에 따라 그룹화됩니다. 마케팅 채널 또는 채널 설정 방법에 대한 자세한 내용은 다음을 참조하십시오 [여기를 클릭하십시오.](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**마케팅 채널 - 경로** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 마케팅 채널과 터치 포인트가 속한 하위 채널이 표시됩니다. 아래 예에서 마케팅 채널 - 경로는 Social.Linkedin입니다. 여기서 마케팅 채널은 Social이고 하위 채널은 LinkedIn입니다.

![](assets/1-3.png)

**Medium** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 오는 경우 Adwords/BingAds의 미디어가 여기에 표시됩니다(예: CPC).

`2)` 터치 포인트가 유료 검색에서 오지 않으면 이 필드에 랜딩 페이지 URL의 utm_medium 값이 표시됩니다.

`3)` 터치 포인트가 오프라인 캠페인에서 발생하면 이 필드에 Salesforce 캠페인에 &#39;Type&#39; 필드가 표시됩니다.

`4)` 이 경우 터치 포인트를 생성한 관련 활동의 활동 유형 값으로 채워집니다.

위의 값이 없는 경우 Marketo Measurement는 자동으로 중간 값을 설정합니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

O

**기회** | 구매자 기여도 분석 터치포인트

이 필드에는 BAT가 속한 기회가 표시됩니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

P

**플랫폼** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 컴퓨터 또는 전화의 유형과 웹 세션 중에 사용된 운영 체제의 유형이 표시됩니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

R

**레퍼러 페이지** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 Lead/Contact 가 웹 사이트로 안내한 마지막 웹 페이지의 URL(UTM 매개 변수 없음)이 표시됩니다.

For example:

- 터치 포인트가 유료/유기 검색에서 나온 경우 필드에 검색 엔진의 URL이 표시됩니다

- 터치포인트가 Social에서 온 경우 필드에 소셜 웹 사이트의 URL(즉, LinkedIn)이 표시됩니다

**레퍼러 페이지 - 원시** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 전체 참조 URL(UTM 매개 변수 포함)을 표시한다는 점을 제외하면 레퍼러 페이지와 동일한 정보를 표시합니다.

**매출 - 사용자 지정 모델** | 구매자 기여도 분석 터치포인트

사용자 지정 속성 모델을 사용하는 경우 이 필드는 사용자 지정 모델에 설정된 속성 비율에 따라 터치포인트에 속하는 달러 매출 금액을 표시합니다.

사용자 지정 모델을 사용하지 않는 경우 달러 금액은 0이 됩니다.

**매출 - 첫 번째 터치** | 구매자 기여도 분석 터치포인트

이 필드는 첫 번째 터치 모델의 속성 비율에 따라 터치 포인트에 속하는 달러 매출 금액을 표시합니다.

**매출 - 전체 경로** | 구매자 기여도 분석 터치포인트

이 필드는 전체 경로 모델의 속성 비율에 따라 터치포인트에 속하는 달러 매출 금액을 표시합니다.

**매출 - 리드 생성 터치** | 구매자 기여도 분석 터치포인트

이 필드는 리드 생성 모델의 속성 비율에 따라 터치포인트에 속하는 달러 매출 금액을 표시합니다.

**매출 - U자형** | 구매자 기여도 분석 터치포인트

이 필드는 U자형 모델의 속성 비율에 따라 터치포인트에 속하는 달러 매출 금액을 표시합니다.

**매출 - W자형** | 구매자 기여도 분석 터치포인트

이 필드는 W자형 모델의 속성 비율에 따라 터치포인트에 속하는 달러 매출 금액을 표시합니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

S

**Salesforce 캠페인** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 터치 포인트가 속한 Salesforce 캠페인이 표시됩니다.

**검색 구** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치 포인트가 유료 검색이나 유기 검색에서 온 경우 이 필드에는 검색 엔진에 입력된 검색 구문이 표시됩니다. 그러나 개인 정보 보호 때문에 일반적으로 이 정보를 사용할 수 없습니다.

**세그먼트** | 구매자 기여도 분석 터치포인트

이 필드에는 터치 포인트가 속한 세그먼트가 표시됩니다. 이는 Marketo 측정 앱에서 세그먼테이션 규칙을 구성한 방법에 따라 다릅니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

T

**터치 포인트 날짜** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 온라인 소스에서 온 경우 이 필드에 터치 포인트가 발생한 날짜 및 시간이 표시됩니다.

`2)` 터치 포인트가 오프라인 이벤트에서 온 경우 이 필드는 Salesforce 캠페인이나 캠페인 동기화 규칙에서 선택한 날짜 필드에 설정된 날짜 및 시간을 표시합니다.

`3)` 터치포인트가 활동에서 나온 경우 이 필드에는 활동 규칙에서 터치포인트 날짜로 선택한 필드의 날짜 및 시간이 표시됩니다.

**터치 포인트 날짜(FT)** | Buyer Touchpoint

이 필드는 터치 포인트 날짜와 동일한 필드이지만 이 필드는 첫 번째 터치 터치 터치 터치 터치 접점이 발생한 날짜 및 시간을 특별히 표시합니다.

**터치 포인트 날짜(LC)** | Buyer Touchpoint

이 필드는 터치 포인트 날짜와 동일한 필드이지만 이 필드는 리드 생성 터치포인트가 발생한 날짜 및 시간을 특별히 표시합니다.

**터치 포인트 위치** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 터치 포인트의 위치를 표시합니다. 터치포인트의 위치는 고객 여정(즉, FT, 양식, LC, OC, Closed)의 주요 이정표 터치포인트를 반영합니다. 터치포인트의 위치는 고객 여정에서 발생한 시기에 따라 다르며, 단일 터치포인트는 두 개 이상의 위치를 가질 수 있습니다. 다양한 터치 포인트 위치는 다음과 같습니다.

첫 번째 터치(FT) - 누군가 자신의 브랜드와 가지고 있는 첫 번째 마케팅 상호 작용

리드 생성(LC) - 가장 먼저 알려진 마케팅 상호 작용(일반적으로 양식 제출 또는 Salesforce 캠페인 포함)

양식 - 방문자가 온라인 양식을 채울 때

기회 생성(OC) - Opp 생성 시 가장 가까운 마케팅 상호 작용

닫힘 - Opp가 닫힐 때(원 또는 손실) 가장 가까운 마케팅 상호 작용

**터치 포인트 소스** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치 포인트가 유료 검색에서 나온 경우 이 필드에 광고 플랫폼의 이름(AdWords/BingAds)이 표시됩니다

`2)` 터치 포인트가 유기 검색에서 나온 경우 이 필드에 검색 엔진의 이름이 표시됩니다

`3)` #1 또는 #2가 없고 utm_source 값이 터치포인트의 랜딩 페이지 URL에 있는 경우 해당 값이 여기에 표시됩니다

`4)` 터치포인트가 CRM 캠페인에서 생성되는 경우 이 이벤트가 CRM 캠페인으로 채워집니다.

`5)` 터치포인트가 CRM 활동에서 생성되는 경우 이 활동이 CRM 활동으로 채워집니다.

위의 필드가 없으면 이 필드가 &#39;Web Direct&#39; 또는 &#39;Web&#39;으로 채워집니다.

**터치 포인트 소스(FT)** | Buyer Touchpoint

이 필드는 터치 포인트 소스와 동일한 필드이지만 이 필드는 첫 번째 터치 터치 터치 터치 포인트의 소스를 특별히 표시합니다.

**터치 포인트 소스(LC)** | Buyer Touchpoint

이 필드는 터치 포인트 소스와 동일한 필드이지만, 이 필드에는 특별히 리드 생성 터치포인트의 소스가 표시됩니다.

**터치 포인트 유형** | Buyer Touchpoint 및 Buyer Attribution Touchpoint에서 발견됩니다.

이 필드에는 터치 포인트의 상호 작용 유형이 표시됩니다. 다음과 같이 표시됩니다. JavaScript 터치포인트에 대한 웹 방문, 웹 양식 또는 웹 채팅. CRM Campaign 터치포인트의 경우, CRM으로 표시됩니다. 활동 터치포인트에 대한 작업 또는 이벤트 유형으로 채워집니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

U

**UniqueId** | Buyer Touchpoint, Buyer Attribution Touchpoint

각 터치 포인트에 연결된 고유 ID입니다

**사용자 ID** | Marketo 측정 ABTest

각 사용에 대한 최적화의 고유 식별 코드

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)

## V {#v}

**변형** | Marketo 측정 ABTest

A/B 테스트의 변형 이름

**변형 ID** | Marketo 측정 ABTest

각 A/B 테스트 변형에 대한 고유한 식별 코드입니다.

[페이지 맨 위로 돌아가려면 여기를 클릭하십시오.](#top)
