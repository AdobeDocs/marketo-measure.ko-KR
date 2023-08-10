---
unique-page-id: 18874757
description: 추가 중 [!DNL Marketo Measure] JavaScript 대상 [!DNL Pardot] - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] JavaScript 대상 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] JavaScript 대상 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 양식을 사용하려면 사이트에 스크립트를 지정하는 것 이상의 양식 템플릿 내에서 추가 처리가 필요합니다. [!DNL Marketo Measure] 양식 제출을 인식하기 위해 프로세스는 간단합니다. [!DNL Marketo Measure] 스크립트를에 추적 [!DNL Pardot] 양식 서식 파일입니다.

## 단계별 지침 {#step-by-step-instructions}

에 로그인한 후 [!DNL Pardot] 계정, 아래 단계를 따르십시오.

1. 다음으로 이동 **[!UICONTROL Marketing]**.

1. 클릭 **[!UICONTROL Landing Pages]**.

1. 선택 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 적절한 레이아웃 템플릿을 결정하고 **[!UICONTROL Edit]** 오른쪽이요

   ![](assets/2-1.png)

1. 복사 및 붙여넣기 [!DNL Marketo Measure] HTML 페이지에서 닫기 헤더 태그 바로 앞에 JavaScript 코드가 있습니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 해당하는 모든 랜딩 페이지 레이아웃 템플릿에 대해 다음 단계를 수행합니다.

1. 다음을 확인합니다. [!DNL Marketo Measure] JavaScript는 일반 사이트 페이지에도 있습니다.

   다음 범위 내 [!DNL Pardot] 레이아웃 템플릿에서 코드는 다음과 같이 표시됩니다.

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 추가 참고 사항 {#additional-notes}

다음과 같은 경우 [!DNL Pardot] IFrame에는 다음 HTML 태그가 있습니다.

`<base href="http://go.pardot.com">`

_및_ 에서 스크립트를 로드하려고 할 때 IFrame 자체는 실제로 비보안 페이지(HTTP) 대신 보안 페이지(HTTPS)에 있습니다. [!DNL Pardot] IFrame을 사용하면 브라우저가 HTTPS 페이지에 스크립트의 HTTP 버전을 로드하려고 시도하여 실패하고 추적을 방지합니다. 해결 방법은 의 스크립트를 [!DNL Pardot] 스크립트의 보안 버전을 로드하려면 IFrame:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

또한 이 영역에는 다음과 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. [!DNL Google Analytics] 코드. 그것들을 세미콜론으로 구분해야 한다 `;` 다음 예제와 같은 단일 스페이스:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
