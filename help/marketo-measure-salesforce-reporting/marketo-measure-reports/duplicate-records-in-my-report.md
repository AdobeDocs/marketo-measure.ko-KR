---
unique-page-id: 18874634
description: 내 보고서의 중복 레코드 - [!DNL Marketo Measure] - 제품 설명서
title: 내 보고서에 중복 레코드
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# 내 보고서에 중복 레코드 {#duplicate-records-in-my-report}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;&quot;은(는) 설명서에 있지만 여전히 &quot;&quot;가 표시됩니다.[!DNL Bizible]&quot;&quot;을 클릭합니다. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

당신이 이 [!DNL Marketo Measure] 의 보고서 [!DNL Salesforce]를 입력하면 보고서에서 &#39;중복&#39; 레코드를 찾을 수 있습니다. 당신은 당신이 검토할 때 이런 느낌을 경험할 것이다 [!DNL Marketo Measure] 기본 제공 보고서.

구매자 터치포인트 객체 또는 구매자 기여도 분석 터치포인트 객체를 사용하여 보고할 때 더 이상 리드, 연락처 또는 기회 수에 대해 보고하지 않지만, 해당 표준 객체(리드, 연락처, 기회)와 연관된 구매자 터치포인트 또는 구매자 기여도 분석 터치포인트 수에 대해 보고하는 것이 중요합니다.

다음 보고서를 예로 들어 보겠습니다.

이것은 **구매자 터치포인트를 사용하는 연락처** 보고서 세트에 대해 설명합니다. 다시, 이것은 우리가 개별 연락처와 연관된 터치포인트 수를 보고 있다는 것을 의미합니다.

![](assets/1.gif)

보시다시피, 보고서에 제임스 윌리암스가 3명의 연락처가 있는 것 같습니다. 따라서 당신은 &quot;중복!&quot; 이라고 생각할지도 모릅니다.

하지만, 이 보고서는 James와 관련된 터치포인트 수를 보여줍니다. 보고서 내에서 James에 개별 FT(첫 번째 터치), 개별 LC, 양식(리드 생성 터치) 및 PostLC 터치포인트(LC 터치포인트 후 발생하는 양식 제출)가 있음을 알 수 있습니다.

&#39;연락처 수&#39;를 이해하려면 &#39;카운트 - 첫 번째 터치&#39;, &#39;카운트 리드 만들기 터치&#39; 또는 &#39;Count-U자형&#39; 필드를 사용하여 마케팅 상호 작용이 있는 연락처의 수를 이해할 수 있습니다.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학: 스톡 SFDC 보고서](https://universityonline.marketo.com/courses/bizible-fundamentals-bizible-102/#/page/5c5cb68dfb384d0c9fb96cc4)
