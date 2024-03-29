---
description: 사용자 지정 모델에 대한 우수 사례 - [!DNL Marketo Measure]
title: 사용자 지정 모델에 대한 우수 사례
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 0%

---

# 사용자 지정 모델에 대한 우수 사례 {#best-practices-for-custom-model}

## 개요 {#overview}

이외에도 [!DNL Marketo Measure] 즉시 사용 가능한 속성 모델 을 통해 계층 2 이상 고객은 사용자 지정 속성 모델에 액세스할 수 있습니다.

다음 [!DNL Marketo Measure] 사용자 지정 속성 모델을 통해 사용자는 모델에 포함할 이정표 접점 위치 및/또는 사용자 지정 단계를 선택할 수 있습니다. 또한 사용자는 모델 내의 각 단계에 귀속되는 크레딧의 백분율을 제어하거나(사용자는 최대 6개의 추가 사용자 정의 단계를 정의할 수 있음), 또는 사용자가 제안한 속성 백분율 값을 사용할 수 있습니다. [!DNL Marketo Measure] 머신 러닝 모델.

사용자 지정 속성 모델에는 다음과 같은 두 가지 주요 측면이 있습니다.

**사용자 지정 단계** 사용자가 단계 를 비즈니스 및 프로세스와 관련하여 정의할 수 있습니다. 사용자 지정 단계는 다음과 같이 구매자의 여정 전반에 걸쳐 &quot;이정표&quot;를 표시해야 합니다. [!DNL Marketo Measure] 이정표(첫 번째 터치, 리드 생성 터치, 기회 생성 터치 및 마감된 원 터치)는 스톡 속성 모델 내에서 수행됩니다. 다음을 보장하기 위해 사용자 지정 단계가 계정 내에서 제대로 정의되고 매핑되는 것이 중요합니다 [!DNL Marketo Measure] 는 스테이지 전환을 제대로 추적합니다. 이는 각 단계와 연계되어야 하는 접점을 식별하고 크레딧을 적절하게 속성을 지정하기 위한 것입니다. 사용자 지정 스테이지 매핑은 기본적으로 표준 &#39;스테이지 매핑&#39;의 확장이며 동일한 사례를 따라야 합니다.

>[!NOTE]
>
>자세한 내용은 스테이지 매핑 모범 사례 리소스 를 참조하십시오

**사용자 지정 속성 모델링** 은 사용자 지정 단계 단계를 선택하면 정의됩니다. 그런 다음 사용자는 각 사용자 지정 단계뿐만 아니라 [!DNL Marketo Measure] 마일스톤 단계. 사용자는 각 단계에 맞는 크레딧을 할당하거나 [!DNL Marketo Measure] 과거 데이터를 기반으로 한 &quot;제안 모델&quot; 역할을 하는 머신 러닝 모델.

다음을 보장하기 위해 사용자 정의 모델의 이러한 두 가지 측면을 정확하고 정확하게 정의하는 것이 중요합니다 [!DNL Marketo Measure] 는 정확한 사용자 지정 속성 모델을 생성합니다.

## 우수 사례 {#best-practice}

사용자 지정 모델을 처음 설정하든 아니면 이전에 설정된 사항을 검토하든 관계없이 다음 모범 사례를 염두에 두는 것이 중요합니다.

* 단순 시작
   * 에 중요한 사용자 지정 모델에 추가할 주요 단계를 식별합니다 [!DNL Marketo Measure] 보고. 일반적으로 이러한 단계는 일반적으로 측정되거나 통찰력을 얻고자 하는 단계입니다
   * 시간이 지남에 따라 언제든지 사용자 정의 모델에 을 추가할 수 있습니다
* 활용 [!DNL Marketo Measure] 머신 러닝 모델
   * 기여도 분석 분류의 백분율을 결정하기 위해 애쓰는 경우 [!DNL Marketo Measure] 머신 러닝 모델은 사용자 지정 속성 모델을 설정할 때 정보에 입각한 결정을 내리는 데 도움이 될 수 있습니다.
   * 머신 러닝 모델을 볼 때 각 단계의 속성 비율은 마케팅 활동의 잠재적 영향을 반영합니다
      * 비율이 높을수록 해당 시점에서 마케팅이 단계 이동에 직접 영향을 줄 수 있음을 의미합니다
      * 기여도 분석 비율이 낮으면 팀이 모니터링하는 단계가 덜 중요함을 의미합니다
* 리드 또는 연락처 단계 중 하나를 기준으로 단계 단계를 정의해야 하며, 둘 다 정의해서는 안 됩니다.
   * 즉, 모든 사람이 상대 개체에 있는 해당 단계를 통과하도록 해야 합니다
      * 예를 들어 리드 오브젝트에서 MQL 단계를 정의하는 경우 모든 사람은 시스템으로 리드 로 이동하고 리드 레코드에서 MQL로 표시되어야 합니다. [!DNL Marketo Measure] 잠재 고객의 MQL 전환과 관련된 터치를 정확하게 반영합니다. 그렇지 않고 일부 사용자가 MQL이 잠재 고객이 되기 전에 [연락처]로 진행하는 경우 [!DNL Marketo Measure] 은 터치포인트 데이터에서 이를 정확하게 설명할 수 없으며, 이미 MQL을 가지고 있다고 간주해야 합니다. [!DNL Marketo Measure] 무대 호핑은 설명할 수 없기 때문에 설령 안 하더라도 무대가 통과된 것으로 유추해 보기로 한다.
* 통합하는 사용자 지정 단계를 정의하는 데 사용되는 모든 필드에 대해 필드 내역 추적이 활성화되어 있는지 확인합니다.
* 공식 필드를 사용하여 사용자 정의 단계를 정의하지 않음
   * 부울 필드는 모범 사례 권장 사항입니다
* 와 일치하는 사용자 지정 모델에 사용자 지정 단계 통합 안 함 [!DNL Marketo Measure] 마일스톤 터치포인트 위치(FT, LC, OC, 원화/손실 마감)
   * 그럴 경우 이러한 위치는 항상 동시에 발생하며 유입 경로의 일부에 부풀려진 속성 크레딧이 발생할 수 있습니다.
* 영업 운영 팀과 협력
   * 단계에 가장 가까운 작업을 하는 팀을 가져오면 올바른 단계를 사용하고 있으며 이러한 단계가 올바르게 정의되었는지 확인합니다

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

연 2회 이상 사용자 정의 모델을 검토하면 사용자 정의 속성 보고가 정확하고 신뢰할 수 있도록 합니다.

사용자 지정 모델이 머신 러닝 모델을 활용하는 경우, 분기별로 사용자 지정 모델 내에서 해당 애플리케이션을 검토하여 사용자 지정 모델이 가능한 최신 상태인지 확인해야 합니다.

사용자 지정 모델에 대한 검토를 트리거할 수 있는 다른 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* CRM 단계에 대한 모든 변경 사항
* 조직 단계 업데이트
* 에서 부정확한 수익 데이터 보기 [!DNL Marketo Measure] 사용자 지정 모델을 적용할 때의 보고
* 조직 단계와 더 이상 관련이 없는 접점 위치가 채워진 것을 볼 수 있습니다.

>[!MORELIKETHIS]
>
>* [사용자 지정 속성 모델 및 설정](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [사용자 지정 모델에 대한 필드 내역 추적 활성화](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [머신 러닝 모델](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
