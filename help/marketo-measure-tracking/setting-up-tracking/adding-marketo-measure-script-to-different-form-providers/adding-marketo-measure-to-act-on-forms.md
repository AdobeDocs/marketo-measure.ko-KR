---
unique-page-id: 18874753
description: Act-On Forms에  [!DNL Marketo Measure] 추가 - [!DNL Marketo Measure]
title: Act-On Forms에  [!DNL Marketo Measure] 을(를) 추가하는 중
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 0%

---

# Act-On Forms에 [!DNL Marketo Measure] 추가 중 {#adding-marketo-measure-to-act-on-forms}

## 방향 {#directions}

1. 편집 중인 양식에서 오른쪽 모서리에 있는 **[!UICONTROL Settings]** 옵션을 선택합니다.
1. 레이블이 [!UICONTROL "External Web Analytics."]인 영역을 찾으십시오. 이 영역은 [!DNL Marketo Measure] 추적 코드 조각을 놓는 위치입니다.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>이 영역에 [!DNL Google Analytics] 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 세미콜론 `;`과 같은 단일 공백을 사용하여 구분하십시오.
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
