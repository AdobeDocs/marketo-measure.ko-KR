---
description: 최신 릴리스 정보 - [!DNL Marketo Measure]
title: 최신 릴리스 정보
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 4a3b8a1df9d8a675d977b08693b9d7facb64bc02
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# 릴리스 노트: 2024 {#release-notes-2024}

2024 릴리스의 모든 새로운 기능 및 업데이트된 기능은 아래를 참조하십시오.

## 2분기 릴리스 {#q2-release}

<p>

**서드파티 쿠키 단계적 축소에 대한 응답으로 Marketo Measure 기능 사용 중단**

증가하는 개인 정보 보호 문제에 대응하여 서드파티 쿠키는 Google Chrome의 2024년 3분기 최종 기한이 종료를 알리는 등 단계적으로 폐지되고 있습니다. Marketo Measure은 타사 쿠키, 특히 Google/DoubleClick 노출 쿠키에 의존하는 도메인 간 추적 및 뷰스루 기여도 분석에 따른 특정 기능을 더 이상 사용하지 않습니다. 이 변경 사항은 다른 Marketo Measure 기능이나 자사 쿠키의 사용에 영향을 주지 않습니다. Google의 타임라인에 따라 이러한 기능은 6월 1일까지 더 이상 사용되지 않을 것으로 예상되지만, 이 날짜 이전에 수집된 데이터는 여전히 고객이 액세스할 수 있습니다.

* [Marketo Measure의 타사 쿠키 사용 중단에 적응하기](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure 쿠키](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**향상된 오류 처리에 대한 단계별 롤아웃**

권한 오류에 대한 즉각적인 인앱 펄스 알림부터 시작하여 내보내기 작업에 대한 향상된 오류 처리의 단계별 롤아웃을 소개하고 있으며, 4월 25일에 오류 시점에서 내보내기 작업이 일시 중지되는 새로운 접근 방식으로 전환하는 중입니다. 이러한 변경은 데이터 무결성 및 가시성을 향상시켜 사용자를 위한 보다 원활하고 안정적인 데이터 관리 프로세스를 보장하는 것을 목표로 합니다. 원활한 전환과 운영 중단을 최소화하기 위해 다음 두 단계로 이러한 변경 사항을 구현하고 있습니다.

* Pulse 알림의 즉각적인 가용성: 내보내기 작업 중 권한 오류에 대한 인앱 Pulse 알림을 받게 됩니다. 이렇게 하면 내보내기가 중단되지는 않지만 현재 작업에 영향을 주지 않고 오류에 대해 학습하는 데 도움이 됩니다.
* 4월 25일 일시 중지 작업 구현: 4월 25일부터 내보내기 작업 중에 시스템에 권한 오류가 발생하면 작업을 일시 중지하여 데이터를 건너뛸 수 없습니다. 모든 문제에 대한 알림을 받게 되며, 권한이 수정되면 중단된 지점에서 내보내기 작업이 원활하게 다시 시작됩니다.

_이것이 중요한 이유_

향상된 데이터 무결성 및 미래 보장 통합: 데이터 손실을 방지하고 정확성을 보장하기 위해 문제의 첫 번째 징후가 발생하면 작업을 중지합니다. 이를 통해 문제를 신속하게 해결하고 데이터 내보내기 품질과 시스템 안정성을 향상시킬 수 있습니다.

즉각적인 가시성: Pulse 알림의 도입으로 권한 오류에 신속하게 대응하여 운영에 미치는 잠재적 영향을 방지할 수 있습니다.

_전환 지원_

이러한 변화에 적응하는 데 도움이 되도록, [설명서를 만들었습니다.](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} 명확한 오류 설명 및 포괄적인 문제 해결 단계.

**linkedIn 통합에 필요한 작업**

LinkedIn은 최근 업데이트된 버전의 Lead Sync API를 발표했습니다. 중단을 방지하려면 5월 20일까지 Marketo Measure 인스턴스에서 LinkedIn 연결을 다시 인증하십시오.
