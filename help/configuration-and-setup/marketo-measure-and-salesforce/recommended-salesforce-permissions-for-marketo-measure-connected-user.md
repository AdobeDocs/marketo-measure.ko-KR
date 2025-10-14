---
unique-page-id: 18874696
description: ' [!DNL Marketo Measure] 연결된 사용자에 대한 권장 [!DNL Salesforce] 권한 - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] 연결된 사용자에 대해  [!DNL Salesforce] 권한 권장'
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# 연결된 [!DNL Marketo Measure]명의 사용자에게 [!DNL Salesforce] 권한 권장 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure]은(는) [!DNL Marketo Measure] 앱 내에서 연결된 [!DNL Salesforce] 사용자를 통해 데이터를 보내고 받습니다.

터치포인트 데이터를 [!DNL Salesforce] 인스턴스로 푸시하려면 연결된 사용자가 [!DNL Marketo Measure]개의 사용자 지정 개체(즉, Buyer Touchpoint 및 Buyer Attribution Touchpoint)와 리드 및 연락처와 같은 표준 [!DNL Salesforce]개의 개체에 액세스할 수 있어야 합니다. Salesforce에서 [[!DNL Marketo Measure] 을(를) 참조하십시오](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 관리자 사용자 라이선스는 기본적으로 필요한 데이터 권한이 있는 경우가 많으므로 연결된 사용자 역할을 할 수 있습니다. 하지만 귀하의 팀은 [!DNL Marketo Measure]이(가) 인스턴스에 미치는 영향을 추적하기 위해 통합 사용자 또는 전용 [!DNL Salesforce] 사용자 라이선스를 사용하는 것을 선호할 수 있습니다.

[!DNL Marketo Measure] 데이터가 정확하게 흐르도록 하려면 다음 권한을 사용하는 것이 좋습니다.

* 전용 사용자에 대한 [!DNL Marketo Measure] 관리자 권한 집합

관리되는 권한 집합을 사용하면 SFDC 관리자는 [!DNL Marketo Measure] 개체에서 레코드를 만들고, 읽고, 쓰고, 삭제할 수 있습니다.

* 전환된 잠재 고객 사용 권한 집합 보기 및 편집

이를 통해 [!DNL Marketo Measure]이(가) 연락처로 전환된 후 리드를 장식할 수 있습니다. 이 권한 집합을 활성화하지 않으면 상당한 데이터 추적 간격이 발생할 수 있습니다. [[!DNL Salesforce Trailblazer] 커뮤니티](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5)에서 자세한 정보를 찾을 수 있습니다.

* [!DNL Salesforce] 마케팅 사용자 확인란

[!UICONTROL Marketing User] 확인란을 통해 사용자는 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 사용자는 캠페인 및 고급 캠페인 설정만 보고, 단일 리드 또는 연락처에 대한 캠페인 내역을 편집하고, 캠페인 보고서를 실행할 수 있습니다. [!DNL Marketo Measure]은(는) campaign 개체를 읽고 쓸 수 있어야 합니다.

**추가 문제 해결**

[!DNL Marketo Measure]에서 데이터를 읽거나 쓰는 데 여전히 문제가 있는 경우 다음 사항을 조사하는 것이 도움이 될 수 있습니다.

* [!DNL Salesforce]개 큐 액세스

전용 사용자가 대기열의 리드에 액세스할 수 없는 경우 [!DNL Marketo Measure] 데이터로 리드를 수정할 수 없습니다. 대기열에 액세스할 수 있는 계층 구조에 역할을 두거나 사용자에게 개별적으로 액세스 권한을 부여하면 됩니다.

* 필드 수준 보안 및 접근성

필드 수준 보안과 필드 접근성은 관련되지만 몇 가지 주요 차이점이 있습니다. 필드 수준 보안은 지정된 프로필에 대한 필드 가시성을 정의하는 반면 필드 접근성은 필드 수준 보안 및 페이지 레이아웃 구성을 기반으로 필드를 편집할 수 있는지 여부를 결정합니다. [!DNL Marketo Measure] 패키지의 사용 권한 집합을 사용하여 필요한 필드 개체 보안 설정을 받습니다. 경우에 따라 올바른 필드 액세스 가능성을 가지려면 연결된 사용자가 페이지 레이아웃에 [!DNL Marketo Measure] 필드를 보유해야 합니다. 레이아웃의 [!DNL Marketo Measure] 필드를 통해 [!DNL Marketo Measure] 데이터를 [!DNL Salesforce]에 매핑할 수 있습니다. 이는 특정 [!DNL Salesforce] 환경에 따라 다릅니다.

모든 조직의 [!DNL Salesforce]에는 개별 요구 사항이 있지만 [!DNL Marketo Measure] 액세스 요구 사항과 보안 프로토콜의 균형을 맞추기 위한 요구 사항을 제공합니다. [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 언제든지 문의하세요.
