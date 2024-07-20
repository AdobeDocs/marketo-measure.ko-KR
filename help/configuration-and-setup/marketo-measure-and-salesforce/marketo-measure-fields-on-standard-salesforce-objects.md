---
unique-page-id: 18874574
description: " 표준 [!DNL Salesforce] 개체 - [!DNL Marketo Measure]의 필드 [!DNL Marketo Measure]개"
title: " 표준 [!DNL Salesforce] 개체의 [!DNL Marketo Measure]개 필드"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 0%

---

# 표준 [!DNL Salesforce] 개체의 [!DNL Marketo Measure] 필드 {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Salesforce] 표준 개체에 추가된 다양한 [!DNL Marketo Measure] 필드에 대해 알아봅니다.

## 계정 {#account}

예측 참여 점수: 이 필드는 ABM 기능과 함께 사용되어 계정의 참여 여부와 관련된 점수를 제공하고 페이지 보기의 최근 상태, 계정과 연결된 연락처 수, 닫힌 팝업 여부 등과 같은 많은 요인을 고려합니다.

## Campaign {#campaign}

추가된 필드는 4개, 단추는 1개, 유효성 검사 규칙은 1개입니다.

UniqueID: 이 필드는 내부적으로 [!DNL Marketo Measure]과(와) 동기화된 다른 캠페인을 추적하는 데 사용됩니다.

구매자 접점 활성화: 이 필드는 오프라인 속성 포함 및 내역 데이터를 위한 캠페인의 실제 동기화를 위한 것입니다.

접점 시작 날짜: 이 필드는 이전 캠페인에 터치포인트를 적용하는 시작 날짜를 설정하는 데 사용됩니다.

접점 종료 날짜: 이 필드는 터치포인트를 기록 캠페인에 적용하는 종료 날짜를 설정하는 데 사용됩니다. 일반적인 예로는 [!DNL Marketo Measure] 이전 버전의 디지털 캠페인을 포함한 다음 종료 날짜를 스크립트가 적용된 날로 설정하는 것입니다.

접점 날짜 벌크 업데이트(단추): 이 단추는 캠페인 멤버십 날짜 또는 즉시 첫 번째 응답 날짜를 참조하므로 캠페인이 동기화될 때 캠페인 멤버의 접점 날짜를 관리하는 데 사용됩니다. 이러한 날짜 필드가 실제 터치포인트 날짜를 정확하게 나타내지 않는 경우 이 버튼을 사용하여 터치포인트 날짜를 설정합니다.

[!DNL Marketo Measure] 속성 업데이트(유효성 검사 규칙): 이 규칙은 패키지 버전 6.0 이후에는 더 이상 사용되지 않습니다.

## 캠페인 멤버 {#campaign-member}

패키지와 함께 추가된 5개의 필드와 1개의 Apex 트리거가 있습니다.

접점 상태(잠재 고객): 기본 켜지지 않은 기능과 관련된 진단 필드입니다. 관련 리드 레코드에 대해 터치포인트가 생성되었는지 여부, 생성되지 않았는지 이유 등을 이해하는 데 사용합니다.

접점 상태(연락처): 기본 켜지지 않은 기능과 관련된 진단 필드입니다. 이를 사용하여 관련 연락처 레코드에 대해 터치포인트가 생성되었는지 여부, 생성되지 않은 경우 그 이유를 파악합니다.

접점 상태(기회): 이 필드는 즉시 사용할 수 없는 기능과 관련된 진단 필드입니다. 이를 사용하여 관련 Opportunity 레코드에 대해 터치포인트가 생성되었는지 여부, 생성되지 않은 경우 그 이유를 파악합니다.

접점 상태 날짜: 진단 필드가 채워진 날짜입니다.

Buyer Touchpoint 날짜: Campaign 개체의 [!UICONTROL Bulk Update Touchpoint date] 단추와 관련되어 있습니다. 이를 사용하면 정의된 터치포인트 날짜를 캠페인 멤버에 적용합니다.

OnCampaignMemberDelete: Campaign 구성원을 삭제할 때 [!DNL Salesforce]이(가) 표시되지 않으므로 정확한 속성 보고에 문제가 발생할 수 있습니다. 캠페인 멤버가 삭제되면 이는 존재하지 않는 해당 캠페인 멤버와 관련된 터치포인트를 제거하도록 [!DNL Marketo Measure]에 알리도록 트리거됩니다.

## 리드 {#lead}

Bizible 계정 필드는 ABM 기능에 대한 Lead-Account 매핑에 사용됩니다. 이 필드를 채워 두 개체 간의 조회 관계를 만듭니다.

## 계정 {#account-1}

ABM 기능에 대한 리드-계정 매핑에 사용됩니다. 이 필드를 채워 두 개체 간의 조회 관계를 만듭니다.

## 기회 {#opportunity}

[!DNL Marketo Measure] 영업 기회 금액: 이 필드는 영업 기회에서 사용자 지정 금액 필드가 사용되는 시나리오에서 사용됩니다. 워크플로우를 사용하여 해당 사용자 지정 필드 값을 [!DNL Marketo Measure] 영업 기회 금액에 매핑한 다음 Buyer Attribution Touchpoint 개체의 매출 속성 필드에 대해 이 필드를 읽습니다.

## 활동 {#activity}

BizibleID: 터치 포인트를 활동 속성 및 호출 추적 지표 통합을 위한 활동과 연결하는 것입니다.

Buyer Touchpoint 날짜: 워크플로우를 통해 채워져 활동 속성 날짜로 사용할 수 있는 필드이며 calltrackingmetrics 통합에 대해 채워져 상호 작용이 언제 발생했는지 알 수 있습니다.
