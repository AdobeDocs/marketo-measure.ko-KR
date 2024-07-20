---
description: "[!DNL Marketo Measure] 101 보고서 개요 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 101 보고서 개요"
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# [!DNL Marketo Measure] 101 보고서 개요 {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure] 및 [!DNL Salesforce]을(를) 사용하는 모든 [!DNL Marketo Measure] 고객은 SFDC 인스턴스 내의 &#39;구매자 터치포인트 보고서&#39; 폴더에 액세스할 수 있습니다. 이 폴더에는 Buyer Touchpoint 데이터를 사용하여 보고를 시작하는 데 도움이 되는 미리 작성된 보고서가 많이 포함되어 있습니다.

![](assets/bizible-101-reports-overview-1.png)

이러한 보고서의 대부분은 특정 보고 목표를 이미 설정했지만, 대부분의 보고 요구 사항을 다루는 세 가지 주요 보고서 유형으로 표현되는 여섯 개의 &quot;_[!DNL Marketo Measure]101..._&quot;이(가) 있습니다.

* 구매자 터치포인트로 리드
* 구매자 터치포인트가 있는 사용자 [!DNL Marketo Measure]명
* 기회가 있는 구매자 속성 접점

![](assets/bizible-101-reports-overview-2.png)

이러한 보고서는 만들려는 [!DNL Marketo Measure] 관련 보고서에 필요한 기본 필드와 인프라를 제공합니다. 신규 고객 및 기존 고객 모두 마케팅 기여도 분석 질문을 탐색할 때 이러한 보고서부터 시작할 것을 권장합니다. 아래에는 여섯 개의 &quot;_[!DNL Marketo Measure]101..._&quot; 보고서에 대한 설명이 있습니다.

_구매자 터치포인트 보고서 폴더 또는 해당 폴더 내에 있는 6개의 &quot;_[!DNL Marketo Measure] 101..._&quot; 보고서를 찾을 수 없는 경우 지원 팀에 문의하세요._

**구매자 터치포인트로 리드** | 다음 두 가지 변형, 리드 및 구매자 터치포인트에 대해 보고합니다. 이 보고서는 동일한 기본 보고서 유형을 사용하지만 다른 지표(잠재 고객 ID와 마케팅 채널)로 그룹화하여 데이터에 대한 두 가지 주요 보기를 제공합니다. 이 보고서 유형은 상위 단계 보고용으로 설계되었으며 리드가 마케팅 활동에 어떻게 참여하는지를 살펴볼 때 이상적입니다. 사용자 지정 전에 아래 두 보고서에 다음이 표시됩니다.

**[!DNL Marketo Measure]101: 채널별 잠재 고객** | 마케팅 채널이 리드 및 추가 참여 생성에 어떤 영향을 미치는지에 대한 높은 수준의 보기.
**[!DNL Marketo Measure]101: ID별 리드** | 여기에는 잠재 고객 스토리가 표시되며, 보다 세분화된 보고서로서 각 개별 잠재 고객과 관련 구매자 터치포인트를 보여 줍니다.

**구매자 터치포인트와의 리드/연락처** | 이러한 보고서를 일반적으로 [!DNL Marketo Measure] 개인 보고서라고 합니다. 위에서 언급한 보고서의 잠재 고객 개체가 아닌 [!DNL Marketo Measure] 사용자 지정 개체 _[!DNL Marketo Measure]Person_&#x200B;을(를) 사용합니다.

[!DNL Marketo Measure]명의 사용자 개체는 잠재 고객 개체와 연락처 개체를 함께 연결합니다. 기본적으로 [!DNL Salesforce]은(는) 동일한 보고서에서 리드 및 연락처 개체를 사용하여 보고서를 만들 수 있는 옵션을 제공하지 않습니다. [!DNL Marketo Measure]명의 사용자는 개인 고유 식별자인 전자 메일을 사용하여 잠재 고객 및 연락처 개체와 관련하여 동일한 보고서 내에서 잠재 고객 및 연락처 관련 구매자 접점에 대해 보고할 수 있습니다. 이 보고서 유형은 가장 포괄적인 접점 보고 수준이므로 [!DNL Marketo Measure] 계정 설정의 유효성을 검사할 때 이상적입니다.

