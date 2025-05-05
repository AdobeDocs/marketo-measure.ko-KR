---
unique-page-id: 18874755
description: ' [!DNL Marketo Measure] to [!DNL Marketo] 랜딩 페이지 추가 - [!DNL Marketo Measure]'
title: Marketo 랜딩 페이지에  [!DNL Marketo Measure] 을(를) 추가하는 중
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Marketo 랜딩 페이지에 [!DNL Marketo Measure]을(를) 추가하는 중 {#adding-marketo-measure-to-marketo-landing-pages}

추가 처리가 필요하므로 [!DNL Marketo Engage] 랜딩 페이지에 추적을 추가하는 방법을 알아봅니다. [!DNL Marketo Measure] JavaScript은 랜딩 페이지와 [!DNL Marketo Engage] 양식 자체에 모두 있어야 합니다. 이렇게 하려면 다음 지침에 설명된 대로 [!DNL Marketo Measure] JavaScript을 [!DNL Marketo Engage]에 로드해야 합니다.

>[!NOTE]
>
>[!DNL Google Tag Manager]과(와) 같은 태그 관리 공급자를 통해 JavaScript을 배포하는 경우 [!DNL Marketo Measure] JS를 [!DNL Marketo Engage]에 수동으로 추가할 필요가 없습니다.

## [!DNL Marketo Engage] 랜딩 페이지에 [!DNL Marketo Measure] 스크립트를 추가하는 방법 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. [!DNL Marketo Engage] 계정에 로그인합니다.
1. 랜딩 페이지를 선택하고 **[!UICONTROL Edit Draft]**&#x200B;을(를) 클릭합니다.
1. HTML 요소를 드래그합니다.
1. [!UICONTROL head] 섹션에 [!DNL Marketo Measure] JavaScript 입력:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

아래 스크린샷의 예

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 추가 참고 사항 {#additional-notes}

* [!DNL Google Analytics] 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 이 작업에는 문제가 없습니다. 세미콜론 `;`과 단일 공백으로 구분하십시오. 이 예제는 다음과 같습니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 여러 랜딩 페이지 템플릿이 사용 중일 수 있습니다. 양식이 있는 모든 템플릿에 코드를 추가해야 합니다.

* 랜딩 페이지의 템플릿을 편집할 때 랜딩 페이지를 사용하는 페이지를 다시 승인해야 하는 경우가 있습니다. 이 문서에서는 [일괄 승인 방법](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html?lang=ko){target="_blank"}에 대해 설명합니다.
