---
unique-page-id: 18874586
description: Marketo Measure 필드 용어집 - Marketo Measure - 제품 설명서
title: Marketo Measure 필드 용어집
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '3213'
ht-degree: 0%

---

# Marketo Measure 필드 용어집 {#glossary-of-marketo-measure-fields}

이 문서에서는 Marketo Measure 기본 패키지에서 Salesforce에 추가된 모든 Marketo Measure 필드의 용어집을 제공합니다. 또한 필드를 찾을 수 있는 개체 및 각 필드에 정보가 채워지는 방법에 대한 정보를 확인할 수 있습니다.

각 Marketo Measure 필드와 관련된 개체의 맵을 보려면 [여기를 클릭](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)하십시오.

[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · H · I · J · [K](#k) · [L](#l) · [M](#m) · N · [O](#o) · [P](#p) · Q · [R](#r) · [S](#s) · [T](#t) · [&#128279;](#u)0&rbrace;U 1&rbrace; · [V](#v) · 너비 · X · Y · Z

## {#a}

**계정** | Buyer Attribution Touchpoint에서 발견

이 필드는 BAT에 연결된 계정 이름으로 채워집니다.

**광고 캠페인 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint에서 발견됨

이 필드를 채울 수 있는 세 가지 방법이 있습니다.

`1)` 터치포인트가 유료 검색 노력(AdWords 또는 BingAds)에서 온 경우 광고 플랫폼의 광고 캠페인 ID가 여기에 표시됩니다.

`2)` 터치포인트가 유료 검색에서 가져오지 않은 경우 랜딩 페이지 URL의 utm_campaign 값을 사용하여 필드가 채워집니다.

예: `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

이 예제에서 광고 캠페인 ID는 다음과 같이 표시됩니다. __GAId__ Marketing Virtual Event September2014

`3)` 접점이 오프라인 Salesforce 캠페인(전화 회의, 저녁 식사 등)에서 온 경우 광고 캠페인 ID에 Salesforce 캠페인 ID가 표시됩니다

위의 어느 것도 해당되지 않으면 이 필드는 비어 있습니다.

**광고 캠페인 이름** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색(AdWords/Bing Ads)에서 온 경우 광고 플랫폼의 광고 캠페인 이름이 여기에 표시됩니다.

`2)` 터치포인트가 유료 검색에서 가져오지 않았으며 랜딩 페이지 URL에 utm_campaign에 대한 값이 포함되어 있으면 해당 값이 여기에 채워집니다.

`3)` 터치포인트가 Salesforce 캠페인에서 온 경우 Salesforce 캠페인의 이름이 여기에 표시됩니다.

`4)` 이 이름은 Marketo Measure 계정 내에서 빌드된 활동에서 생성된 터치포인트에 대해 정의된 캠페인 이름으로 채워집니다.

위의 어느 것도 해당되지 않으면 이 필드는 비어 있습니다.

**광고 캠페인 이름(FT)** | Buyer Touchpoint

이 필드는 광고 캠페인 이름과 동일한 방식으로 채워집니다. 그러나 이 필드에는 첫 번째 터치 터치포인트를 생성한 광고 캠페인의 이름이 구체적으로 표시됩니다.

**광고 캠페인 이름(LC)** | Buyer Touchpoint

이 필드는 광고 캠페인 이름과 동일한 방식으로 채워집니다. 그러나 이 필드에는 리드 생성 터치포인트를 생성한 광고 캠페인의 이름이 구체적으로 표시됩니다.

**광고 콘텐츠** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색(AdWords/Bing Ads)에서 온 경우 필드에 광고 플랫폼의 전체 광고 사본이 표시됩니다.

`2)` 터치포인트가 유료 검색에서 가져온 것이 아니면 이 필드에 랜딩 페이지 URL의 utm_content 값이 표시됩니다.

`3)` 터치포인트를 생성한 관련 활동의 제목 값으로 채워집니다.

위의 어느 것도 해당되지 않으면 이 필드는 비어 있습니다.

**광고 대상 URL** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 검색 엔진에서 광고를 클릭하면 이 필드에 사용자가 이동하는 URL 대상이 표시됩니다.

터치포인트가 유료 검색에서 가져온 것이 아닌 경우 필드가 비어 있습니다.

**광고 그룹 Id** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 AdWords/Bing 광고의 광고 그룹 ID가 여기에 표시됩니다.

터치포인트가 유료 검색에서 오지 않은 경우 필드가 비어 있습니다.

**광고 그룹 이름** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 AdWords/Bing 광고의 광고 그룹 이름이 여기에 표시됩니다.

터치포인트가 유료 검색에서 오지 않은 경우 필드가 비어 있습니다.

**광고 ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 AdWords/Bing 광고의 광고 ID가 여기에 표시됩니다.

`2)` 터치포인트가 CRM 활동에서 생성된 경우 활동 외부 ID로 채워집니다.

터치포인트가 유료 검색에서 오지 않은 경우 필드가 비어 있습니다.

**속성 % 사용자 지정 모델** | Buyer Attribution Touchpoint

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 값에 따라 터치포인트에 속하는 매출의 백분율이 표시됩니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**속성 % 첫 번째 터치** | Buyer Attribution Touchpoint

이 필드에는 첫 번째 터치 모델에 따라 접점에 속하는 매출률이 표시됩니다.

**기여도 분석 % 전체** | Buyer Attribution Touchpoint

이 필드에는 전체 경로 모델에 따라 터치포인트에 속하는 매출의 백분율이 표시됩니다.

**속성 % 잠재 고객 생성** | Buyer Attribution Touchpoint

이 필드에는 리드 생성 모델에 따라 접점에 속하는 매출률이 표시됩니다.

**속성 % U자형** | Buyer Attribution Touchpoint

이 필드에는 U자형 모델에 따라 접점으로 인한 매출액 비율이 표시됩니다.

**기여도 분석 % W자형** | Buyer Attribution Touchpoint

이 필드에는 W자형 모델에 따라 접점에 속하는 매출률이 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## B {#b}

**Marketo Measure 영업 기회 금액** | Salesforce 기회

사용자 정의 금액 필드를 사용하여 Opportunity 매출을 보고하는 경우 Marketo Measure에서 이 사용자 정의 금액 필드를 읽을 수 없습니다. Marketo Measure Opportunity Amount 는 Marketo Measure에서 Opportunity에 대한 사용자 정의 Amount 필드를 읽을 수 있는 워크플로우를 만드는 데 사용되는 숨겨진 필드입니다.

**브라우저** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 웹 세션 중에 사용된 웹 브라우저 유형(Chrome, Safari, Firefox 등)이 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## C {#c}

**연락처** | Buyer Touchpoint, Buyer Attribution Touchpoint

필드에는 터치포인트가 속한 연락처 가 표시됩니다.

**Count - 사용자 지정 모델** | Buyer Attribution Touchpoint

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 값에 따라 접점에 부여되는 수익 크레딧의 백분율이 십진수 형식으로 표시됩니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**Count - 사용자 지정 모델** | Buyer Touchpoint

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 값에 따라 접점에 부여되는 속성 크레딧의 백분율이 십진수 형식으로 표시됩니다. 이 필드는 Buyer Touchpoint 오브젝트와 관련이 있으므로 매출 크레딧의 반영이 아니라 속성 크레딧만 반영합니다.

사용자 지정 모델을 사용하지 않는 경우 이 필드는 비어 있습니다.

**카운트 - 첫 번째 터치** | Buyer Attribution Touchpoint

이 필드에는 첫 번째 터치 모델에 따라 접점에 부여되는 매출 크레딧의 백분율이 십진수 형식으로 표시됩니다.

**카운트 - 첫 번째 터치** | Buyer Touchpoint

이 필드에는 첫 번째 터치 모델에 따라 접점에 주어진 속성 크레딧의 백분율이 십진수 형식으로 표시됩니다. 접점이 첫 번째 터치인 경우 이 필드는 항상 1.0(100% 속성 크레딧을 나타냄)이 됩니다. 접점이 첫 번째 터치가 아닌 경우 이 필드는 항상 0(0% 속성 크레딧을 나타냄)이 됩니다.

이 필드는 Buyer Touchpoint 오브젝트와 관련이 있으므로 매출 크레딧의 반영이 아니라 속성 크레딧만 반영합니다.

**Count - 전체 경로** | Buyer Attribution Touchpoint

이 필드에는 전체 경로 모델에 따라 접점에 주어진 매출의 백분율이 십진수 형식으로 표시됩니다.

**개수 - 잠재 고객 생성 터치** | Buyer Attribution Touchpoint

이 필드에는 잠재 고객 생성 모델에 따라 접점에 제공된 수익 크레딧의 백분율이 십진수 형식으로 표시됩니다.

**개수 - 잠재 고객 생성 터치** | Buyer Touchpoint

이 필드에는 리드 생성 모델에 따라 접점에 부여되는 속성 크레딧의 백분율이 소수점 형식으로 표시됩니다. 접점이 잠재 고객 생성 터치인 경우 이 필드는 항상 1.0(100% 속성 크레딧을 나타냄)입니다. 접점이 잠재 고객 생성 터치가 아닌 경우 이 필드는 항상 0(0% 속성 크레딧을 나타냄)이 됩니다.

이 필드는 Buyer Touchpoint 오브젝트와 관련이 있으므로 매출 크레딧의 반영이 아니라 속성 크레딧만 반영합니다.

**개수 - U자형** | Buyer Attribution Touchpoint

이 필드는 U자형 모델에 따라 접점에 부여되는 수익 크레딧의 백분율을 소수점 형식으로 표시합니다.

**개수 - U자형** | Buyer Touchpoint

이 필드에는 U자형 모델에 따라 접점에 부여된 속성 크레딧의 백분율이 십진수 형식으로 표시됩니다. U자형 모델에서 크레딧은 첫 번째 터치, 리드 생성 터치 및 첫 번째 터치와 리드 생성 터치 간에 발생한 중간 양식 제출로 나눠집니다.

이 필드는 Buyer Touchpoint 오브젝트와 관련이 있으므로 매출 크레딧의 반영이 아니라 속성 크레딧만 반영합니다.

**개수 - W자형** | Buyer Attribution Touchpoint

이 필드에는 W자형 모델에 따라 접점에 제공된 크레딧의 백분율이 십진수 형식으로 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## D {#d}

보고된 날짜 | Marketo Measure ABTest, Marketo Measure 이벤트

Marketo Measure 이벤트 - 사용자가 웹 사이트에서 특정 작업을 수행하여 이벤트를 활성화한 날짜

Marketo Measure ABTest - 사용자가 웹 사이트에서 A/B 테스트에 참여한 날짜

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## 전자 {#e}

**이벤트 이름** | Marketo Measure 이벤트

이 필드에는 이벤트를 트리거한 작업의 이름(예: 페이지 보기)이 표시됩니다.

**이벤트 값** | Marketo Measure 이벤트

이벤트(즉, 홈 페이지)에 대한 설명

**실험 이름** | Marketo Measure ABest

이 필드에는 실험의 이름(예: 체험판 단추)이 표시됩니다.

**실험 ID** |Marketo Measure AB 테스트

각 실험에 대한 고유한 식별 코드

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## F {#f}

양식 URL | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 양식 채우기가 발생한 페이지 URL의 단축 버전이 표시됩니다(UTM 매개 변수 없음)

양식 URL - 원시 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 UTM 매개 변수를 포함하여 양식 채우기가 발생한 전체 페이지 URL이 표시됩니다

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## G {#g}

지역 도시 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 잠재 고객/연락처가 웹 사이트를 방문한 도시의 이름이 표시됩니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

지역 국가 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 잠재 고객/담당자가 웹 사이트를 방문한 국가가 표시됩니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

지역 | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 잠재 고객/담당자가 웹 사이트를 방문한 지역 또는 상태가 표시됩니다. 이 작업은 역방향 IP 조회를 통해 수행됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## K {#k}

**키워드 ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치포인트가 유료 검색에서 온 경우 이 필드에는 광고 플랫폼의 키워드 ID가 표시됩니다(Adwords/BingAds).

이 터치포인트가 유료 검색에서 오지 않은 경우 이 필드는 비어 있습니다.

**키워드 MatchType** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치포인트가 유료 검색에서 온 경우 이 필드에는 광고 플랫폼의 일치 유형이 표시됩니다(Adwords/Bing).

**키워드 텍스트** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 이 필드에 광고 플랫폼의 키워드 텍스트(Adwords/BingAds) 또는 랜딩 페이지 URL의 _bk 매개 변수의 값이 표시됩니다.

예: `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` 터치포인트가 유료 검색에서 오지 않으면 이 필드에 랜딩 페이지 URL의 utm_term 값이 표시됩니다.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

터치포인트가 유료 검색에서 오지 않았거나 utm_term 값이 없는 경우 이 필드는 비어 있습니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## L {#l}

**랜딩 페이지** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 웹 세션 중에 방문한 첫 번째 웹 페이지의 URL(UTM 매개 변수 없음)의 단축 버전이 표시됩니다.

**랜딩 페이지 - 원시** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 웹 세션 중에 방문한 첫 번째 웹 페이지의 전체 URL(UTM 매개 변수 포함)이 표시됩니다.

**리드** | Buyer Touchpoint, Marketo Measure 사람

이 필드에는 터치포인트가 속한 리드의 이름이 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## M {#m}

**마케팅 채널** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 터치포인트가 속한 마케팅 활동 또는 마케팅 채널의 일반 그룹(예: 유료 검색, 직접, 소셜 등)이 표시됩니다. 터치포인트는 Marketo Measure 앱에서 채널이 설정된 방식에 따라 그룹화됩니다. 마케팅 채널 또는 채널 설정 방법에 대한 자세한 내용을 보려면 [여기를 클릭하세요](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**마케팅 채널 - 경로** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 마케팅 채널과 터치포인트가 속한 하위 채널이 표시됩니다. 아래 예에서 마케팅 채널 - 경로는 Social.Linkedin입니다. 여기서 마케팅 채널은 Social이고 하위 채널은 LinkedIn입니다.

![](assets/1-3.png)

**Medium** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 Adwords/BingAds의 미디어가 여기에 표시됩니다(예: CPC).

`2)` 터치포인트가 유료 검색에서 오지 않으면 이 필드에 랜딩 페이지 URL의 utm_medium 값이 표시됩니다.

`3)` 접점이 오프라인 캠페인에서 온 경우 이 필드에 Salesforce 캠페인의 &#39;유형&#39; 필드가 표시됩니다.

`4)` 터치포인트를 생성한 관련 활동의 활동 유형 값으로 채워집니다.

위의 어느 것도 해당되지 않으면 Marketo Measure은 자동으로 Medium 값을 설정합니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

O

**기회** | Buyer Attribution Touchpoint

이 필드에는 BAT이 속한 기회가 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

P

**플랫폼** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 컴퓨터 또는 전화의 유형과 웹 세션 중에 사용된 운영 체제의 유형이 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

R

**레퍼러 페이지** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 잠재 고객/연락처가 웹 사이트로 안내한 마지막 웹 페이지의 URL(UTM 매개 변수 없음)이 표시됩니다.

For example:

- 터치포인트가 유료/유기 검색에서 온 경우 필드에 검색 엔진의 URL이 표시됩니다

- 터치포인트가 소셜에서 온 경우 필드에는 소셜 웹 사이트의 URL(예: LinkedIn)이 표시됩니다

**레퍼러 페이지 - 원시** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드는 전체 참조 URL(UTM 매개 변수 포함)을 표시한다는 점을 제외하면 레퍼러 페이지와 동일한 정보를 표시합니다.

**매출 - 사용자 지정 모델** | Buyer Attribution Touchpoint

사용자 지정 속성 모델을 사용하는 경우 이 필드에는 사용자 지정 모델에 설정된 속성 비율에 따라 터치포인트에 속하는 달러 수익 금액이 표시됩니다.

사용자 지정 모델을 사용하지 않는 경우 달러 금액은 0이 됩니다.

**매출 - 첫 번째 터치** | Buyer Attribution Touchpoint

이 필드에는 첫 번째 터치 모델에서 속성 비율에 따라 접점에 속하는 달러 매출액이 표시됩니다.

**매출 - 전체 경로** | Buyer Attribution Touchpoint

이 필드에는 전체 경로 모델에서 기여도 분석에 따라 접점에 속하는 달러 매출액이 표시됩니다.

**매출 - 잠재 고객 생성 터치** | Buyer Attribution Touchpoint

이 필드에는 잠재 고객 생성 모델의 속성 비율에 따라 터치포인트에 속하는 달러 수익 금액이 표시됩니다.

**매출 - U자형** | Buyer Attribution Touchpoint

이 필드에는 U자형 모델의 기여도 분석에 따라 접점에 의한 달러 수익 금액이 표시됩니다.

**매출 - W자형** | Buyer Attribution Touchpoint

이 필드에는 W자형 모델의 기여도 분석에 따라 접점에 의한 달러 수익 금액이 표시됩니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

S

**Salesforce 캠페인** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 터치포인트가 속한 Salesforce 캠페인이 표시됩니다.

**검색 구문** | Buyer Touchpoint, Buyer Attribution Touchpoint

터치포인트가 유료 또는 유기 검색에서 온 경우 이 필드에 검색 엔진에 입력한 검색 구문이 표시됩니다. 그러나 개인 정보 보호 문제로 인해 이 정보는 일반적으로 사용할 수 없습니다.

**세그먼트** | Buyer Attribution Touchpoint

이 필드에는 터치포인트가 속한 세그먼트가 표시됩니다. 이는 Marketo Measure 앱에서 세그멘테이션 규칙을 구성한 방식에 따라 달라집니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

T

**접점 날짜** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 접점이 온라인 소스에서 온 경우 이 필드에 접점이 발생한 날짜와 시간이 표시됩니다.

`2)` 접점이 오프라인 이벤트에서 온 경우 이 필드에는 Salesforce Campaign에 설정된 날짜 및 시간 또는 Campaign 동기화 규칙에서 선택한 날짜 필드가 표시됩니다.

`3)` 터치포인트가 활동에서 온 경우 이 필드에는 활동 규칙에서 터치포인트 날짜로 선택한 필드의 날짜 및 시간이 표시됩니다.

**접점 날짜(FT)** | Buyer Touchpoint

터치포인트 날짜와 동일한 필드이지만 이 필드에는 첫 번째 터치 터치포인트가 발생한 날짜와 시간이 구체적으로 표시됩니다.

**터치포인트 날짜(LC)** | Buyer Touchpoint

접점 날짜와 동일한 필드이지만 이 필드에는 잠재 고객 생성 접점이 발생한 날짜와 시간이 구체적으로 표시됩니다.

**접점 위치** | Buyer Touchpoint, Buyer Attribution Touchpoint

이 필드에는 터치포인트의 위치가 표시됩니다. 접점의 위치는 고객 여정(예: FT, Form, LC, OC, Closed)의 주요 이정표 접점을 반영합니다. 터치 포인트의 위치는 고객 여정에서 언제 발생했는지에 따라 달라지며 단일 터치 포인트는 두 개 이상의 위치를 가질 수 있습니다. 서로 다른 접점 위치는 다음과 같습니다.

첫 번째 터치(FT) - 다른 사람이 내 브랜드와 갖는 첫 번째 마케팅 상호 작용

LC(리드 생성) - 처음 알려진 마케팅 상호 작용(일반적으로 양식 제출 또는 Salesforce 캠페인 포함)

양식 - 방문자가 온라인 양식을 작성할 때

OC(Opportunity Creation) - Opp 생성 시 가장 가까운 마케팅 상호 작용

마감됨 - Opp가 마감된 시기(성사 또는 상실)에 가장 가까운 마케팅 상호 작용

**터치포인트 Source** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` 터치포인트가 유료 검색에서 온 경우 이 필드에 광고 플랫폼의 이름이 표시됩니다(AdWords/BingAds)

