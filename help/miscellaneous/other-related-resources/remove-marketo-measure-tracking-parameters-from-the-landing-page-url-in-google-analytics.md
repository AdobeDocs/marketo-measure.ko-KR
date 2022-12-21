---
unique-page-id: 18874736
description: 제거 [!DNL Marketo Measure] 랜딩 페이지 URL에서 Google Analytics 매개 변수 추적 - [!DNL Marketo Measure] - 제품 설명서
title: 제거 [!DNL Marketo Measure] Google Analytics의 랜딩 페이지 URL에서 매개 변수 추적
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# 제거 [!DNL Marketo Measure] Google Analytics의 랜딩 페이지 URL에서 매개 변수 추적 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

경우에 따라 에서 랜딩 페이지를 볼 때 [!DNL Google Analytics]를 URL에서 추적 매개 변수를 제거할 수 있습니다. 그렇지 않으면 개별 행으로 분할됩니다.

다행히도, 이것은 쉬운 수정이다.

1. in [!DNL Google Analytics], 이동 [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. 상자에 &quot;_bt,_bk,_bm,_bn,_bg&quot;를 입력합니다(따옴표 제외).
1. 아래로 스크롤하여 클릭 **[!UICONTROL Save]**.

   주의 사항 [!DNL Google Analytics] 는 데이터를 재처리하지 않습니다. 따라서 이 변경 사항은 앞으로 진행되는 경우에만 반영되며, 이전 데이터는 여전히 bt, bk 및 bm 매개 변수와 함께 표시됩니다.
