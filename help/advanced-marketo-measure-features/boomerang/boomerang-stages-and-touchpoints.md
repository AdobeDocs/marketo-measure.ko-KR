---
unique-page-id: 18874558
description: 부메랑 단계와 터치포인트 - [!DNL Marketo Measure] - 제품 설명서
title: 부메랑 단계와 터치포인트
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# 부메랑 단계와 터치포인트 {#boomerang-stages-and-touchpoints}

[!DNL Marketo Measure] 우리의 부메랑 무대 기능을 출시했습니다! Boomerang Stage 기능은 고객의 여정에 대한 가시성을 제공하기 위해 만들어졌습니다 [!DNL Marketo Measure] 판매 주기가 긴 고객 이 기능을 통해 마케터는 Opportunity 여정에서 발생하는 모든 Stage 전환에 대한 터치포인트를 만든 다음 MQL로 이동한 다음 MQL 단계로 되돌아갈 수 있습니다. &quot;MQL 단계 재입력&quot; 또는 &quot;MQL 재입력&quot;에 연결하는 경우 MQL은 부메랑 단계로 간주합니다. 부메랑 무대에는 다음과 함께 기능이 있습니다 [!DNL Marketo Measure] 사용자 지정 단계.

## 이 기능의 기능 {#what-this-feature-does}

* 기회의 여정에서 발생하는 모든 스테이지 전환에 대한 &quot;부메랑&quot; 터치포인트를 만듭니다
* 모든 사용자 지정 단계(예: MQL에 문의하고 SAL로 이동한 다음 MQL 단계로 돌아갑니다.
* Opportunity에 포함할 단계 전환의 수와 세트를 지정할 수 있습니다(예: 처음 10개의 MQL 또는 마지막 5개의 MQL)
* 사용자 지정 모델 사용자인 경우 이러한 각 단계에 할당할 속성 가중치와 백분율 크레딧을 결정할 수 있습니다(예: 첫 번째 또는 마지막 MQL 발생에 속성 가중치를 지정하거나 모든 발생 항목 간에 속성 가중치를 균일하게 배포)

>[!NOTE]
>
>[부메랑 단계를 설정하는 방법에 대한 지침](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## CRM에서 부메랑 단계 및 터치포인트의 모양 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Boomerang 단계(&quot;before&quot;)가 없으면 최신 MQL 또는 리드/연락처 레코드에 연결된 최신 SQL 터치포인트만 표시됩니다.

![](assets/1.png)

부메랑 단계와 터치포인트를 사용하면 각 단계 전환에서 발생하는 터치포인트를 볼 수 있습니다. 이러한 부메랑 터치포인트에 대한 이름 지정 규칙은 다음과 같습니다.

**[스테이지 이름]-00.**

아래 예를 사용하여 다음을 수행하십시오 [!DNL Marketo Measure] account는 MQL 및 SQL을 해당 부메랑 단계에 포함했으며, 스테이지당 2개의 부메랑 터치포인트를 표시하도록 선택했습니다.

![](assets/2.png)

**MQL-01** 는 첫 번째 MQL 단계 전환입니다.

터치 포인트 위치의 숫자 값은 단계 전환이 발생한 순서를 나타냅니다. 마지막 부메랑 터치포인트는 다음과 같이 스탬핑됩니다.

MQL-02 **(마지막)**

## 부메랑 단계의 기존 데이터 변경 방법 {#how-boomerang-stages-change-your-existing-data}

부메랑 스테이지는 영향을 줄 것이다:

**채널별 속성**

* 이후 [!DNL Boomerang Stages] 더 많은 터치포인트를 만듭니다. 이렇게 하면 현재 데이터에 있는 터치포인트 간에 속성이 배포되는 방식이 변경됩니다. 그 결과, 수익 값이 마케팅 채널 간에 이동하게 될 수 있습니다. 구현하기 전에 이를 고려하십시오 [!DNL Boomerang stages]또는 계정 관리자에게 자세한 내용을 문의하십시오.

**&quot;같음&quot;을 사용하는 모든 보고서 [터치 포인트 위치]&quot;**

* 부메랑 단계는 새로운 터치포인트 위치를 데이터에 도입할 것입니다. [!DNL Marketo Measure] &quot;MQL-01&quot; 또는 &quot;MQL-05(마지막)&quot;과 같이 스테이지의 발생을 포함하도록 터치 포인트 위치의 형식을 변경합니다. 이 예에서는 Boomerang Stage가 &quot;Touchpoint Position이 MQL과 같음&quot;을 사용하는 모든 보고서에 영향을 줍니다. 이러한 보고서를 조정하려면 필터가 대신 &quot;포함&quot; 연산자를 사용해야 합니다.

## FAQ {#faq}

**내 속성 모델에 몇 개의 부메랑 단계를 포함할 수 있습니까?**

최대 15개의 단계를 선택할 수 있습니다.

**Q: 무대마다 얼마나 많은 부메랑 터치포인트를 가질 수 있나요?**

스테이지당 최대 10개의 부메랑 터치포인트를 선택할 수 있습니다.

**Q: 왜 우리는 무대 당 10개의 부메랑만 제한하는가?**

[!DNL Marketo Measure] 처리 시간을 제어하려면 단계 수에 제한을 두어야 합니다. 기여도 분석 모델에 15개의 부메랑 단계 및 단계당 10개의 부메랑 터치포인트를 포함하도록 선택하면 잠재 고객/연락처 레코드당 150개 이상의 터치포인트를 가질 수 있습니다.

**Q: Data Warehouse이 있습니다 제가 모든 자료를 얻을 수 있을까요, 아니면 부메랑 무대 캡도 저에게 적용되나요?**

처리 제한 때문에 이 캡은 Data Warehouse 및 CRM에 적용됩니다 [!DNL Marketo Measure] 이(가) 제자리에 있습니다. Data Warehouse은 단계당 10개 터치포인트 제한을 보게 된다.

**Q: 사용자 정의 모델링에 부메랑 단계를 사용할 때 얻을 수 있는 이점은 무엇입니까?**

사용 [!UICONTROL Boomerang] 사용자 지정 모델링을 사용하는 스테이지에서는 속성 가중치를 [!UICONTROL Boomerang] 터치포인트. 이러한 단계에 매출 크레딧을 할당합니다.

사용자 정의 모델링을 사용하지 않으면 [!DNL Marketo Measure] 은 각 부메랑 및 단계 전환에 대한 터치포인트를 만들지만 이러한 터치포인트에 속성 크레딧을 할당하지 않습니다. 속성 크레딧을 받을 유일한 부메랑 접점은 양식 제출 접점입니다. 사용자 지정 모델이 없으면 [!DNL Boomerang] 터치포인트는 &#39;중간 터치&#39;와 동일하게 간주되며 그에 따라 속성 크레딧을 받습니다.
