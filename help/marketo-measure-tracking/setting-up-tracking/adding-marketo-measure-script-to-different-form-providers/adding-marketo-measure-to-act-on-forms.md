---
unique-page-id: 18874753
description: 추가 중 [!DNL Marketo Measure] Forms에 실제 적용 - [!DNL Marketo Measure]
title: 추가 중 [!DNL Marketo Measure] Forms에 실제 적용
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Forms에 실제 적용 {#adding-marketo-measure-to-act-on-forms}

## 방향 {#directions}

1. 편집 중인 양식에서 **[!UICONTROL Settings]** 오른쪽 모서리에 있는 옵션입니다.
1. 레이블이 지정된 영역을 찾습니다. [!UICONTROL "External Web Analytics."] 여기서 를 삭제합니다. [!DNL Marketo Measure] 추적 코드 조각.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>이 영역에는 다음과 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. [!DNL Google Analytics] 코드. 세미콜론으로 구분해야 합니다 `;` 그리고 다음과 같은 단일 공간:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