다음 두 보고서 변형은 동일한 보고서 유형을 사용하지만 개인 ID(이메일)와 마케팅 채널 등 다른 지표로 그룹화됩니다. 리드 및 연락처가 마케팅 활동에 어떻게 참여하는지를 살펴볼 때 유용한 단계/단계 중간 보고서의 맨 위입니다. 사용자 지정 전에 아래 두 보고서에 다음이 표시됩니다.

**[!DNL Marketo Measure]101: 채널별 잠재 고객/연락처** | 마케팅 채널이 리드 또는 연락처 생성 및 추가 참여에 어떤 영향을 미치는지에 대한 높은 수준의 보기. 이 보고서는 마케팅 채널 전반의 총 참여 횟수와 Salesforce 인스턴스 내에서 새로운 이름을 만들어내는 마케팅 채널을 파악하고자 할 때 이상적입니다.
**[!DNL Marketo Measure]101: ID별 잠재 고객/연락처** | 여기에는 각 [!DNL Marketo Measure]명의 스토리가 표시되며, 훨씬 세분화된 보고서로서 잠재 고객 또는 연락처일 때 터치포인트가 발생했는지 여부에 관계없이 각 개인과 구매자 터치포인트를 표시합니다.

**구매자 속성 터치포인트를 사용하는 기회** | 마지막 두 개의 &quot;_[!DNL Marketo Measure]101..._&quot; 보고서는 Opportunity와 관련된 Buyer Attribution Touchpoint 데이터를 표시하는 단계 보고서의 맨 아래에 있습니다. 이러한 보고서의 주요 차별화 요소는 매출과 같은 영업 기회 및 영업 기회 수준 데이터와 관련된 _구매자 속성 접점_&#x200B;을 기반으로 구축되었다는 것입니다. Opportunity 또는 Attribute 수익에 대해 보고하려는 경우 항상 이 보고서 유형을 사용해야 합니다. 아래 두 보고서는 동일한 보고서 유형을 사용하지만, 영업 기회 ID와 마케팅 채널이라는 서로 다른 지표로 그룹화됩니다. 사용자 지정 전에 아래 두 보고서에 다음이 표시됩니다.

**[!DNL Marketo Measure]101: 채널별 기회** | 마케팅 채널이 Opportunity 전반에서 기여하는 매출에 어떤 영향을 주고 받는지에 대한 높은 수준의 관점.
**[!DNL Marketo Measure]101: ID별 기회** | 이 세분화된 보고서 버전은 Opportunity 의 전체 여정을 보여 줍니다. 이 보고서에서는 다양한 속성 모델을 통해 Opportunity 와 관련된 모든 Buyer Attribution Touchpoint 및 해당 속성 매출을 볼 수 있습니다.

&quot;_[!DNL Marketo Measure]101..._&quot; 보고서를 보고 요구 사항에 대한 템플릿으로 처리하는 것이 좋습니다. 위의 보고서 중 하나로 시작하면 시간을 절약하고 [!DNL Marketo Measure] 데이터와 관련된 올바른 필드를 사용하여 작업하고 있는지 확인합니다. 보고서의 원래 변형을 유지하기 위해 &quot;_[!DNL Marketo Measure]101..._&quot; 템플릿을 사용자 지정할 때마다 항상 &quot;다른 이름으로 저장&quot;하도록 하십시오.

&quot;Buyer Touchpoint 보고서&quot; 폴더는 [!DNL Marketo Measure] 보고를 시작하는 데 도움이 되도록 디자인되었습니다. 실행 가능한 보고서의 경우 보고 요구 사항에 맞게 보고서를 사용자 지정해야 합니다. 보고서 내의 레코드(및 관련 터치포인트)가 보고 목표에 맞게 정렬되도록 하려면 필요한 필터를 추가해야 합니다.

&quot;_[!DNL Marketo Measure]101..._&quot; 보고서를 잘 알고 있는 경우 사용자 지정 보고 요구 사항을 더 많이 충족하기 위해 사용자 지정 보고서 유형에서 다시 만들 수 있습니다. [[!DNL Marketo Measure] 사용자 지정 보고서 유형](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md)을(를) 만들면 다른 CRM 보고서에서 일반적으로 사용할 수 있는 사용자 지정 필드를 가져올 수 있습니다. 이를 통해 [!DNL Marketo Measure] 보고를 다음 수준으로 전환할 수 있습니다.
