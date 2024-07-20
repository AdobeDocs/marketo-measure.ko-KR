---
description: 현재 릴리스 정보 - [!DNL Marketo Measure]
title: 최신 릴리스 정보
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 9f374537dd3690b5c904e2ac1933ff460dc66282
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 0%

---

# 릴리스 노트: 2024 {#release-notes-2024}

2024 릴리스의 모든 새로운 기능 및 업데이트된 기능은 아래를 참조하십시오.

## 3분기 릴리스 {#q3-release}

<p>

**미리 알림: Salesforce 필드 사용 중단 - 6월 14일**

작년에 발표된 대로 통합을 단순화하고 Salesforce 표준 개체로 내보낼 필요가 없도록 [리드/연락처 개체로의 내보내기 작업을 단계적으로 축소](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"}할 예정입니다. [여기에 기록됨](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}단계를 따라 터치포인트 개체에서 동일한 데이터를 가져올 수 있습니다. 또한 이 데이터를 리드/연락처 개체에 추가하기 위한 워크플로우 만들기에 대한 설명서를 공유할 것입니다. 사용 중지 기간은 2024년 6월 14일부터 적용됩니다.

이 변경은 다음과 같은 두 가지 주요 이점을 제공합니다.

* **Salesforce API 비용 절감**: 고객은 Salesforce API 비용을 약 10% 절감할 수 있습니다.
* **간소화된 통합**: 내보내기 작업에서 가장 많은 오류가 이러한 프로세스와 관련이 있습니다. 이를 제거하면 통합이 크게 간소화됩니다.

**속성 영업 기회 대시보드**

마케팅 노력이 초기 및 성숙 파이프라인 기회 모두에 기여하는 방식에 대한 포괄적인 보기를 제공하기 위해 설계된 새로운 [속성 영업 기회 대시보드](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"}를 소개하게 되어 기쁘게 생각합니다. 이 대시보드를 사용하면 영업 기회 단계를 기준으로 필터링할 수 있는 유연성을 가지고 전략에 따라 발생하는 모든 개설 및 마감된 영업 기회에 대한 세부 정보를 파악할 수 있습니다. 속성 기회 금액 측면에서 가장 높은 등급을 제공하는 채널, 하위 채널 또는 캠페인에 대한 통찰력을 제공하며, 속성 오픈 및 마감된 기회의 수와 함께 총 속성 기회 금액을 표시합니다.

**Marketo Measure Ultimate용 Marketo Engage 쿠키 동기화**

이제 Marketo Measure Ultimate에서 Marketo Engage 쿠키 동기화를 사용할 수 있습니다. 이 기능을 사용하려면 다음 작업을 수행하십시오.

1. AEP 스키마 페이지에서 B2B 개인 스키마를 편집하고 필드 그룹 &quot;개인 세부 정보 Marketo Engage&quot;를 추가합니다.
1. MMU로 데이터를 수집할 때 필드 그룹의 쿠키 ID 필드를 Marketo Engage의 쿠키 필드에 매핑합니다.

**계층 2 고객에 대해 부메랑 단계가 활성화됨**

이전에는 Tier 3 고객에게만 제공되었던 부메랑 스테이지 기능은 2024년 6월 13일부터 모든 Tier 2 고객에게도 제공됩니다. 이 기능에 대한 자세한 내용은 아래 설명서를 참조하십시오.

* [부메랑 단계 및 터치포인트](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [부메랑 단계 설정](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [부메랑 단계 시나리오](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## 2분기 릴리스 {#q2-release}

<p>

**타사 쿠키 페이드 아웃에 대한 응답으로 Marketo Measure 기능 사용 중단**

개인 정보 보호 문제가 증가함에 따라 서드파티 쿠키는 Google Chrome의 2024년 3분기 마감 기한이 종료를 알리는 등 단계적으로 폐지되고 있습니다. Marketo Measure은 타사 쿠키, 특히 Google/DoubleClick 노출 쿠키에 의존하는 도메인 간 추적 및 뷰스루 기여도 분석에 따른 특정 기능을 더 이상 사용하지 않습니다. 이 변경 사항은 다른 Marketo Measure 기능이나 자사 쿠키의 사용에 영향을 주지 않습니다. Google의 타임라인에 따라 이러한 기능은 6월 1일까지 더 이상 사용되지 않을 것으로 예상되지만, 이 날짜 이전에 수집된 데이터는 여전히 고객이 액세스할 수 있습니다.

* [Marketo Measure에서 타사 쿠키 사용 중단에 적응](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure 쿠키](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**향상된 오류 처리에 대한 단계별 롤아웃**

권한 오류에 대한 즉각적인 인앱 펄스 알림부터 시작하여 내보내기 작업에 대한 향상된 오류 처리의 단계별 롤아웃을 소개하고, 오류 시점에서 내보내기 작업이 일시 중지되는 새로운 접근 방식으로 전환하는 중입니다. 이러한 변경은 데이터 무결성 및 가시성을 향상시켜 사용자를 위한 보다 원활하고 안정적인 데이터 관리 프로세스를 보장하는 것을 목표로 합니다. 원활한 전환과 운영 중단을 최소화하기 위해 다음 두 단계로 이러한 변경 사항을 구현하고 있습니다.

* Pulse 알림의 즉각적인 가용성: 내보내기 작업 중 권한 오류에 대한 인앱 Pulse 알림을 받게 됩니다. 이렇게 하면 내보내기가 중단되지는 않지만 현재 작업에 영향을 주지 않고 오류에 대해 학습하는 데 도움이 됩니다.
* 4월 25일 작업 일시 중지 구현: **연기됨** - Marketo Measure 사용자의 피드백을 고려한 후 오류가 발생한 시점에 일시 중지 내보내기 작업의 구현을 연기하기로 결정했습니다. 원래 일정은 4월 25일입니다. 우리는 작업 중단이 가장 효과적인 방법이 아닐 수 있다는 것을 알고 있다. Dell은 데이터 무결성을 유지하고 중단을 최소화하는 더 나은 솔루션을 찾기 위해 노력하고 있습니다. Dell은 사용자의 요구 사항에 더 부합하는 솔루션을 제공할 때까지 현재 시스템에 대한 변경 작업을 보류합니다.

_이 문제가 되는 이유_

향상된 데이터 무결성 및 미래 보장 통합: 데이터 손실을 방지하고 정확성을 보장하기 위해 문제의 첫 번째 징후가 발생하면 작업을 중지합니다. 이를 통해 문제를 신속하게 해결하고 데이터 내보내기 품질과 시스템 안정성을 향상시킬 수 있습니다.

즉각적인 가시성: Pulse 알림의 도입으로 권한 오류에 신속하게 대응하여 운영에 미치는 잠재적 영향을 방지할 수 있습니다.

_전환 지원_

이 변경 사항에 적응하는 데 도움이 되도록 [명확한 오류 설명과 포괄적인 문제 해결 단계를 포함하는 설명서를 만들었습니다](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}.

<br>

**LinkedIn 통합에 필요한 작업**

LinkedIn은 최근 업데이트된 버전의 Lead Sync API를 발표했습니다. 중단을 방지하려면 5월 20일까지 Marketo Measure 인스턴스에서 LinkedIn 연결을 다시 인증하십시오.

