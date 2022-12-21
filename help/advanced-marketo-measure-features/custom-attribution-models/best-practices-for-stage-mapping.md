---
description: 스테이지 매핑 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 스테이지 매핑 우수 사례
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 스테이지 매핑 우수 사례 {#best-practices-for-stage-mapping}

## 개요 {#overview}

의 단계 매핑 섹션 [!DNL Marketo Measure] 계정은 [!DNL Marketo Measure] 사용자 지정 속성 모델을 사용하는 경우 정의한 사용자 정의 단계 및 CRM에서 자동으로 가져옵니다. 당신의 유효성 [!DNL Marketo Measure] 데이터는 다음 단계를 올바르게 정렬하여 [!DNL Marketo Measure] 는 단계 및 해당 단계 전체에서 레코드의 진행 상황을 정확하게 파악할 수 있습니다.

의 단계 매핑 섹션에서 [!DNL Marketo Measure] 예를 들어 CRM에서 활성 단계와 비활성 단계를 모두 볼 수 있습니다. 모든 단계를 현재 단계에 맞게 최상으로 정렬하십시오.

이 섹션에서 관리되는 추가 기능은 단계 단계이며, 속성을 적용하지 않고 단계에 단계를 추가할 수 있습니다. 단계 단계는 터치포인트로 추적되고 CRM의 터치포인트 위치 필드에 채워집니다. 이러한 단계 단계는 또한 의 다양한 여정 보드 내에 표시됩니다 [!DNL Marketo Measure] 검색.

## 우수 사례 {#best-practices}

처음 단계 매핑을 평가하든 아니면 단계 순서를 단순히 검토하든 관계없이 다음 모범 사례를 기억하십시오.

* 명령만 하면 돼!
   * 고려 [!DNL Marketo Measure] CRM에서 활성 단계와 비활성 단계를 모두 가져와서 리드/연락처 또는 Opportunity에서 사용할 수 있는 모든 단계가 함께 그룹화되어 정렬되었는지 확인합니다
* 사용자 지정 단계를 정의할 때 스테이지를 정의하는 데 사용되는 모든 필드에 대해 필드 내역 추적이 활성화되어 있는지 확인합니다
* 수식 필드를 사용하여 사용자 지정 단계를 정의하지 마십시오
   * 가장 좋은 방법은 부울 필드입니다
* Lead 또는 Contact 단계 섹션은 Lost, Open 및 Converted 로 구분됩니다. 단계가 적절한 단계 섹션에 있는지 확인합니다.
   * 잘못된 단계 섹션에 스테이지가 있으면 매우 올바르지 않을 수 있습니다 [!DNL Marketo Measure] 데이터
* Opportunity 단계 섹션은 Lost, Open 및 Won으로 구분됩니다. 단계가 적절한 단계 섹션에 있는지 확인합니다.
   * 잘못된 단계 섹션에 스테이지가 있으면 매우 올바르지 않을 수 있습니다 [!DNL Marketo Measure] 매출 또는 파이프라인 매출 데이터
* 중복 스테이지 이름을 사용하지 마십시오(시스템에서 이러한 이름을 감지하여 자동으로 제거합니다.).

## 유지 관리 우수 사례 {#best-practices-for-maintenance}

1년에 한 번 단계 매핑을 검토하여 Opportunity 데이터가 [!DNL Marketo Measure] 는 정확하며 최신 상태입니다.

단계 매핑의 검토를 트리거할 수 있는 기타 이유는 다음과 같습니다.

* 마케팅 팀의 이직률
* CRM 단계에 대한 모든 변경 사항
* 조직의 단계에 대한 업데이트
* 에서 잘못된 매출 데이터 보기 [!DNL Marketo Measure] 보고

>[!MORELIKETHIS]
>
>[단계 단계와 사용자 지정 모델 단계 간의 차이점](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
