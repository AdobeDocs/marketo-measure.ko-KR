---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Dynamics를 위한 매출 워크플로우 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] Dynamics를 위한 매출 워크플로우"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Dynamics를 위한 매출 워크플로우 {#marketo-measure-revenue-workflows-for-dynamics}

## 1부: 예상 매출과 실제 매출 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] 즉시 하나(실제 수입)의 표준 수익 필드를 가리키지만 Dynamics에는 두 개의 표준 수익 필드가 있습니다. 실제 매출 및 예상 매출액. Discover Dashboard에서 파이프라인 수익을 사용할 수 있도록 하려면 Opportunity 가 Open 또는 Closed (Won)인지 여부에 따라 Estimated Revenue 또는 Actual Revenue 필드에서 정확한 금액을 캡처하기 위해 사용자 지정 필드 및 워크플로우가 필요합니다.

1단계: Dynamics에서 사용자 지정 영업 기회 금액 필드 만들기

>[!NOTE]
>
>모든 Dynamics 매출 필드에는 기본 필드와 일반 필드가 있습니다. 기본 필드는 무시하십시오.

2단계: 1단계에서 생성된 사용자 지정 영업 기회 금액 필드와 [!DNL Marketo Measure] Opportunity Amount 필드

>[!NOTE]
>
>우리는 이(가) [!DNL Marketo Measure] Dynamics 계정이 있는 Discover 의 Opportunity Amount (bizible2_bizible_opportunity_amount) 필드 Dynamics 고객은 Analytics에 대해 사용자 지정 영업 기회 금액 필드를 만들어야 합니다 [!DNL Marketo Measure] Discover에서 을 가리키도록 했습니다. 완료되면 고객이 업데이트를 수행하는 워크플로우를 만들어야 합니다 **둘 다** a [!DNL Marketo Measure] 기회 금액(bizible2_bizible_opportunity_amount) **및** 사용자 지정 기회 금액 필드. 다음 [!DNL Marketo Measure] Opportunity Amount 필드는 패키지와 함께 제공되지만 사용자 정의 필드를 만들어야 합니다.

금액 워크플로우 지침:

**워크플로우 #1**: 기회 - 업데이트 [!DNL Marketo Measure] 기회 금액 필드 및 사용자 지정 필드 = 예상 수익

이 워크플로우는 예상 매출이 변경될 때마다 열린 기회에 실행되며 [!DNL Marketo Measure] Opportunity Amount 필드 및 사용자 지정 필드가 Estimated Revenue 필드와 같습니다. 워크플로우는 &quot;실시간&quot;을 실행하도록 설정되어야 하지만 &quot;on demand&quot;로 실행하여 오픈 기회를 업데이트할 수도 있습니다.

다음 사항을 제공하십시오. [!DNL Marketo Measure] 사용자 지정 영업 기회 금액 필드의 이름이 있는 연락 지점입니다. 그러면 가 [!DNL Marketo Measure] 사용자 지정 영업 기회 금액 필드의 이름을 포함하는 앱 기회 설정 이렇게 하면 보고에 사용할 필드가 검색 결과에 표시됩니다.

**워크플로우 #2**: 기회 - 업데이트 [!DNL Marketo Measure] 기회 금액 필드 및 사용자 지정 필드 = 실제 수익

이 워크플로우는 실시간으로 실행됩니다. 사용자가 Opportunity 를 닫으면 Opportunity 가 Update 됩니다 [!DNL Marketo Measure] Opportunity 가 Closed 로 잠기기 전에 Opportunity Close 양식에 Actual Revenue 가 추가된 Opportunity Amount 필드 및 사용자 정의 필드입니다.

## 2부: 예상 마감 일자와 실제 마감 일자 비교 {#part-estimated-close-date-vs-actual-close-date}

기본적으로 Dynamics에는 두 개의 스톡 닫기 날짜 필드가 있으므로 기본적으로 파이프라인 매출 데이터를 대시보드에서 사용할 수 없습니다. 예상 마감 일자 및 실제 마감 일자. [!DNL Marketo Measure] 대시보드에서 한 개의 닫기 날짜 필드만 가리키도록 할 수 있으며 현재 실제 마감 날짜를 가리키고 있습니다.

