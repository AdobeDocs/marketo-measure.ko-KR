---
description: 사용자 정의 수익 금액 필드 사용 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 정의 수익 금액 필드 사용
hide: true
hidefromtoc: true
feature: Custom Revenue Amount
source-git-commit: 2d2fe74998abd853f6592c5e65edfe2ce39d7ce6
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# 사용자 정의 수익 금액 필드 사용 {#using-a-custom-revenue-amount-field}

기본적으로 구매자 속성 터치포인트는 다음 두 필드 중 하나에서 기회 금액을 가져옵니다.

* 금액(SFDC 기본값)
* [!DNL Marketo Measure] 영업 기회 금액(사용자 정의)

기회에서 사용자 정의 금액 필드를 사용하는 경우 구매자 접점 매출을 계산하기 위해 워크플로우를 구성해야 합니다. 이에 대한 보다 고급 지식이 필요합니다. [!DNL Salesforce]SFDC 관리자의 도움이 필요할 수 있습니다.

시작하려면 다음 정보가 필요합니다.

* 금액 필드의 API 이름

여기부터 워크플로우 만들기를 시작합니다.

## Salesforce Lightning에서 워크플로우 만들기 {#create-the-workflow-in-salesforce-lightning}

다음 단계는 Salesforce Lightning 사용자를 위한 것입니다. 여전히 Salesforce Classic을 사용하는 경우 다음 단계를 수행합니다 [아래에 나열되어 있습니다.](#create-the-workflow-in-salesforce-classic).

1. 설정에서 빠른 찾기 상자에 &quot;흐름&quot;을 입력하고 다음을 선택합니다. **플로우** Flow Builder를 시작합니다. 오른쪽 패널에서 **새 흐름** 단추를 클릭합니다.

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. 선택 **레코드 트리거된 흐름** 을(를) 클릭하고 **만들기** 오른쪽 하단의 버튼입니다.

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. Configure Start 창에서 Opportunity 객체를 선택합니다. 트리거 구성 섹션에서 을(를) 선택합니다. **레코드가 생성되거나 업데이트됩니다.**.

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. 시작 조건 설정 섹션의 조건 요구 사항 아래에서 **사용자 지정 조건 논리가 충족됨**.
   * 검색 필드에서 사용자 정의 금액 필드를 선택합니다.
   * 연산자를 다음으로 설정 **Null임**, 및 값 **False**.
   * 평가 기준을 다음으로 설정 **레코드가 업데이트되고 조건 요구 사항을 충족할 때마다**.

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. &quot;다음에 대한 흐름 최적화&quot; 섹션에서 을(를) 선택합니다. **빠른 필드 업데이트**. 클릭 **완료**.

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. 요소를 추가하려면 더하기(+) 아이콘을 클릭하고 를 선택합니다 **트리거 기록 업데이트**.

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. 신규 레코드 갱신 창에서 다음을 입력합니다.

   * 레이블 입력 - API 이름이 자동으로 생성됩니다.
   * &quot;업데이트할 레코드를 찾고 값을 설정하는 방법&quot;에서 **플로우를 트리거한 영업 기회 레코드 사용**.
   * &quot;필터 조건 설정&quot; 섹션에서 다음을 선택합니다 **항상 레코드 업데이트** 레코드를 업데이트하는 조건 요구 사항입니다.
   * &quot;캠페인 레코드에 대한 필드 값 설정&quot;에서 필드에서 Marketo Measure 기회 금액을 선택하고 사용자 정의 금액 필드를 평가합니다.
   * 클릭 **완료**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. **저장**&#x200B;을 클릭합니다. 팝업이 나타납니다. 흐름 저장 창에 &quot;흐름 레이블&quot;을 입력합니다(흐름 API 이름이 자동으로 생성됨). 클릭 **저장** 다시.

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. 다음을 클릭합니다. **활성화** 단추를 클릭하여 흐름을 활성화합니다.

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## Salesforce Classic에서 워크플로우 만들기 {#create-the-workflow-in-salesforce-classic}

다음 단계는 Salesforce Classic 사용자를 위한 것입니다. Salesforce Lightning으로 전환한 경우 해당 단계 [위에서 찾을 수 있음](#create-the-workflow-in-salesforce-lightning).

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. 선택 **[!UICONTROL New Rule]**&#x200B;개체를 &quot;Opportunity&quot;로 설정하고 **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. 워크플로우를 구성합니다. 규칙 이름을 &quot;Update&quot;로 설정 [!DNL Marketo Measure] Opportunity Amount.&quot; 평가 기준을 &quot;만들어짐, 편집할 때마다&quot;로 설정합니다. 규칙 기준에 대해 사용자 정의 금액 필드를 선택하고 연산자를 선택합니다 [!UICONTROL as "Not Equal To"] 그리고 &quot;값&quot; 필드를 비워 둡니다.

   ![](assets/4.jpg)

1. 워크플로우 작업을 추가합니다. 이 선택 목록을 &quot;(으)로 설정[!UICONTROL New Field Update].&quot;
   ![](assets/5.jpg)

1. 여기에서 필드 정보를 작성할 수 있습니다. &quot;이름&quot; 필드에서는 다음 이름을 사용하는 것이 좋습니다. &quot;[!DNL Marketo Measure] Opp 금액.&quot; &quot;고유 이름&quot;은 &quot;이름&quot; 필드를 기반으로 자동으로 채워집니다. &quot;업데이트할 필드&quot; 선택 목록에서 &quot;[!DNL Marketo Measure] Opportunity Amount.&quot; 필드를 선택한 후 &quot;필드 변경 후 워크플로우 규칙 재평가&quot; 상자를 선택합니다. &quot;새 필드 값 지정&quot;에서 &quot;새 값을 설정하려면 수식 사용&quot;을 선택합니다. 빈 상자에 사용자 정의 금액 필드의 API 이름을 놓습니다. 클릭 **[!UICONTROL Save]**.

   ![](assets/6.png)

1. 워크플로우의 롤업 페이지로 돌아가서, &quot;활성화&quot;해야 합니다. 계속하셔도 좋습니다. 활성화하려면 **편집** 새 워크플로우 옆에 있는 을(를) 클릭하고 **활성화**.

   이 단계를 완료하고 나면 워크플로우를 트리거하여 의 새 값을 갖도록 기회를 업데이트해야 합니다. [!UICONTROL custom opportunity] 필드.

   SFDC 내의 Data Loader를 통해 기회를 실행하여 이를 수행할 수 있습니다. 에서 데이터 로더 사용에 대한 세부 사항을 확인하십시오. [이 문서](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

질문이 있는 경우 주저하지 말고 Adobe 계정 팀(계정 관리자)이나 [[!DNL Marketo] 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
