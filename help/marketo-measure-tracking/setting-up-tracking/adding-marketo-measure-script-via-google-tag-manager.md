---
unique-page-id: 18874797
description: 추가 중 [!DNL Marketo Measure] 를 통해 스크립트 [!DNL Google Tag Manager] - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] 를 통해 스크립트 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 를 통해 스크립트 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

설치 시 [!DNL Marketo Measure] javascript를 적극 권장합니다. [스크립트를 하드 코딩합니다.](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target=&quot;_blank&quot;} 를 사이트에 바로 삽입할 수 있습니다. 그러나 불가능한 경우 다음을 사용할 수도 있습니다 [!DNL Google Tag Manager] (GTM)를 로드하여 [!DNL Marketo Measure] JS. 주의하십시오 [!DNL Marketo Measure] GTM을 통해 로드된 JS는 지연에 취약합니다. 지연은 스크립트 로드 시간이 지연되어 모든 양식 제출의 약 3~5%가 누락될 수 있습니다.

GTM을 통해 스크립트를 추가하기로 결정한 경우, 다음을 설정하십시오. [!DNL Marketo Measure] 스크립트를 실행 순서에서 가장 높은 우선 순위로 설정하고 앞에 동기 스크립트가 없는지 확인합니다. [!DNL Marketo Measure] 태그로 래핑되어 있습니다.

>[!NOTE]
>
>이것을 사용하세요 [Google의 지원 문서](https://support.google.com/tagmanager/answer/2772421?hl=en)자세한 내용은 {target=&quot;_blank&quot;}을 참조하십시오.

## 추가 방법 [!DNL Marketo Measure] 를 통한 JS [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. GTM을 열고 를 추가합니다 [!DNL Marketo Measure] 스크립트를 웹 사이트 컨테이너에 추가합니다. 을(를) 선택합니다. **[!UICONTROL Custom HTML tag]**.

1. 를 사용하십시오 [!DNL Marketo Measure] 아래의 스크립트를 작성하여 컨테이너에 통합합니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 클릭 **[!UICONTROL Add a Firing Rule]** 따라서 Google에서 코드 조각을 로드하도록 할 수 있습니다. *모든 페이지*.

1. 왼쪽의 컨테이너 초안 개요 섹션으로 이동합니다. 버튼을 클릭하여 컨테이너의 새 버전을 만들고 변경 사항을 게시합니다.
