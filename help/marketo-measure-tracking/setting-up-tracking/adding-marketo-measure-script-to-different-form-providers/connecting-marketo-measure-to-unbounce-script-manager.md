---
unique-page-id: 18874743
description: 언바운스 스크립트 관리자에  [!DNL Marketo Measure] 연결 - [!DNL Marketo Measure]
title: 언바운스 스크립트 관리자에  [!DNL Marketo Measure] 연결 중
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# [!DNL Marketo Measure]을(를) 언바운스 스크립트 관리자에 연결 중 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure]은(는) 언바운스와 직접 통합되므로 [!DNL Salesforce]에서 랜딩 페이지 전환의 디지털 마케팅 소스를 직접 추적할 수 있습니다. 연결하려면 [!DNL Marketo Measure] 스크립트를 [언바운스 스크립트 관리자]에 추가하면 됩니다. 방법은 다음과 같습니다.

1. [!DNL Unbounce] 계정에 로그인합니다.
1. **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**&#x200B;을(를) 클릭합니다.
1. 팝업에서 [!UICONTROL Custom Script]을(를) 선택하고 이름을 &quot;[!DNL Marketo Measure Marketing Analytics]&quot;로 지정합니다. **[!UICONTROL Add Script Details]**&#x200B;을(를) 클릭합니다.
1. 헤드(Head)에서 배치(placement)를 선택합니다. 기본 랜딩 페이지 및 양식 확인 대화 상자에 스크립트를 포함합니다. 아래의 [!DNL Marketo Measure] 스크립트를 상자에 붙여 넣으십시오.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

[!DNL Marketo Measure] 통합은 unbounce.com 도메인을 사용하는 랜딩 페이지가 아닌 도메인(예: landing.mysite.com)에서 호스팅되는 한 언바운스 랜딩 페이지에서 작동합니다.
