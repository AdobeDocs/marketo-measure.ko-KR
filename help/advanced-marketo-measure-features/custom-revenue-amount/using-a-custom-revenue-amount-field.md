---
unique-page-id: 18874793
description: 사용자 정의 수익 금액 필드 사용 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 정의 수익 금액 필드 사용
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '356'
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
