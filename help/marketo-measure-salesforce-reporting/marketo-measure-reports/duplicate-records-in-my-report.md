---
unique-page-id: 18874634
description: 내 보고서의 중복 레코드 - [!DNL Marketo Measure] - 제품 설명서
title: 내 보고서의 레코드 복제
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# 내 보고서의 레코드 복제 {#duplicate-records-in-my-report}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;&quot;가 표시되지만, 여전히 &quot;[!DNL Bizible]CRM에 있는 &quot;입니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

As you dive다이빙 in the [!DNL Marketo Measure] 의 보고서 [!DNL Salesforce]보고서에서 &#39;중복&#39; 레코드를 찾을 수 있습니다. 당신은 리뷰를 할 때 이 느낌을 경험할 것 같습니다 [!DNL Marketo Measure] 기본 제공 보고서.

구매자 접점 오브젝트 또는 구매자 속성 접점 오브젝트로 보고할 때, 더 이상 리드, 연락처 또는 기회의 수를 보고하지 않고 해당 표준 오브젝트(리드, 연락처, 기회)와 연결된 구매자 접점 또는 구매자 속성 접점 수를 보고하는 것이 중요합니다.

다음 보고서를 예로 들어 보겠습니다.

(이)는 **구매자 접점 연락처** 보고서. 다시 말하지만, 이것은 우리가 개별 연락처와 연관된 터치포인트의 개수를 보고 있다는 것을 의미합니다.

![](assets/1.gif)

보시다시피, 보고서에 세 명의 James Williams 연락처가 있는 것 같습니다. 따라서 &quot;중복됩니다!&quot; 라고 생각할 수 있습니다.

그러나 이 보고서는 제임스와 관련된 터치포인트의 수를 보여주고 있습니다. 보고서에서 James에 개별 FT(첫 번째 터치), 개별 LC, 양식(리드 생성 터치) 및 PostLC 터치포인트(LC 터치포인트 후에 발생하는 양식 제출)가 있음을 확인할 수 있습니다.

&#39;연락처 수&#39;를 이해하려면 &#39;수 - 첫 번째 터치&#39;, &#39;수-리드 생성 터치&#39; 또는 &#39;수-U자형&#39; 필드를 사용하여 마케팅 상호 작용을 한 연락처 수를 파악할 수 있습니다.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학: Stock SFDC 보고서](https://universityonline.marketo.com/courses/bizible-fundamentals-bizible-102/#/page/5c5cb68dfb384d0c9fb96cc4)
