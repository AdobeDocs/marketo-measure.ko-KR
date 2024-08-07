---
unique-page-id: 18874775
description: 기계 학습 모델 FAQ - [!DNL Marketo Measure]
title: 기계 학습 모델 FAQ
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# 기계 학습 모델 FAQ {#machine-learning-model-faq}

[!DNL Marketo Measure] 기계 학습 모델은 터치포인트 데이터를 사용하여 각 단계에 할당해야 하는 속성 가중치를 계산합니다. 이는 각 단계가 거래를 성사시키는 데 얼마나 중요했는지에 따라 결정된다.

머신 러닝 모델의 기여도 분석 비율은 각 단계에 대해 어떻게 알려 줍니까?

각 단계의 속성 비율은 마케팅 노력의 잠재적인 영향을 반영합니다. 비율이 높을수록 해당 시점에서 마케팅이 단계 이동에 직접 영향을 줄 수 있음을 의미합니다. 기여도 분석 비율이 낮으면 팀이 모니터링하는 단계가 덜 중요함을 의미합니다.

머신 러닝 모델은 어떻게 계산됩니까?

[!DNL Marketo Measure]은(는) 계정의 터치포인트 데이터를 사용하여 각 사용자 지정 단계의 중요도를 계산합니다. 각 단계의 중요도를 결정하는 데 사용되는 기준은 다음과 같습니다.

* 모델 정확도: 접점 데이터로 예측 모델을 구축하여 최종적으로 딜을 따낼지 예측한다면 모델이 얼마나 정확할까요? 예측 정확도가 높다는 것은 이 단계의 세부 사항이 거래가 성사될 것인지 여부와 더 상관 관계가 있다는 것을 의미합니다
* 전환율: 이 특정 단계의 리드 또는 기회가 높은 비율로 다음 단계로 전환되는 경우 이 단계에서 발생한 마케팅 활동이 크게 중요하지 않았음을 나타냅니다. 반대로 어떤 단계가 낮은 비율로 다음 단계로 전환한다면 이는 이 단계에서 발생한 마케팅 활동이 전환을 견인하는 데 영향을 미쳤음을 시사할 수 있다.
* 접점 고유성 가중치: 단계가 독립형 전환으로 발생하는 경우, 즉, 동시에 발생한 다른 단계 전환이 없는 경우 이 단계에서 더 높은 속성 가중치를 받을 수 있습니다. 반대로 단계에 대한 접점이 다른 단계와 공유되는 경우(예: 접점이 첫 번째 터치, 리드 전환 및 기회 전환 단계를 공유함) 이 단계는 더 낮은 속성 가중치를 받을 수 있습니다.

사용자 지정 단계에 대한 최종 가중치는 다음과 같이 계산됩니다.

**_모델 백분율 = 모델 정확도 x 전환율 x 터치포인트 고유성 가중치_**

마지막에 모든 사용자 지정 단계 가중치가 정규화되고 아래와 같이 %로 변환됩니다.

기계 학습 열에 숫자가 표시되지 않는 이유는 무엇입니까?

계정에 대해 사용자 지정 속성 모델 이 활성화되면 일반적으로 이전 데이터를 기반으로 모델이 실행되고 이러한 숫자를 빌드하는 데 3~7일 정도 걸립니다.

머신 러닝 모델은 얼마나 자주 업데이트됩니까?

우리는 7일마다 모델을 재실행합니다.

모델이 항상 중간 터치를 10%로 설정하는 이유는 무엇입니까?

Middle Touches에 10% 속성 크레딧을 할당하는 것은 모든 속성 모델에 적용되는 표준 설정입니다.

내 속성 분포는 언제 변경해야 합니까?

계정 관리자에게 문의하여 속성 비율 변경의 의미와 사용자 지정 모델에 포함할 단계에 대해 논의하십시오. 각 [!DNL Salesforce] 및 판매 프로세스는 고유하며, 사용자 지정 모델이 정확하게 모델링되도록 하려고 합니다.

고객의 일반적인 트렌드를 확인했습니다.

우리가 주목한 한 한 가지 경향은 모델에 더 많은 단계를 포함하는 것이 항상 유익하지는 않다는 것입니다. 예를 들어 고객이 단계 하단에 여러 개의 Opportunity 단계를 추가한 경우 이러한 단계는 매우 낮은 기여도 분석 비율 값을 받는 경향이 있습니다. 낮은 백분율 값은 높은 전환율을 나타내며, 이는 일반적으로 이러한 단계가 거래를 성사시키는 데 영향을 미치지 않음을 의미합니다. 일부 고객은 최종적으로 단계에 이러한 단계를 포함하지 않기로 결정합니다. 속성 모델에서 단계를 제거하기로 결정한 경우 시스템 모델이 백분율을 다시 계산하고 재분배합니다.

또한 잠재 고객 생성에서 마케팅 적격 단계로의 전환율이 높으며 결과적으로 마케팅 적격 단계에서 더 낮은 비율의 속성 가중치를 받을 수 있다는 것을 발견했습니다. 비즈니스 및 판매 주기에 따라 맞춤형 모델에서 이 단계를 제거하는 것이 유용할 수 있습니다.

특정 단계 전환을 통해 마케팅 활동을 추적하지만 이 단계가 속성 크레딧을 받지 않도록 하려면 모델에 이 단계를 포함하고 해당 단계에 0% 속성 크레딧을 할당할 수 있습니다.
