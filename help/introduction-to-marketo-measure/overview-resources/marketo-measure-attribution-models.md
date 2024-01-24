---
unique-page-id: 18874568
description: Marketo Measure 속성 모델 - Marketo Measure - 제품 설명서
title: Marketo Measure 속성 모델
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
feature: Attribution
source-git-commit: aa12df4d0c77cdc677f78bcab19497806927ec2b
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 0%

---

# Marketo Measure 속성 모델 {#marketo-measure-attribution-models}

Marketo Measure에서는 6가지 유형의 속성 모델을 제공합니다.

* 첫 번째 터치
* 잠재 고객 생성
* U자형
* W자형
* 전체 경로
* 사용자 지정 모델

이러한 모델은 복잡성이 다양합니다. 첫 번째 터치 및 리드 생성은 간단한 단일 터치 모델입니다. 나머지 4개는 보다 복잡한 멀티 터치 모델입니다. Marketo Measure의 속성 모델 구조는 고객 여정에서 발생하는 4가지 주요 접점을 반영합니다.

* 첫 번째 터치(FT)
* 리드 생성(LC)
* 영업 기회 생성(OC)
* 비공개 거래(CW)

![](assets/1-1.png)

다음에서 **단일 터치 모델**, 속성 크레딧은 하나의 이정표 접점에만 기인 - 따라서 이름은 &#39;single-touch&#39;입니다.
다음에서 **멀티 터치 모델**, 대부분의 속성 크레딧이 둘 이상의 마일스톤 접점에 할당됩니다. 나머지 크레딧은 이정표 접점 사이에 발생하는 접점에 기인합니다.

다음 몇 섹션에서는 각 속성 모델과 속성 크레딧이 지정되는 방법을 다룹니다.

## 단일 터치 모델 {#single-touch-models}

**첫 번째 터치 모델**

첫 번째 터치 모델은 리드가 조직과 갖는 첫 번째 상호 작용에만 중점을 둡니다. 이 모델은 잠재 고객이 귀사를 처음 알게 된 첫 번째 터치인 FT(First Touch)에 기여도 분석 크레딧의 100%를 기여합니다.

케이트 방문 `www.adobe.com` Adwords Ad 를 통해 처음으로 백서를 봅니다. Adwords 채널은 해당 Opportunity에서 기여도 분석 크레딧을 100% 받습니다.

![](assets/2.png)

**잠재 고객 생성 모델**

잠재 고객 생성 모델은 잠재 고객이 연락처 정보를 제공하고 잠재 고객이 될 때 LC 접점에 속성 크레딧의 100%를 지정합니다.

Kate의 첫 번째 방문 이후인 이전 예제를 계속 `www.adobe.com` Adwords를 통해 Austin은 Linkedin 게시물을 통해 웹 사이트를 방문합니다. Austin은 양식을 작성하고 단서가 됩니다. 이 모델에서 Linkedin은 속성 크레딧의 100%를 받습니다.

![](assets/3.png)

## 멀티 터치 모델 {#multi-touch-models}

멀티 터치 모델은 더 길고 복잡한 영업 주기를 위해 사용됩니다. 이러한 모델은 계정/회사의 여러 사람이 구매자의 여정에 관여하는 경우 특히 유용합니다.

**U자형 모델**

U자형 모델은 FT 및 LC 터치포인트 모두에 중점을 둡니다. 이 모델에서 FT와 LC 접점은 각각 매출액 크레딧의 50%를 받습니다.

케이트의 첫 방문 `www.adobe.com` adWords 광고를 통해 기여도 분석 크레딧의 50%를 받습니다. 나머지 50퍼센트는 Austin이 양식을 작성하고 선두가 되도록 유도한 Linkedin의 게시물에 귀속될 것입니다.

![](assets/4.png)

**W자형 모델**

이정표 접점 중 세 개가 W자형 모델에 포함되어 있다. 이 모형에서 FT, LC, OC 접점은 각각 속성 크레딧의 30%에 귀속된다. 나머지 10%는 세 개의 이정표 접점 사이에 발생하는 중간 접점에 비례적으로 기여합니다.

케이트와 오스틴은 동료인 힐러리에게 Marketo Measure을 언급했다. 그녀는 구글 검색을 통해 콘텐츠 한 조각을 찾아 양식을 작성한다. 나중에 Austin은 웨비나 등록 이메일을 받고 웹 사이트에서 등록 양식을 작성합니다. Kate는 Marketo Measure 제품에 대해 영업 담당자와 이야기를 나누었습니다.

Hillary 는 요금 페이지에 대한 링크가 포함된 이메일을 받고 페이지를 방문합니다. 그러면 계정에 대한 Opportunity 가 생성됩니다. 가격 책정 페이지에 대한 Hillary의 웹 방문은 Opportunity Creation 날짜와 가장 가까운 마케팅 상호 작용이었기 때문에 Opportunity Creation에 대한 크레딧을 받습니다. 각 마일스톤 접점에는 속성 크레딧의 30%가 할당되고 중간 접점은 나머지 10%가 할당됩니다.

![](assets/5.png)

**전체 경로 모델**

전체 경로 모델은 4개의 이정표 접점을 모두 포함합니다. FT, LC, OC, CW는 각각 수익크레딧의 22.5%가 주어지고 나머지 10%는 중개자 접점 간에 균등하게 분배된다.

기회 창출 후, Kate, Austin 및 Hillary는 CMO인 Elizabeth에게 Marketo Measure을 지원하기로 결정했습니다. 엘리자베스는 Marketo Measure이 행사를 주최하는 회의에 참석합니다. Kate는 사례 연구에 대한 Linkedin 게시물을 보고 해당 콘텐츠를 다운로드할 수 있는 양식을 작성합니다. Elizabeth는 Marketo Measure이 주최하는 판매 만찬에 참석한다. 저녁 식사 후, 그녀는 Marketo Measure을 구매하기로 결정하고 고객이 됩니다. 이 시나리오에서는 판매 만찬이 종료된 거래로 인한 수익 크레딧의 22.5%에 귀속됩니다. FT, LC, OC 접점도 각각 22.5%의 크레딧을 받는다. 중간 접점은 나머지 10%의 수익 크레딧에 동일하게 할당됩니다.

![](assets/6.png)

**사용자 지정 속성 모델**

Marketo Measure은 또한 사용자가 모델에 포함할 터치포인트 또는 사용자 지정 단계를 선택할 수 있는 사용자 지정 속성 모델을 제공합니다. 또한 사용자는 이러한 접점 및 단계에 기여하는 속성 크레딧의 비율을 제어할 수 있습니다. Opportunity에 전용 중간 터치만 없으면 백분율이 다른 Position에 고르게 분산됩니다.
