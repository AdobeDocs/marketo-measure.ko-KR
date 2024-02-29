---
unique-page-id: 18874743
description: 연결 중 [!DNL Marketo Measure] 스크립트 관리자 바운스를 해제하려면 - [!DNL Marketo Measure]
title: 연결 중 [!DNL Marketo Measure] 스크립트 관리자의 바운스를 해제하려면
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# 연결 중 [!DNL Marketo Measure] 스크립트 관리자의 바운스를 해제하려면 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 는 언바운스와 직접 통합되므로 에서 랜딩 페이지 전환의 디지털 마케팅 소스를 직접 추적할 수 있습니다. [!DNL Salesforce]. 연결하려면 을(를) [!DNL Marketo Measure] 언바운스 스크립트 관리자로 스크립팅합니다. 방법은 다음과 같습니다.

1. 에 로그인 [!DNL Unbounce] 계정입니다.
1. 클릭 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 팝업에서 을 선택합니다. [!UICONTROL Custom Script] 이름을 &quot;[!DNL Marketo Measure Marketing Analytics].&quot; 클릭 **[!UICONTROL Add Script Details]**.
1. 헤드(Head)에서 배치(placement)를 선택합니다. 기본 랜딩 페이지 및 양식 확인 대화 상자에 스크립트를 포함합니다. 붙여넣기 [!DNL Marketo Measure] 아래에 있는 를 상자에 스크립팅합니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 클릭 **[!UICONTROL Save]**.

다음 [!DNL Marketo Measure] 통합은 unbounce.com 도메인을 사용하는 랜딩 페이지가 아닌 도메인(예: landing.mysite.com)에서 호스팅되는 한 언바운스 랜딩 페이지에서 작동합니다.
