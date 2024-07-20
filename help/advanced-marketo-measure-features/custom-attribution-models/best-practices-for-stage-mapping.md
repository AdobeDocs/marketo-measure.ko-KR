---
description: 스테이지 매핑 모범 사례 - [!DNL Marketo Measure]
title: 스테이지 매핑 우수 사례
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# 스테이지 매핑 우수 사례 {#best-practices-for-stage-mapping}

## 개요 {#overview}

[!DNL Marketo Measure] 계정의 단계 매핑 섹션은 [!DNL Marketo Measure]이(가) CRM에서 자동으로 가져오는 단계와 사용자 지정 속성 모델을 사용하는 경우 정의한 모든 사용자 지정 단계에 대해 간략하게 설명합니다. [!DNL Marketo Measure] 데이터의 유효성은 이러한 단계 순서를 올바르게 지정하기 때문에 [!DNL Marketo Measure]이(가) 단계 및 해당 단계 전체에서 레코드의 진행률을 정확하게 이해할 수 있습니다.

[!DNL Marketo Measure] 인스턴스의 단계 매핑 섹션에서 CRM의 활성 단계와 비활성 단계를 모두 볼 수 있습니다. 현재 단계에 따라 모든 단계를 능력에 맞게 정렬하십시오.

이 섹션에서 관리되는 추가 기능은 속성을 적용하지 않고 단계에 단계를 추가할 수 있는 단계 단계입니다. 단계 단계는 터치포인트로 추적되고 CRM의 터치포인트 위치 필드에 채워집니다. 이러한 단계 단계는 [!DNL Marketo Measure] Discover의 다양한 여정 게시판에서도 표시됩니다.

## 우수 사례 {#best-practices}

스테이지 매핑을 처음 평가하든 단계 순서를 검토하든 관계없이 다음 모범 사례를 염두에 두는 것이 중요합니다.

* 질서가 전부입니다!
   * [!DNL Marketo Measure]이(가) CRM에서 활성 및 비활성 단계를 모두 가져오는 것을 고려하여 잠재 고객/연락처 또는 영업 기회에서 사용할 수 있는 단계를 함께 그룹화하고 그에 따라 순서를 지정하는지 확인하십시오
* 사용자 지정 단계를 정의할 때 단계를 정의하는 데 사용되는 모든 필드에 필드 내역 추적이 활성화되어 있는지 확인합니다
* 공식 필드를 사용하여 사용자 정의 단계를 정의하지 않음
   * 부울 필드는 모범 사례 권장 사항입니다
* 잠재 고객 또는 연락처 단계 섹션은 손실, 열기 및 전환으로 구분되며 단계가 해당 단계 섹션에 있는지 확인합니다
   * 스테이지가 잘못된 스테이지 섹션에 있으면 [!DNL Marketo Measure] 데이터가 많이 잘못될 수 있습니다.
   * Marketo Measure Ultimate 고객이고 기본 대시보드 개체를 연락처로 설정한 경우, 아래 두 필드를 리드와 관련된 것으로 사용하지 마십시오([자세히 알아보기](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Opportunity 단계 섹션은 Lost, Open 및 Won으로 구분되므로 해당 단계가 적절한 단계 섹션에 있는지 확인합니다.
   * 스테이지가 잘못된 스테이지 섹션에 있으면 [!DNL Marketo Measure] 매출 또는 파이프라인 매출 데이터가 많이 잘못될 수 있습니다.
* 중복 단계 이름을 사용하지 마십시오(시스템에서 단계 이름을 감지하고 자동으로 제거합니다).
* NULL 값을 확인하는 규칙을 설정하려면 값 텍스트 상자를 비워 둡니다.

## 유지 관리 우수 사례 {#best-practices-for-maintenance}

1년에 한 번 단계 매핑을 검토하면 [!DNL Marketo Measure]의 Opportunity 데이터가 정확하고 최신 상태인지 확인할 수 있습니다.

스테이지 매핑 검토를 트리거할 수 있는 다른 이유에는 다음이 포함됩니다.

* 마케팅 팀에서의 이직률
* CRM 단계에 대한 모든 변경 사항
* 조직의 단계에 대한 업데이트
* [!DNL Marketo Measure] 보고에서 잘못된 매출 데이터를 보고 있습니다.

>[!MORELIKETHIS]
>
>[단계 단계와 사용자 지정 모델 단계의 차이점](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
