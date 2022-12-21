---
unique-page-id: 18874730
description: 계정 기반 마케팅 개요 - [!DNL Marketo Measure] - 제품 설명서
title: 계정 기반 마케팅 개요
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# 계정 기반 마케팅 개요 {#account-based-marketing-overview}

다음은 ABM의 구성 요소인 [!DNL Marketo Measure] ABM 기능 및 기능을 [!DNL Salesforce] 페이지 레이아웃. ABM에 대해 자세히 알아보려면 다음을 확인하십시오 [이 페이지](https://www.marketo.com/account-based-marketing/){target=&quot;_blank&quot;}.

내에서 ABM 설정을 위한 지침으로 직접 이동하려면 [!DNL Salesforce] 예 [여기를 클릭하십시오.](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target=&quot;_blank&quot;}.

## ABM이란 무엇입니까? {#what-is-abm}

계정 기반 마케팅 ABM은 개인뿐만 아니라 회사 및 계정 전체에 대해 타깃팅하고 판매하는 마케팅 전략입니다. [!DNL Marketo Measure] 은 마케팅 및 영업 팀이 리드-투-계정 매핑 기능과 예측 참여 점수를 사용하여 성공적인 ABM 전략을 실행하는 데 도움이 됩니다.

계정 기반 마케팅 모델이 CRM에서 채워지려면, [!DNL Marketo Measure] 를 충족하려면 다음 기준이 필요합니다.

* CRM에는 최소 25개의 Closed Won Opportunity 가 있으며, 따라서 Adobe는 귀하의 비즈니스에 대한 &quot;성공적인&quot; Account/Opportunity 의 공통점을 더 잘 파악할 수 있습니다.
* 동전의 다른 측면에서는 CRM에 마감 원화 기회 없이 최소 25개의 계정이 필요합니다(모든 옵션은 &quot;개설&quot; 단계 카테고리 또는 &quot;미결 손실&quot; 카테고리에 있어야 함). 이렇게 하면 조직에서 등급 계정을 낮추는 것을 측정하는 데 도움이 됩니다.

>[!NOTE]
>
>10원대를 적립하지 않고 최소한 12개월 이상 계좌를 개설해야 한다. 해당 모델의 목적 때문에 Opp가 부실했는지 여부에 대한 기본 지침입니다.

## 리드-계정 매핑 {#lead-to-account-mapping}

리드-계정 매핑은 효과적인 ABM 접근 방식의 중요한 부분입니다. 리드-계정 매핑, 잠재 고객 또는 리드를 통해 브랜드와 거래할 때 동일한 회사 계정으로 그룹화됩니다. 이를 통해 동일한 회사의 개인에게 일관된 방식으로 타깃팅하고 판매할 수 있습니다. 추가 없음 [!DNL Salesforce] 이 기능에서 혜택을 얻기 위해 구성이 필요합니다. 다음 [!DNL Marketo Measure] Lead to Account Mapping 에는

* 웹 사이트를 계정 웹 사이트로 안내
* 계정 웹 사이트 도메인에 이메일 도메인 안내
* 잠재 고객명 계정 이름
* 회사 계정 웹 사이트 도메인 안내
* 연락처의 이메일 주소를 통해 잠재 고객의 이메일 주소의 도메인을 계정에 일치

## 예측 참여 점수 {#predictive-engagement-score}

다음 [!DNL Marketo Measure] 예측 참여 점수 또는 PES는 특정 계정이 마케팅 활동에 얼마나 참여하는지를 보여주는 동적 값입니다. 이 점수는 target에 계정을 세그먼트화하는 데 유용합니다. 이 툴은 보다 효과적이고 효율적으로 타겟팅할 계정을 식별하는 데 유용한 도구입니다.

PES를 계산하는 알고리즘에 들어가는 많은 구성 요소가 있습니다. 최근 및 나이는 마지막 터치 포인트 활동 또는 페이지 보기와 함께 점수 변경에 큰 영향을 줍니다. 계정에 새 연락처를 추가하면 PES에도 영향을 줍니다. 다음은 일부 PES 입력 목록입니다.

* 계정의 총 페이지 보기 수
* 평균 페이지 보기 수
* 계정의 평균 사용자 수
* 마지막 페이지 보기의 페이지
* 페이지 보기 평균 연령
* 계정에 있는 사람 수
* 특정 중요한 페이지와 지난 30/60/90일 동안 방문이 있었던 경우
* 계좌에 유실/원 거래가 종결된 경우
* 닫힐 가능성/원

>[!NOTE]
>
>일부 계정의 예측 참여 점수에 &quot;N/A&quot; 또는 &quot;-&quot;(대시 기호) 등급을 표시할 수 있습니다.

_&quot;N/A&quot; 등급은 모델이 실제 등급을 생성할 수 있도록 해당 계정에 아직 충분한 데이터가 없음을 의미합니다. 데이터가 더 많이 있으면 결국 등급이 지정됩니다._
_&quot;-&quot; 등급(대시 기호)은 시간 제한, 가끔 누락된 프로세스 등으로 인해 ABM 프로세스에서 이 계정을 아직 처리하지 않았음을 의미합니다. 계정에 다른 유사한 계정 또는 시간대에 따라 등급이 매겨져야 한다고 생각되는 경우 해당 계정에 연락하여 [!DNL Marketo Measure] 알아_

## ABM 페이지 레이아웃 설정 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

PES를 사용하려면 PES 필드 및 관련 목록을 의 해당 페이지 레이아웃에 추가하면 됩니다 [!DNL Salesforce].

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 그런 다음 편집할 페이지 레이아웃을 선택합니다.
1. 이동 [!UICONTROL Fields] 및 &quot;예측 참여 점수&quot; 필드를 계정 정보 섹션으로 이동합니다.

   ![](assets/1.png)

1. 마지막으로, [!UICONTROL Related Lists] 리드 관련 목록을 페이지 레이아웃으로 이동합니다.

   ![](assets/2.png)

1. 다음으로 이동합니다. **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 편집할 적절한 페이지 레이아웃을 선택합니다.
1. 클릭 **[!UICONTROL Fields]** 그리고 [!UICONTROL Account] 페이지에 맞는 필드입니다.

   ![](assets/3.png)

다 끝났어!

