---
unique-page-id: 18874797
description: 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager] - [!DNL Marketo Measure]
title: 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

설치 시 [!DNL Marketo Measure] JavaScript를 사용하십시오. [스크립트 하드 코딩](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 사이트로 바로 이동합니다. 가능하지 않은 경우 [!DNL Google Tag Manager] (GTM): [!DNL Marketo Measure] JS. 참고: [!DNL Marketo Measure] GTM을 통해 로드된 JS는 지연되기 쉽습니다. 지연으로 인해 스크립트 로드 시간이 지연되어 모든 양식 제출의 약 3~5%가 누락될 수 있습니다.

GTM을 통해 스크립트를 추가하기로 결정한 경우 [!DNL Marketo Measure] 실행 순서에서 가장 높은 우선 순위로 스크립트를 만들고 앞에 동기 스크립트가 없는지 확인합니다. [!DNL Marketo Measure] 태그 : GTM 지연으로 인한 영향을 줄이십시오.

>[!NOTE]
>
>사용 [Google의 지원 문서](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 자세히 알아보십시오.

## 추가 방법 [!DNL Marketo Measure] 를 통한 JS [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. GTM을 열고 [!DNL Marketo Measure] 웹 사이트 컨테이너의 스크립트입니다. 다음을 선택하십시오. **[!UICONTROL Custom HTML tag]**.

1. 사용 [!DNL Marketo Measure] 아래 스크립트를 작성하여 컨테이너에 통합합니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 클릭 **[!UICONTROL Add a Firing Rule]** Google에 코드 조각을 로드하도록 요청할 수 있습니다. *모든 페이지*.

1. 왼쪽의 컨테이너 초안 개요 섹션으로 이동합니다. 버튼을 클릭하여 컨테이너의 버전을 만들고 변경 사항을 게시합니다.
