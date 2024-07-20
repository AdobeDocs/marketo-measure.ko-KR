---
unique-page-id: 18874614
description: 구매자 터치포인트 보고서가 있는 리드 - [!DNL Marketo Measure]
title: 구매자 접점 관련 리드 보고서
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# 구매자 접점 관련 리드 보고서 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>설명서에는 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시되지만 CRM에는 여전히 &quot;[!DNL Bizible]&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure]을(를) 사용하면 즉시 여러 보고 기능을 사용할 수 있지만, 몇 가지 추가 보고서 유형을 만드는 것이 좋습니다. 아래 구매자 접점 보고서 유형을 사용하여 포함 리드를 생성하는 방법에 대해 알아보십시오.

1. [!DNL Salesforce] 내에서 설정 옵션으로 이동합니다. 여기에서 &quot;만들기&quot; 그룹화를 확장하고 **[!UICONTROL Report Types]**&#x200B;을(를) 선택합니다.

   ![](assets/1.jpg)

1. **[!UICONTROL New Custom Report Type]**&#x200B;을(를) 선택합니다.

   ![](assets/2.jpg)

1. 기본 객체를 &quot;가망 고객&quot;으로 설정하고 &quot;보고서 유형 레이블&quot; 입력 &quot;구매자 접점 포함 가망 고객 - 포함&quot;에 &quot;가망 고객&quot;을 설정합니다. 보고서를 &quot;잠재 고객&quot; 범주 내에 저장하고 배포 상태를 **[!UICONTROL Deployed]**(으)로 변경합니다. **[!UICONTROL Next]**&#x200B;을(를) 선택합니다.

   ![](assets/3.jpg)

1. 개체 관계의 경우 **[!DNL Marketo Measure]명의 사용자** 개체를 보조 개체로 선택하십시오. A-B 관계를 &quot;각 &#39;A&#39; 레코드에는 관련 &#39;B&#39; 레코드가 하나 이상 있어야 합니다.&quot;로 선택합니다. 여기에서 &quot;Buyer Touchpoint&quot; 개체와 관계를 설정하고 B 개체와 C 개체 간에 동일한 관계를 선택합니다.

   ![](assets/4.jpg)

1. 저장하고 일부 보고서 작성을 시작하십시오!
