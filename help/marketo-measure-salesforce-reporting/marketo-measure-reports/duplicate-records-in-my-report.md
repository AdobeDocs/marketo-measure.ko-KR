---
unique-page-id: 18874634
description: 내 보고서의 중복 레코드 - [!DNL Marketo Measure]
title: 내 보고서의 레코드 복제
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# 내 보고서의 레코드 복제 {#duplicate-records-in-my-report}

>[!NOTE]
>
>설명서에는 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시되지만 CRM에는 여전히 &quot;[!DNL Bizible]&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Salesforce]의 [!DNL Marketo Measure] 보고서를 자세히 살펴보면 보고서에서 &#39;중복&#39; 레코드를 찾을 수 있습니다. [!DNL Marketo Measure]개의 기본 보고서를 검토할 때 이러한 느낌이 들 수 있습니다.

구매자 접점 오브젝트 또는 Buyer Attribution Touchpoint 오브젝트로 보고할 때 더 이상 리드, 연락처 또는 기회의 수를 보고하지 않고 해당 표준 오브젝트(리드, 연락처, 기회)에 연결된 구매자 접점 또는 구매자 속성 접점 수를 보고하는 것이 중요합니다.

다음 보고서를 예로 들어 보겠습니다.

**구매자 접점 연락처** 보고서입니다. 다시 말하지만, 이것은 우리가 개별 연락처와 연관된 터치포인트의 개수를 보고 있다는 것을 의미합니다.

![](assets/1.gif)

보시다시피, 보고서에 세 명의 James Williams 연락처가 있는 것 같습니다. 따라서 &quot;중복됩니다!&quot; 라고 생각할 수 있습니다.

그러나 이 보고서는 제임스와 관련된 터치포인트의 수를 보여주고 있습니다. 보고서에서 James에 개별 FT(첫 번째 터치), 개별 LC, 양식(리드 생성 터치) 및 PostLC 터치포인트(LC 터치포인트 후에 발생하는 양식 제출)가 있음을 확인할 수 있습니다.

&#39;연락처 수&#39;를 이해하려면 &#39;수 - 첫 번째 터치&#39;, &#39;수-리드 생성 터치&#39; 또는 &#39;수-U자형&#39; 필드를 사용하여 마케팅 상호 작용을 한 연락처 수를 파악할 수 있습니다.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: 재고 SFDC 보고서](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
