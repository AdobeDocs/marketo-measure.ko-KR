---
unique-page-id: 18874753
description: 추가 중 [!DNL Marketo Measure] 작업 - Forms - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] Forms 작업
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Forms 작업 {#adding-marketo-measure-to-act-on-forms}

## 방향 {#directions}

1. 편집할 양식에서 **[!UICONTROL Settings]** 오른쪽 모서리의 옵션.
1. 레이블이 지정된 영역을 찾습니다. [!UICONTROL "External Web Analytics."] 여기에서 [!DNL Marketo Measure] 추적 코드 조각.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>이 영역에는 이미 다음과 같은 다른 추적 코드 조각이 있을 수 있습니다. [!DNL Google Analytics] 코드가 있어야 합니다. 세미콜론을 사용하여 구분하십시오 `;` 그리고 다음과 같은 단일 공간:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
