---
description: 현재 릴리스 노트 - [!DNL Marketo Measure] - 제품 설명서
title: 현재 릴리스 노트
source-git-commit: 8e8ddd80d69102455fa678a32f31a9fe8319822c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 릴리스 노트: 2023년 {#release-notes-2023}

아래에서는 2023년 릴리스의 새로운 기능과 업데이트된 기능을 모두 확인할 수 있습니다.

## 2분기 릴리스 {#q2-release}

<p>

**Salesforce 패키지 통합**

* 모든 Salesforce 패키지를 사용자 경험과 간소화된 사용을 위해 하나의 포괄적인 패키지로 병합하고 있습니다. V1, V2_EXT 및 보고 패키지는 다음 분기에 사용이 중단되었습니다. 새 패키지는 이전 모든 기능을 결합하므로 더 효율적인 추적과 더 깊은 고객 통찰력을 제공합니다.
* V2 패키지가 이미 설치되어 있는 고객은 이를 새로운 통합 버전으로 업데이트해야 합니다.
* 보고 기능을 향상시키기 위해 두 개의 새 필드를 추가했습니다.
   * form_name: 이제 BT/BAT 개체에서 사용할 수 있으므로 이 필드를 사용하면 양식 이름을 기반으로 보고서를 만들 수 있습니다.
   * user_touchpoint_id: 이 필드를 사용하면 사용자가 고유한 사용자 터치 포인트 카운트로 보고서를 만들 수 있습니다.
* [이 문서](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 기존 보고 패키지에서 보고서 및 대시보드를 다시 만드는 방법에 대한 안내서를 포함합니다.

**Salesforce API 버전 업데이트**

* UserActivityContext 클래스를 포함한 Apex 클래스의 모든 Salesforce API 버전이 지원되는 버전으로 업데이트됩니다. (31.0~57.0)

**새 패키지 설치**

* 새로운 통합 패키지 설치 링크 [여기에서 찾을 수 있습니다.](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 무슨 일이야? {#whats-coming}

<p>

**IP 주소 저장소 변경**

* 개인 정보 고려 사항에 따라 더 이상 시스템에 IP 주소를 저장하지 않습니다. IP 주소의 지역 위치를 계속 식별 및 저장하지만 형식은 변경됩니다(예: &quot;미국&quot;이 &quot;미국&quot;으로).
