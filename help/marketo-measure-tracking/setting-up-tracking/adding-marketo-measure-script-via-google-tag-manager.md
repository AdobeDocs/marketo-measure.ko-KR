---
unique-page-id: 18874797
description: ' [!DNL Google Tag Manager] - [!DNL Marketo Measure]을(를) 통해  [!DNL Marketo Measure] 스크립트 추가 중'
title: ' [!DNL Google Tag Manager]을(를) 통해  [!DNL Marketo Measure] 스크립트 추가'
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# [!DNL Google Tag Manager]을(를) 통해 [!DNL Marketo Measure] 스크립트 추가 {#adding-marketo-measure-script-via-google-tag-manager}

[!DNL Marketo Measure] JavaScript을 설치할 때는 사이트에 직접 [스크립트를 하드 코딩](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"}하는 것이 좋습니다. 불가능한 경우 [!DNL Google Tag Manager] (GTM)을 사용하여 [!DNL Marketo Measure] JS를 로드할 수도 있습니다. GTM을 통해 로드된 [!DNL Marketo Measure] JS는 지연되기 쉽습니다. 지연으로 인해 스크립트 로드 시간이 지연되어 모든 양식 제출의 약 3~5%가 누락될 수 있습니다.

GTM을 통해 스크립트를 추가하기로 결정한 경우 실행 순서에서 [!DNL Marketo Measure] 스크립트를 가장 높은 우선 순위로 설정하고 [!DNL Marketo Measure] 태그 앞에 동기 스크립트가 없는지 확인하여 GTM 지연으로 인한 영향을 줄이십시오.

>[!NOTE]
>
>자세한 내용은 이 [Google의 지원 문서](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"}를 참조하세요.

## [!DNL Google Tag Manager]을(를) 통해 [!DNL Marketo Measure] JS를 추가하는 방법 {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. GTM을 열고 웹 사이트 컨테이너에 [!DNL Marketo Measure] 스크립트를 추가합니다. **[!UICONTROL Custom HTML tag]**&#x200B;을(를) 선택하십시오.

1. 아래의 [!DNL Marketo Measure] 스크립트를 사용하여 컨테이너에 통합하십시오.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Google에서 *모든 페이지*&#x200B;에 코드 조각을 로드하도록 하려면 **[!UICONTROL Add a Firing Rule]**&#x200B;을(를) 클릭하십시오.

1. 왼쪽의 컨테이너 초안 개요 섹션으로 이동합니다. 버튼을 클릭하여 컨테이너의 버전을 만들고 변경 사항을 게시합니다.
