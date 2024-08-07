---
unique-page-id: 37356027
description: "[!DNL Marketo Measure] CRM 패키지 없는 통합 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] CRM 패키지 없는 통합"
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM 패키지 없는 통합 {#marketo-measure-crm-packageless-integration}

제한된 액세스, CRM 소유권, 가치 창출 시간 연장 또는 법적 영향 등 모든 마케팅 팀이 CRM에서 마케팅 보고를 실행하고자 하거나 액세스 권한이 있는 것은 아닙니다. [!DNL Marketo Measure] 빠른 시작의 경로를 계속 진행하면 가능한 한 CRM에 거의 의존하지 않고 [!DNL Marketo Measure]을(를) 효과적으로 구현하고 실행할 수 있습니다.

## 표준 [!DNL Marketo Measure] 설치 {#standard-marketo-measure-installation}

표준 [!DNL Marketo Measure] 설치를 통해 [!DNL Salesforce] 패키지 또는 [!DNL Microsoft Dynamics] 관리 솔루션을 설치해야 합니다. 설치에는 [!DNL Marketo Measure]이(가) 데이터를 쓸 수 있는 CRM에 추가된 사용자 지정 개체/엔터티 및 사용자 지정 필드가 포함되어 있습니다.

[!DNL Marketo Measure]과(와) 패키지 없는 통합은 CRM에서 사용자 지정 개체/엔터티 또는 사용자 지정 필드를 만들지 않으려는 고객을 위한 것입니다. 외부 Data Warehouse을 사용하는 고객에게도 좋은 옵션입니다.

## 권한 {#permissions}

[!DNL Marketo Measure] CRM 패키지 없는 통합을 사용하려면 리드 및 연락처와 같은 표준 CRM 개체에 액세스해야 합니다. 적절한 데이터 액세스 권한이 있으므로 전용 사용자가 연결된 사용자 역할을 하는 것이 좋습니다.

모든 데이터를 CRM에서 올바르게 가져오려면 다음 보안 및 액세스 가능성 설정이 필요합니다. 전용 사용자의 프로필에 대한 모든 데이터 보기. 이 권한 집합은 [!DNL Marketo Measure]에게 표준 개체에서 데이터를 다운로드하는 데 필요한 액세스 권한을 제공합니다. 이 사용 권한 집합은 프로필 수준입니다.

## ID 공급자 및 데이터 연결 설정 {#setup-your-identity-provider-and-data-connections}

아래 안내서에서 [!DNL Salesforce] 패키지 또는 [!DNL Microsoft Dynamics] 관리 솔루션을 설치하는 단계를 건너뛰고 사용 권한 및 통합 지침만 따릅니다.

[!DNL Salesforce]명의 고객이 [여기](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)를 클릭합니다.

[!DNL Microsoft Dynamics]명의 고객이 [여기](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)를 클릭합니다.

이러한 단계를 완료하면 통합이 작동해야 합니다. 문제가 발생하면 [!DNL Marketo Measure] 담당자 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하십시오.

>[!NOTE]
>
>[!DNL Marketo Measure] CRM 패키지 없는 통합으로 시작하면 나중에 Salesforce 패키지 또는 Microsoft Dynamics 관리 솔루션을 설치할 수 있습니다.
