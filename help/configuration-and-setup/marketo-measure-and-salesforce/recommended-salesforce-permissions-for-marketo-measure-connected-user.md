---
unique-page-id: 18874696
description: 추천 [!DNL Salesforce] 다음에 대한 권한 [!DNL Marketo Measure] 연결된 사용자 - [!DNL Marketo Measure] - 제품 설명서
title: 추천 [!DNL Salesforce] 다음에 대한 권한 [!DNL Marketo Measure] 연결된 사용자
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# 추천 [!DNL Salesforce] 다음에 대한 권한 [!DNL Marketo Measure] 연결된 사용자 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 연결된 을(를) 통해 데이터 전송 및 수신 [!DNL Salesforce] 다음 내의 사용자 [!DNL Marketo Measure] 앱.

터치 포인트 데이터를 로 푸시하려면 [!DNL Salesforce] 인스턴스: 연결된 사용자는 다음에 대한 액세스 권한이 있어야 합니다. [!DNL Marketo Measure] 사용자 정의 객체(예: 구매자 접점 및 구매자 속성 접점)와 표준 [!DNL Salesforce] 잠재 고객 및 연락처 등의 오브젝트(참조) [[!DNL Marketo Measure] Salesforce에서](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 관리자 사용자 라이선스는 기본적으로 필요한 데이터 권한을 가진 경우가 많으므로 연결된 사용자 역할을 할 수 있습니다. 그러나 팀은 통합 사용자 또는 전용 을 사용하는 것을 선호할 수 있습니다 [!DNL Salesforce] 의 영향을 추적할 사용자 라이선스 [!DNL Marketo Measure] 을 참조하십시오.

다음을 확인하려면 다음 권한을 사용하는 것이 좋습니다. [!DNL Marketo Measure] 데이터 흐름이 정확함:

* [!DNL Marketo Measure] 전용 사용자에 대한 관리자 권한 집합

관리 권한 집합은 SFDC 관리자에게 레코드 만들기, 읽기, 쓰기 및 삭제 기능을 제공합니다. [!DNL Marketo Measure] 개체.

* 전환된 잠재 고객 사용 권한 집합 보기 및 편집

이렇게 하면 [!DNL Marketo Measure] 잠재 고객을 연락처로 전환한 후 장식합니다. 이 권한 집합을 사용하지 않으면 상당한 데이터 추적 간격이 발생할 수 있습니다. 다음에서 자세한 정보를 찾을 수 있습니다. [[!DNL Salesforce Trailblazer] 커뮤니티](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] 마케팅 사용자 확인란

다음 [!UICONTROL Marketing User] 확인란을 통해 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 사용자는 캠페인 및 고급 캠페인 설정만 보고, 단일 리드 또는 연락처에 대한 캠페인 내역을 편집하고, 캠페인 보고서를 실행할 수 있습니다. [!DNL Marketo Measure] campaign 개체를 읽고 쓸 수 있어야 합니다.

**추가 문제 해결**

If [!DNL Marketo Measure] 에서 데이터를 읽거나 쓰는 데 여전히 문제가 있습니다. 다음 사항을 조사하는 것이 유용할 수 있습니다.

* 액세스 대상: [!DNL Salesforce] 큐

전용 사용자가 대기열의 리드에 액세스할 수 없는 경우 를 사용하여 리드를 수정할 수 없습니다. [!DNL Marketo Measure] 데이터. 대기열에 액세스할 수 있는 계층 구조에 역할을 두거나 사용자에게 개별적으로 액세스 권한을 부여하면 됩니다.

* 필드 수준 보안 및 접근성

필드 수준 보안과 필드 접근성은 관련되지만 몇 가지 주요 차이점이 있습니다. 필드 수준 보안은 지정된 프로필에 대한 필드 가시성을 정의하는 반면 필드 접근성은 필드 수준 보안 및 페이지 레이아웃 구성을 기반으로 필드를 편집할 수 있는지 여부를 결정합니다. 사용 [!DNL Marketo Measure] 패키지의 권한 집합은 필요한 필드 개체 보안 설정을 받습니다. 경우에 따라 올바른 필드 접근성을 가지려면 연결된 사용자가 [!DNL Marketo Measure] 페이지 레이아웃의 필드. [!DNL Marketo Measure] 레이아웃의 필드를 사용하여 [!DNL Marketo Measure] 매핑할 데이터 [!DNL Salesforce]. 이는 귀하의 특정 항목에 따라 다릅니다 [!DNL Salesforce] 환경.

모든 조직 [!DNL Salesforce] 은(는) 개별적인 요구 사항을 가지고 있지만, 당사는 귀하에게 균형을 맞추기 위한 요구 사항을 제공합니다. [!DNL Marketo Measure] 보안 프로토콜로 액세스 요구 사항을 충족합니다. 주저하지 말고 다음 대상에게 연락하십시오. [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
