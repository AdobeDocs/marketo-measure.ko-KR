---
unique-page-id: 18874732
description: UTM 매개 변수 설정에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: UTM 매개 변수 설정에 대한 우수 사례
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# UTM 매개 변수 설정에 대한 우수 사례 {#best-practices-for-setting-up-utm-parameters}

UTM 매개 변수는 마케팅 데이터를 분류하고 분류하는 좋은 방법입니다. [!DNL Marketo Measure] 은 을 사용하고 모든 UTM 매개 변수를 캡처하여 Salesforce 및 [!DNL Marketo Measure] 앱. 이러한 정보를 통해 리드, 영업 기회, 거래 성사/거래 성사 등에 대한 세부 사항을 파악할 수 있습니다.

를 활용할 수 있습니다 [Google URL 빌더](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} 모든 UTM 링크를 보다 쉽게 추적하려면 다음을 수행하십시오.

## 각 매개 변수에 대한 높은 수준 값 {#high-level-values-for-each-parameter}

**utm_medium**: 이 필드는 중간 필드에 매핑됩니다. utm_medium을 사용하여 높은 수준의 채널을 나타냅니다.

예, [!UICONTROL Social], CPC, 이메일, 웹, 유기

이 필드를 사용하여 하위 채널을 호출하지 마십시오.

**utm_source**: 이 필드는 터치 포인트 소스 필드에 매핑됩니다. utm_source를 사용하여 리드가 시작되는 하위 채널을 정의합니다.

예: Facebook, Twitter, Linkedin, Dropping_email, Email_blast, newsletter.

간단합니다. 이 매개 변수를 사용하여 재타겟팅, 스폰서 등과 같은 광고 유형을 표시하지 마십시오. utm_source = homepage, webdirect, website를 추가하지 마십시오. [!DNL Marketo Measure] 이 정보는 자동으로 입력됩니다.

**utm_campaign**: 이 필드는 광고 캠페인 이름에 매핑됩니다. utm_campaign을 사용하여 캠페인의 제목을 광고 플랫폼에 있는 그대로 또는 내부적으로 참조되는 것으로 나타냅니다.

지리적 위치, 광고 네트워크 유형(디스플레이 v 검색) 등을 나타내는 좋은 매개 변수입니다.

공백 대신 밑줄을 사용하고 구두점을 사용하지 않는 것이 좋습니다. 이렇게 하면 매개 변수를 읽을 때 브라우저별로 인코딩 오류가 발생할 가능성이 줄어듭니다.

예: AU_Idea_for_an_App_50k

**utm_content**: 광고 컨텐츠에 매핑됩니다. utm_content 매개 변수에서 광고 제목을 사용합니다. 이미지 광고인 경우 광고 제목을 사용하고 광고 차원을 포함합니다.

예, [광고 제목] 200x400px

**utm_term**: 키워드 텍스트에 매핑됩니다. 이 매개 변수를 사용하여 광고 실행과 관련된 키워드를 나타냅니다.

광고와 관련된 키워드가 없는 경우 이 매개 변수는 비워 둡니다.

예: iPhone 앱 아이디어

**간단하고 간결하게 유지하십시오. 노력, 용어 및 채널을 중복하지 마십시오.**

다음과 같이 UTM 계층 구조를 가정합니다.

보통 > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

예: [!UICONTROL display] 광고가 Facebook에 배치되면, 다음을 권장합니다.

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

용어/채널은 중복되지 않으며 utm_term은 이 경우에는 사용되지 않습니다.

질문이 있는 경우 Adobe 계정 팀(계정 관리자)에 문의하거나 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
