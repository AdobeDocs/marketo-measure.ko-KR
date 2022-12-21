---
unique-page-id: 18874614
description: 구매자 터치포인트를 사용한 리드 보고서 - [!DNL Marketo Measure] - 제품 설명서
title: 구매자 터치포인트를 사용한 리드 보고서
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# 구매자 터치포인트를 사용한 리드 보고서 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;&quot;은(는) 설명서에 있지만 여전히 &quot;&quot;가 표시됩니다.[!DNL Bizible]&quot;&quot;을 클릭합니다. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

즉시 사용 가능한 경우 다양한 보고 기능을 편리하게 이용할 수 있습니다 [!DNL Marketo Measure]하지만 빌드하는 것이 권장되는 몇 가지 추가 보고서 유형이 있습니다. 아래 구매자 터치포인트 보고서 유형을 사용하여 포괄적인 리드를 생성하는 방법에 대해 알아봅니다.

1. 내에서 설정 옵션으로 이동합니다 [!DNL Salesforce]. 여기에서 &quot;생성&quot; 그룹을 확장하고 을 선택합니다 **[!UICONTROL Report Types]**.

   ![](assets/1.jpg)

1. 선택 **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. 기본 객체를 &quot;리드&quot;로 설정하고 &quot;보고서 유형 레이블&quot; 입력 &quot;구매자 터치포인트를 포함하는 리드 - 포함&quot; 내에서 설정합니다. 보고서를 &quot;리드&quot; 범주 내에 저장하고 배포 상태를 로 변경합니다. **[!UICONTROL Deployed]**. 그런 다음 을(를) 선택합니다 **[!UICONTROL Next]**.

   ![](assets/3.jpg)

1. 객체 관계에 대해 **[!DNL Marketo Measure]사람** 개체를 보조 개체로 사용합니다. A-B 관계를 선택합니다. &quot;각 &#39;A&#39; 레코드에는 하나 이상의 관련 &#39;B&#39; 레코드가 있어야 합니다.&quot; 여기에서 &quot;구매자 터치포인트&quot; 객체를 연관시키고 B와 C 객체 간에 동일한 관계를 선택합니다.

   ![](assets/4.jpg)

1. 일부 보고서를 저장하고 작성을 시작합니다.
