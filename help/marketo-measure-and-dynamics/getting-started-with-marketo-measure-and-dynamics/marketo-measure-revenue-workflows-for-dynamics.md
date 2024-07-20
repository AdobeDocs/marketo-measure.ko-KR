---
unique-page-id: 37356132
description: '" [!DNL Marketo Measure]" Dynamics에 대한 [!DNL Marketo Measure] 수익 워크플로"'
title: "[!DNL Marketo Measure] Dynamics용 수익 워크플로"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# Dynamics용 수익 워크플로 [!DNL Marketo Measure]개 {#marketo-measure-revenue-workflows-for-dynamics}

## 1부: 예상 수익 대 실제 수익 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure]이(가) 즉시 하나의 표준 수익 필드를 가리키지만(실제 수익) Dynamics에는 실제 수익과 예상 수익이라는 두 개의 표준 수익 필드가 있습니다. Discover Dashboard에서 파이프라인 매출을 사용하려면 Opportunity 가 Open 인지 Closed (Won) 인지에 따라 Estimated Revenue 또는 Actual Revenue 필드에서 정확한 금액을 캡처하는 사용자 정의 필드와 워크플로우가 필요합니다.

1단계: Dynamics에서 사용자 지정 영업 기회 금액 필드 만들기

>[!NOTE]
>
>모든 Dynamics 매출 필드에는 기본 필드와 일반 필드가 있습니다. 기본 필드는 무시합니다.

2단계: 1단계에서 만든 사용자 지정 영업 기회 금액 필드와 [!DNL Marketo Measure] 영업 기회 금액 필드를 모두 업데이트하는 워크플로우를 만듭니다.

>[!NOTE]
>
>Dynamics 계정이 있는 검색에서 [!DNL Marketo Measure] 영업 기회 금액(bizible2_bizible_opportunity_amount) 필드를 지정할 수 없습니다. Dynamics 고객은 [!DNL Marketo Measure]이(가) Discover를 가리키도록 사용자 지정 영업 기회 금액 필드를 만들어야 합니다. 완료되면 고객은 **모두** [!DNL Marketo Measure] 영업 기회 금액(bizible2_bizible_opportunity_amount) **및** 사용자 지정 영업 기회 금액 필드를 업데이트하는 워크플로우를 만들어야 합니다. [!DNL Marketo Measure] 영업 기회 금액 필드는 패키지와 함께 제공되지만 사용자 지정 필드를 만들어야 합니다.

금액 워크플로우 지침:

**워크플로 #1**: 영업 기회 - [!DNL Marketo Measure] 영업 기회 금액 필드 및 사용자 지정 필드 업데이트 = 예상 수익

이 워크플로우는 예상 수익이 변경될 때마다 열려 있는 기회에서 실행되고 [!DNL Marketo Measure] 기회 금액 필드와 사용자 지정 필드를 예상 수익 필드와 동일하게 업데이트합니다. 워크플로는 &quot;실시간&quot;으로 실행되도록 설정되어야 하지만 열려 있는 기회를 업데이트하기 위해 &quot;온디맨드&quot;로 실행될 수도 있습니다.

사용자 지정 영업 기회 금액 필드의 이름으로 [!DNL Marketo Measure] 연락처를 제공하십시오. [!DNL Marketo Measure] 앱 영업 기회 설정을 업데이트하여 사용자 지정 영업 기회 금액 필드의 이름을 포함합니다. 보고에 사용할 필드를 검색합니다.

**워크플로 #2**: 영업 기회 - [!DNL Marketo Measure] 영업 기회 금액 필드 및 사용자 지정 필드 업데이트 = 실제 수익

이 워크플로우는 사용자가 영업 기회를 닫고 영업 기회가 종료된 것으로 잠기기 전에 영업 기회 금액 필드 [!DNL Marketo Measure]과(와) 영업 기회 종료 양식에 추가된 실제 수익으로 사용자 정의 필드를 업데이트할 때 시작됩니다.

## 2부: 예상 마감 일자 대 실제 마감 일자 {#part-estimated-close-date-vs-actual-close-date}

