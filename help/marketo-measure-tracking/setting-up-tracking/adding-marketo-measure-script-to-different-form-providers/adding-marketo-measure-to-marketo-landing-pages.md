---
unique-page-id: 18874755
description: 추가 중 [!DNL Marketo Measure] 끝 [!DNL Marketo] 랜딩 페이지 - [!DNL Marketo Measure]
title: 추가 중 [!DNL Marketo Measure] Marketo 랜딩 페이지로
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Marketo 랜딩 페이지로 {#adding-marketo-measure-to-marketo-landing-pages}

에 추적을 추가하는 방법 알아보기 [!DNL Marketo Engage] 추가 처리가 필요한 랜딩 페이지. [!DNL Marketo Measure] JavaScript는 랜딩 페이지와 [!DNL Marketo Engage] 양식 자체. 이 작업을 수행하려면 을 로드해야 합니다. [!DNL Marketo Measure] 에 JavaScript [!DNL Marketo Engage] 다음 지침에 설명되어 있습니다.

>[!NOTE]
>
>와 같은 태그 관리 공급자를 통해 JavaScript를 배포하는 경우 [!DNL Google Tag Manager]를 수동으로 추가할 필요는 없습니다 [!DNL Marketo Measure] JS에서 로 [!DNL Marketo Engage].

## 추가 방법 [!DNL Marketo Measure] 스크립팅 대상 [!DNL Marketo Engage] 랜딩 페이지 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 에 로그인 [!DNL Marketo Engage] 계정입니다.
1. 랜딩 페이지를 선택하고 **[!UICONTROL Edit Draft]**.
1. HTML 요소를 드래그합니다.
1. 다음을 입력합니다. [!DNL Marketo Measure] JavaScript를 [!UICONTROL head] 섹션:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

아래 스크린샷의 예

1. 클릭 **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 추가 참고 사항 {#additional-notes}

* 다음과 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. [!DNL Google Analytics] 코드. 이 부분은 문제없고 세미콜론으로 구분해서 사용하시면 됩니다 `;` 단일 공간도 있습니다. 이 예제는 다음과 같습니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 여러 랜딩 페이지 템플릿이 사용 중일 수 있습니다. 양식이 있는 모든 템플릿에 코드를 추가해야 합니다.

* 랜딩 페이지의 템플릿을 편집할 때 랜딩 페이지가 사용되는 페이지를 다시 승인해야 하는 경우가 있습니다. 이 문서에서는 [일괄 승인 방법](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
