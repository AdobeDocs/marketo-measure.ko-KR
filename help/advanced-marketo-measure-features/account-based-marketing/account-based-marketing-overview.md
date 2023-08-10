---
unique-page-id: 18874730
description: 계정 기반 마케팅 개요 - [!DNL Marketo Measure] - 제품 설명서
title: 계정 기반 마케팅 개요
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 계정 기반 마케팅 개요 {#account-based-marketing-overview}

다음은 의 구성 요소인 ABM에 대한 간략한 개요입니다. [!DNL Marketo Measure] ABM 기능 및 추가 방법 [!DNL Salesforce] 페이지 레이아웃입니다. ABM에 대해 자세히 알아보려면 [이 페이지](https://www.marketo.com/account-based-marketing/){target="_blank"}.

내에서 ABM 설정에 대한 지침으로 직접 이동하려면 [!DNL Salesforce] 인스턴스: [여기를 클릭하십시오](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## ABM이란 {#what-is-abm}

계정 기반 마케팅, ABM은 개인뿐만 아니라 기업 및 계정 전체를 대상으로 하여 판매하는 마케팅 전략입니다. [!DNL Marketo Measure] 은 마케팅 및 영업 팀이 리드-계정 매핑 기능과 예측 참여 점수를 통해 성공적인 ABM 전략을 실행하는 데 도움이 됩니다.

계정 기반 마케팅 모델이 CRM에 채워지도록 하려면 [!DNL Marketo Measure] 은(는) 다음 기준을 충족해야 합니다.

* CRM에는 최소 25개의 계정에 최소 하나의 확정된 영업 기회가 있어야 하므로, &quot;성공한&quot; 계정/영업 기회의 공통점을 비즈니스에 더 잘 측정할 수 있습니다.
* 동전의 반대편인 CRM에는 종결된 성공 기회 없이 최소 25개의 계정이 필요합니다(모든 옵션은 &quot;공개&quot; 단계 범주 또는 &quot;종결된 손실&quot; 범주에 있어야 함). 이를 통해 조직에서 등급이 낮은 계정을 만드는 이유를 측정할 수 있습니다.

>[!NOTE]
>
>위의 &quot;불량&quot; 계정은 폐쇄 원화 OPP를 누적하지 않고 최소 12개월 동안 열어야 합니다. 이는 Opp가 모델의 목적에 따라 부실화되었는지 여부에 대한 기본 지침입니다.

## 리드-계정 매핑 {#lead-to-account-mapping}

리드-계정 매핑은 효과적인 ABM 접근법의 중요한 부분입니다. 리드-계정 매핑, 잠재 고객 또는 리드를 사용하면 브랜드와 관계를 맺을 때 동일한 회사 계정으로 그룹화됩니다. 이를 통해 일관된 방식으로 동일한 회사의 개인에 대해 타겟팅 및 판매를 수행할 수 있습니다. 추가 항목이 없습니다. [!DNL Salesforce] 이 기능을 사용하려면 구성이 필요합니다. 다음 [!DNL Marketo Measure] 리드-계정 매핑 5가지 일치 방법:

* 잠재 고객 웹 사이트 - 계정 웹 사이트
* 이메일 도메인을 계정 웹 사이트 도메인으로 리드
* 리드 회사 이름을 계정 이름으로
* 회사를 계정 웹 사이트 도메인으로 안내합니다.
* 잠재 고객 이메일 주소의 도메인을 연락처 이메일 주소를 통해 계정과 일치

>[!NOTE]
>
>각 Lead 는 위의 방법 순서에 따라 Account에 대응됩니다. 일치하는 항목이 있으면 AccountId가 즉시 리드에 설정되고 다른 방법을 사용하여 일치하지 않습니다. 잠재 고객에 이미 유효한 AccountId가 있는 경우 잠재 고객을 건너뜁니다.

## 예측 참여 점수 {#predictive-engagement-score}

다음 [!DNL Marketo Measure] 예측 참여 점수(PES)는 특정 계정이 마케팅 활동에 얼마나 참여했는지 보여 주는 동적 값입니다. 이 점수는 계정을 대상으로 세그먼트화하는 데 유용합니다. 보다 효과적이고 효율적으로 타깃팅할 계정을 식별하는 데 귀중한 툴입니다.

PES를 계산하는 알고리즘에는 많은 구성 요소가 들어갑니다. 최신성 및 연령은 마지막 터치포인트 활동 또는 페이지 조회수와 함께 점수 변화에 큰 영향을 미칩니다. 계정에 새 연락처를 추가하면 PES에도 영향을 줍니다. 다음은 일부 PES 입력 목록입니다.

* 계정의 총 페이지 보기 수
* 평균 페이지 보기 수
* 계정의 평균 사람 수
* 마지막 페이지 보기 나이
* 페이지 조회수의 평균 연령
* 계정의 사용자 수
* 특정 중요 페이지 및 지난 30/60/90일 동안 방문이 있었던 경우
* 계정에 종료된 손실/원 거래
* 손실/원화로 마감될 가능성

>[!NOTE]
>
>일부 계정에 대한 예측 참여 점수에서 &quot;N/A&quot; 또는 &quot;-&quot;(대시 기호)의 등급을 볼 수 있습니다.

_&quot;N/A&quot;의 등급은 실제 등급을 생성하기 위해 모델에 대한 해당 계정에 대한 데이터가 아직 충분하지 않다는 것을 의미합니다. 데이터가 많을수록 등급이 부여됩니다._
_&quot;-&quot; 등급(대시 기호)은 시간 제한, 때때로 프로세스 누락 등으로 인해 이 계정이 ABM 프로세스에서 아직 처리되지 않았음을 의미합니다. 유사한 다른 계정 또는 일정에 따라 등급이 부여되어야 한다고 생각되는 경우, 연락하여 허용하십시오. [!DNL Marketo Measure] 알아._

## 에서 ABM 페이지 레이아웃 설정 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

PES를 사용하기 시작하려면 PES 필드 및 관련 목록 을 의 해당 페이지 레이아웃에 추가하면 됩니다 [!DNL Salesforce].

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 그런 다음 편집할 페이지 레이아웃을 선택합니다.
1. 다음으로 이동 [!UICONTROL Fields] 및 필드 &quot;예측 참여 점수&quot;를 계정 정보 섹션으로 이동합니다.

   ![](assets/1.png)

1. 마지막으로 다음으로 이동 [!UICONTROL Related Lists] &quot;잠재 고객&quot; 관련 목록을 페이지 레이아웃으로 이동합니다.

   ![](assets/2.png)

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 편집할 페이지 레이아웃을 선택합니다.
1. 클릭 **[!UICONTROL Fields]** 및 추가 [!UICONTROL Account] 페이지에 맞는 필드가 표시됩니다.

   ![](assets/3.png)

준비가 완료되었습니다!

