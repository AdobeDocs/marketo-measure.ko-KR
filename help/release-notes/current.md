---
description: 최신 릴리스 정보 - [!DNL Marketo Measure] - 제품 설명서
title: 최신 릴리스 정보
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 릴리스 노트: 2023 {#release-notes-2023}

아래에는 2023년 릴리스의 모든 새로운 기능과 업데이트된 기능이 있습니다.

## 2분기 릴리스 {#q2-release}

<p>

**Salesforce 패키지 통합**

* 향상된 사용자 경험과 간소화된 사용을 위해 모든 Salesforce 패키지를 포괄적인 단일 패키지로 병합하고 있습니다. V1, V2_EXT 및 보고 패키지가 다음 분기에 중단됩니다. 새로운 패키지는 이전의 모든 기능을 결합하므로 보다 효율적인 추적을 수행하고 보다 심층적인 고객 통찰력을 얻을 수 있습니다.
* 이미 V2 패키지를 설치한 고객은 이 패키지를 새로운 통합 버전으로 업데이트해야 합니다.
* 보고 기능을 향상시키기 위해 두 개의 새 필드가 추가되었습니다.
   * form_name: 이제 BT/BAT 객체에서 사용할 수 있으며, 이 필드를 통해 사용자는 양식 이름을 기반으로 보고서를 작성할 수 있습니다.
   * user_touchpoint_id: 이 필드를 사용하면 사용자가 고유한 사용자 터치포인트 카운트로 보고서를 만들 수 있습니다.
* [이 문서](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 기존 보고 패키지에서 보고서 및 대시보드를 다시 만드는 방법에 대한 안내서를 포함합니다.

**Salesforce API 버전 업데이트**

* UserActivityContext 클래스를 비롯한 Apex 클래스의 모든 Salesforce API 버전이 지원되는 버전으로 업데이트됩니다. (31.0~57.0)

**새 패키지 설치**

* 새로운 통합 패키지 설치 링크 [은(는) 여기에서 찾을 수 있음](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 뭐가 오는데? {#whats-coming}

<p>

**IP 주소 스토리지 변경**

* 개인 정보 보호 고려 사항에 따라 시스템에 더 이상 IP 주소를 저장하지 않습니다. IP 주소의 지리적 위치를 계속 식별하고 저장하지만 형식이 변경됩니다(예: &quot;미국&quot;에서 &quot;미국&quot;으로 변경).