기본적으로 Dynamics에는 예상 마감 일자 및 실제 마감 일자의 두 가지 재고 마감 일자 필드가 있으므로 기본적으로 파이프라인 매출 데이터를 대시보드에서 사용할 수 없습니다. [!DNL Marketo Measure]은(는) 대시보드에 있는 하나의 종료 날짜 필드만 지정할 수 있으며 실제 종료 날짜를 가리키고 있습니다.

개설 기회에 실제 마감 일자 필드에 데이터가 없는 경우 대시보드에 개설 기회에 대한 데이터가 없습니다. 즉, 두 날짜 필드를 모두 지원하려면 영업 기회 단계를 기반으로 한 워크플로우가 필요합니다.

1. 영업 기회 개체([!DNL Marketo Measure] 사용자 지정 종료 날짜)에 사용자 지정 종료 날짜 필드를 만듭니다.
1. [!DNL Marketo Measure] 사용자 지정 닫기 날짜 필드를 영업 기회가 열려 있는지 아니면 닫혀 있는지에 따라 예상 종료 날짜 또는 실제 종료 날짜의 날짜로 업데이트하는 워크플로를 만듭니다. 워크플로를 실시간으로 실행하려면 저장해야 하지만 현재 열려 있는 모든 영업 기회를 업데이트하려면 &quot;요청 시&quot;에 한 번 이상 실행해야 합니다.
1. 워크플로우를 테스트하고 작동하는지 확인합니다.
1. [!DNL Marketo Measure]에 사용자 지정 종료 날짜 API 이름을 제공할 고객.
1. [!DNL Marketo Measure] 대시보드의 [!DNL Marketo Measure] 사용자 지정 종료 날짜 필드를 가리키도록 [!DNL Marketo Measure] 앱 설정을 업데이트합니다.

   위의 단계를 완료하면 워크플로우를 실행하여 내역 기회에서 사용자 지정 [!DNL Marketo Measure] 운영 총액 필드와 [!DNL Marketo Measure] 사용자 지정 종료 날짜 필드를 모두 업데이트하여 올바른 데이터를 반영합니다. 이렇게 하면 수정된 일자/기준 필드가 변경될 수 있으므로 팀에 문제가 있는지 확인해야 합니다.

마감된 기회를 갱신하려면...

1. [!DNL Marketo Measure] 시작 날짜 이후 워크플로가 활성화될 때까지 종료된 영업 기회를 격리합니다. 워크플로우를 통해 업데이트해야 하는 과거 기회 그룹입니다.
1. 모든 레코드를 Excel로 내보냅니다.
1. Excel 파일을 열고 콘텐츠를 활성화합니다.
1. 실제 종료 날짜 데이터를 [!DNL Marketo Measure] 사용자 지정 종료 날짜에 복사합니다.
1. 실제 수익 데이터를 [!DNL Marketo Measure] 사용자 지정 영업 기회 금액 **및** [!DNL Marketo Measure] 영업 기회 금액에 복사합니다(두 개의 필드가 있음).
1. 파일을 저장합니다.
1. 파일을 가져옵니다. Dynamics에서는 이 파일을 업데이트할 기존 레코드가 있는 파일로 인식합니다.
1. 가져오기 파일에 오류가 있는지 확인합니다.

>[!NOTE]
>
>이 문서에 설명된 워크플로는 [!DNL Marketo Measure]이(가) 검색에 올바른 데이터를 표시할 수 있도록 필드를 업데이트하는 한 가지 방법입니다. 같은 일을 해낼 수 있는 다른 방법이 있다면, 도전해 볼 수 있다. 기본적으로 이러한 워크플로에서 필요한 사항은 다음과 같은 작업을 수행하는 것입니다.
>
> * Opp = Open인 경우, 사용자 정의 Opp 금액 필드, 사용자 정의 Opp 금액 필드 및 [!DNL Marketo Measure] Opp 금액 필드를 각각 예상 종료 일자 및 예상 매출과 동일하게 업데이트합니다.
> * Opp = 마감된 원화인 경우, 사용자 정의 마감 일자 필드, 사용자 정의 영업 기회 금액 필드 및 [!DNL Marketo Measure] 영업 기회 금액 필드를 각각 실제 마감 일자 및 실제 매출과 동일하게 업데이트합니다.