`2)` 터치포인트가 유기 검색에서 온 경우 이 필드에 검색 엔진의 이름이 표시됩니다

`3)` #1 또는 #2 않은 경우 utm_source 값이 터치포인트의 랜딩 페이지 URL에 있으면 해당 값이 여기에 표시됩니다.

`4)` 터치포인트가 CRM 캠페인에서 생성된 경우 CRM 캠페인으로 채워집니다.

`5)` 터치포인트가 CRM 활동에서 생성된 경우 CRM 활동으로 채워집니다.

위의 필드가 없으면 이 필드는 &#39;Web Direct&#39; 또는 &#39;Web&#39;으로 채워집니다.

**터치포인트 Source(FT)** | Buyer Touchpoint

이 필드는 터치포인트 Source과 동일하지만 이 필드에는 첫 번째 터치 터치포인트의 소스가 구체적으로 표시됩니다.

**터치포인트 Source(LC)** | Buyer Touchpoint

이 필드는 터치포인트 Source과 동일하지만 이 필드에는 특별히 리드 만들기 터치포인트의 소스가 표시됩니다.

**접점 유형** | Buyer Touchpoint 및 Buyer Attribution Touchpoint에서 찾을 수 있습니다.

이 필드에는 터치포인트의 상호 작용 유형이 표시됩니다. JavaScript 터치포인트에 대한 웹 방문, 웹 양식 또는 웹 채팅으로 표시됩니다. CRM Campaign 터치포인트의 경우, CRM으로 표시됩니다. 활동 터치포인트에 대한 작업 또는 이벤트 유형으로 채워집니다.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

U

**UniqueId** | Buyer Touchpoint, Buyer Attribution Touchpoint

각 터치포인트에 연결된 고유 ID

**사용자 ID** | Marketo Measure ABest

각 사용에 대한 Optimizely의 고유 식별 코드

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)

## V {#v}

**변형** | Marketo Measure ABest

A/B 테스트의 변형 이름

**변형 ID** | Marketo Measure ABest

각 A/B 테스트 변형에 대한 고유한 식별 코드.

[페이지 상단으로 돌아가려면 여기를 클릭하십시오.](#top)
