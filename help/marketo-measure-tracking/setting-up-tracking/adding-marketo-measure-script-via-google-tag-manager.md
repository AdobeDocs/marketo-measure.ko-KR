---
unique-page-id: 18874797
description: 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager] - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 다음을 통한 스크립트 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

설치 시 [!DNL Marketo Measure] javascript를 사용하는 것이 좋습니다 [스크립트 하드 코딩](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 을 사이트에 바로 추가합니다. 그러나 가능하지 않은 경우 다음을 사용할 수도 있습니다. [!DNL Google Tag Manager] (GTM): [!DNL Marketo Measure] JS. 다음을 참고하십시오. [!DNL Marketo Measure] GTM을 통해 로드된 JS는 지연되기 쉽습니다. 지연으로 인해 스크립트 로드 시간이 지연되어 모든 양식 제출의 약 3~5%가 누락될 수 있습니다.

GTM을 통해 스크립트를 추가하기로 결정한 경우 [!DNL Marketo Measure] 실행 순서에서 가장 높은 우선 순위로 스크립트를 만들고 앞에 동기 스크립트가 없는지 확인합니다. [!DNL Marketo Measure] 는 GTM 지연으로 인한 영향을 줄이기 위해 를 호출합니다.

>[!NOTE]
>
>이 항목을 사용하십시오 [Google의 지원 문서](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 자세히 알아보십시오.

## 추가 방법 [!DNL Marketo Measure] 를 통한 JS [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. GTM을 열고 [!DNL Marketo Measure] 웹 사이트 컨테이너의 스크립트입니다. 다음을 선택하십시오. **[!UICONTROL Custom HTML tag]**.

1. 사용 [!DNL Marketo Measure] 아래 스크립트를 작성하여 컨테이너에 통합합니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 클릭 **[!UICONTROL Add a Firing Rule]** Google에 코드 조각을 로드하도록 요청할 수 있습니다. *모든 페이지*.

1. 왼쪽의 컨테이너 초안 개요 섹션으로 이동합니다. 컨테이너의 새 버전을 만들고 변경 사항을 게시하려면 버튼을 클릭합니다.
