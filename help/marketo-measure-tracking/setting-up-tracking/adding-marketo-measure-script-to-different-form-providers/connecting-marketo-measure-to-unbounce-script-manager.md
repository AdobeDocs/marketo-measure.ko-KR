---
unique-page-id: 18874743
description: 연결 중 [!DNL Marketo Measure] Unbound Script Manager - [!DNL Marketo Measure] - 제품 설명서
title: 연결 중 [!DNL Marketo Measure] Unbound Script Manager
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# 연결 중 [!DNL Marketo Measure] Unbound Script Manager {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 에서 바로 Unbounce와 통합되므로 랜딩 페이지 전환의 디지털 마케팅 소스를 추적할 수 있습니다. [!DNL Salesforce]. 연결을 만들려면 [!DNL Marketo Measure] 스크립트를 바운스 해제 스크립트 관리자에 추가합니다. 방법은 다음과 같습니다.

1. 에 로그인합니다. [!DNL Unbounce] 계정이 필요합니다.
1. 클릭 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 팝업에서 [!UICONTROL Custom Script] 이름을 &quot;[!DNL Marketo Measure Marketing Analytics].&quot; 클릭 **[!UICONTROL Add Script Details]**.
1. 헤드에서 배치를 선택합니다. 기본 랜딩 페이지 및 양식 확인 대화 상자에 스크립트를 포함합니다. 붙여넣기 [!DNL Marketo Measure] 아래의 스크립트를 상자에 넣습니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 클릭 **[!UICONTROL Save]**.

다음 [!DNL Marketo Measure] 통합은 unbounce.com 도메인을 사용하는 항목이 아닌 도메인(예: landing.mysite.com)에서 호스팅되는 한 Unbound 랜딩 페이지에서 작동합니다.