열려 있는 기회에 실제 마감 일자 필드에 데이터가 없으면 대시보드에 열린 기회에 대한 데이터가 표시되지 않습니다. 즉, 두 날짜 필드를 모두 지원하는 기회 단계를 기반으로 워크플로우를 필요로 합니다.

1. Opportunity Object에 Custom Close Date 필드를 생성합니다(예: [!DNL Marketo Measure] 사용자 지정 종료 날짜).
1. 워크플로우를 만들어 업데이트 [!DNL Marketo Measure] 영업 기회의 개설 또는 마감 여부에 따라 예상 마감 일자 또는 실제 마감 일자부터 일자가 있는 사용자 지정 마감 일자 필드가 표시됩니다(워크플로우를 실시간으로 실행하도록 저장하되 현재 개설 옵션을 모두 갱신하려면 적어도 한 번 &quot;요청 시&quot;를 실행해야 함).
1. 워크플로우를 테스트하고 작동하는지 확인합니다.
1. 고객 - 사용자 지정 종료 날짜 API 이름을 [!DNL Marketo Measure].
1. [!DNL Marketo Measure] 를 업데이트하려면 [!DNL Marketo Measure] 앱 설정을 가리키도록 설정 [!DNL Marketo Measure] 대시보드의 사용자 지정 닫기 날짜 필드.

   위의 단계를 완료하면 워크플로우를 실행하여 사용자 지정 을 모두 업데이트해야 합니다 [!DNL Marketo Measure] Opp 금액 필드 및 [!DNL Marketo Measure] 올바른 데이터를 반영하기 위한 이전 기회의 사용자 지정 마감 날짜 필드입니다. 이렇게 하면 수정된 설정/기준 필드가 변경되므로 팀에 문의하여 문제가 있는지 확인하십시오.

종결된 기회를 업데이트하는 방법..

1. 이후에 중단되었던 영업 기회 파악 [!DNL Marketo Measure] 워크플로우가 활성 상태가 될 때까지 시작 날짜입니다. 워크플로우를 통해 업데이트해야 하는 과거 기회 그룹입니다.
1. 모든 레코드를 Excel로 내보냅니다.
1. Excel 파일을 열고 컨텐츠를 활성화합니다.
1. 실제 마감 날짜 데이터 복사 [!DNL Marketo Measure] 사용자 지정 종료 날짜.
1. 실제 매출 데이터를에 복사 [!DNL Marketo Measure] 사용자 지정 영업 기회 금액 **및** [!DNL Marketo Measure] 영업 기회 금액(두 개의 필드가 있습니다.)
1. 파일을 저장합니다.
1. 파일을 가져옵니다. Dynamics에서는 이 파일을 업데이트할 기존 레코드가 있는 파일로 인식합니다.
1. 가져오기 파일에 대한 오류를 확인합니다.

>[!NOTE]
>
>이 문서에 설명된 워크플로우는 필드 업데이트를 수행하는 한 가지 방법이므로 [!DNL Marketo Measure] 는 Discover에서 올바른 데이터를 표시할 수 있습니다. 같은 일을 완수하는 또 다른 방법이 있다면, 그것을 할 수 있습니다. 기본적으로 이러한 워크플로우에서 필요한 것은 다음을 수행하는 일종의 워크플로우입니다.
>
> * Opp = Open인 경우, 사용자 지정 닫기 날짜 필드, 사용자 지정 옵프 금액 필드 및 [!DNL Marketo Measure] 예상 마감 일자 및 예상 매출과 동일한 opp 금액 필드.
> * Opp = Closed Won인 경우 사용자 정의 마감 날짜 필드, 사용자 정의 opp 금액 필드 및 [!DNL Marketo Measure] 금액 필드를 실제 마감 일자 및 실제 매출과 같게 각각 설정합니다.

