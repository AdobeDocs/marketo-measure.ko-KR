---
unique-page-id: 18874696
description: 권장 [!DNL Salesforce] 에 대한 권한 [!DNL Marketo Measure] 연결된 사용자 - [!DNL Marketo Measure] - 제품 설명서
title: 권장 [!DNL Salesforce] 에 대한 권한 [!DNL Marketo Measure] 연결된 사용자
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# 권장 [!DNL Salesforce] 에 대한 권한 [!DNL Marketo Measure] 연결된 사용자 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 연결된 데이터를 통해 전송 및 수신 [!DNL Salesforce] 내 사용자 [!DNL Marketo Measure] 앱.

터치 포인트 데이터를 [!DNL Salesforce] 예를 들어 연결된 사용자는 [!DNL Marketo Measure] 사용자 정의 객체(예: Buyer Touchpoint 및 Buyer Attribution Touchpoint)와 표준 [!DNL Salesforce] 리드 및 연락처와 같은 객체(참조) [[!DNL Marketo Measure] Salesforce에서](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 관리자 사용자 라이센스는 기본적으로 필요한 데이터 권한이 있는 경우가 많으므로 연결된 사용자로 사용할 수 있습니다. 그러나 팀에서는 통합 사용자 또는 전용 사용자를 사용하는 것을 선호할 수 있습니다 [!DNL Salesforce] 사용자 라이선스 : [!DNL Marketo Measure] 참조하십시오.

다음 권한을 사용하여 다음을 확인하는 것이 좋습니다 [!DNL Marketo Measure] 데이터가 정확하게 흐릅니다.

* [!DNL Marketo Measure] 전용 사용자에 대한 관리자 권한 집합

관리 권한 집합에서는 SFDC 관리자가 레코드를 작성, 읽기, 쓰기, 삭제할 수 있는 기능을 제공합니다. [!DNL Marketo Measure] 개체.

* 변환된 리드 권한 집합 보기 및 편집

이렇게 하면 [!DNL Marketo Measure] 연락처로 전환한 후에 리드를 장식하기 위해. 이 권한 세트가 활성화되어 있지 않으면 상당한 데이터 추적 차이가 있을 수 있습니다. 자세한 내용은 [[!DNL Salesforce Trailblazer] 커뮤니티](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] 마케팅 사용자 확인란

다음 [!UICONTROL Marketing User] 확인란을 통해 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 사용자는 캠페인 및 고급 캠페인 설정만 보고, 단일 리드 또는 연락처에 대한 캠페인 내역을 편집하고, 캠페인 보고서를 실행할 수 있습니다. [!DNL Marketo Measure] campaign 개체를 읽고 쓸 수 있어야 합니다.

**추가 문제 해결**

If [!DNL Marketo Measure] 가 여전히 데이터를 읽거나 쓰는 데 문제가 있는 경우 다음을 조사하는 데 도움이 될 수 있습니다.

* 액세스 권한 [!DNL Salesforce] 큐

전용 사용자가 큐의 리드에 액세스할 수 없는 경우 리드를 수정할 수 없습니다 [!DNL Marketo Measure] 데이터. 대기열에 액세스할 수 있는 계층에서 역할을 가지거나 개별적으로 사용자 액세스 권한을 부여하여 이를 수행할 수 있습니다.

* 필드 수준 보안 및 액세스 가능성

필드 수준 보안 및 필드 액세스 가능성은 관련이 있지만 몇 가지 주요 차이점이 있습니다. 필드 수준 보안은 지정된 프로필에 대한 필드 가시성을 정의하는 반면, 필드 액세스 가능성은 필드 수준 보안 및 페이지 레이아웃 구성을 기반으로 필드를 편집할 수 있는지 여부를 결정합니다. 사용 [!DNL Marketo Measure] 패키지의 권한 집합은 필요한 필드 개체 보안 설정을 받게 됩니다. 경우에 따라 올바른 필드 액세스 가능성이 있으려면 연결된 사용자가 [!DNL Marketo Measure] 페이지 레이아웃의 필드. [!DNL Marketo Measure] 레이아웃의 필드에서 [!DNL Marketo Measure] 매핑할 데이터 [!DNL Salesforce]. 이는 특정 항목에 따라 달라집니다 [!DNL Salesforce] 환경.

모든 조직의 [!DNL Salesforce] 개별 요구 사항을 가지고 있지만, Dell은 사용자에게 균형을 맞추기 위한 요구 사항을 제공합니다 [!DNL Marketo Measure] 보안 프로토콜로 액세스 요구 사항 망설이지 말고 연락하세요 [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.
