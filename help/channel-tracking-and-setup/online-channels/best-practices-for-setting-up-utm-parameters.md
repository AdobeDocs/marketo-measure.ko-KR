---
unique-page-id: 18874732
description: UTM 매개 변수 설정에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: UTM 매개 변수 설정에 대한 우수 사례
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# UTM 매개 변수 설정에 대한 우수 사례 {#best-practices-for-setting-up-utm-parameters}

UTM 매개 변수는 마케팅 데이터를 분류할 수 있는 좋은 방법입니다. [!DNL Marketo Measure] 모든 UTM 매개 변수를 사용하고 캡처하여 Salesforce 및 의 필드를 채웁니다. [!DNL Marketo Measure] 앱. 이 정보를 통해 잠재 고객, 영업 기회 및 비공개/성공 거래의 출처를 구체적으로 파악할 수 있습니다.

다음을 활용할 수 있습니다. [Google URL 빌더](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} 모든 UTM 링크를 보다 쉽게 추적하려면 다음 작업을 수행하십시오.

## 각 매개 변수에 대한 높은 수준 값 {#high-level-values-for-each-parameter}

**utm_medium**: 이 필드는 중간 필드에 매핑됩니다. utm_medium 을 사용하여 상위 레벨 채널을 나타냅니다.

예: [!UICONTROL Social], CPC, 이메일, 웹, 유기

이 필드를 사용하여 하위 채널을 호출하지 마십시오.

**utm_source**: 이 필드는 터치포인트 소스 필드에 매핑됩니다. utm_source를 사용하여 리드가 시작되는 하위 채널을 정의합니다.

예: Facebook, Twitter, Linkedin, Drip_email, Email_blast, 뉴스레터.

단순하게 유지하십시오. 이 매개 변수를 사용하여 리타겟팅, 스폰서 등과 같은 광고 유형을 표시하지 마십시오. utm_source = homepage, webdirect, website를 추가하지 마십시오. [!DNL Marketo Measure] 이(가) 자동으로 이 정보를 입력합니다.

**utm_campaign**: 이 필드는 광고 캠페인 이름에 매핑됩니다. utm_campaign을 사용하여 광고 플랫폼에 있거나 내부적으로 지칭되는 캠페인의 제목을 나타냅니다.

지리적 위치, 광고 네트워크 유형(디스플레이 v. 검색) 등을 표시하는 데 유용한 매개 변수도 있습니다.

공백 대신 밑줄을 사용하고, 구두점 사용은 피하는 것이 좋습니다. 이렇게 하면 매개 변수를 읽을 때 브라우저별 인코딩 오류 가능성이 줄어듭니다.

예: AU_Idea_for_an_App_50k

**utm_content**: 광고 콘텐츠에 매핑됩니다. utm_content 매개 변수에서 광고 제목 을 사용합니다. 이미지 광고인 경우 광고 제목 을 사용하고 광고 차원을 포함합니다.

예: [광고 제목] 200x400px

**utm_term**: 키워드 텍스트에 매핑됩니다. 이 매개 변수를 사용하여 광고 실행과 관련된 키워드를 나타냅니다.

광고와 관련된 키워드가 없는 경우 이 매개 변수를 비워 둡니다.

예: iPhone 앱 아이디어

**단순하고 간결하게 유지하십시오. 노력, 용어 및 채널을 복제하지 마십시오.**

다음과 같은 UTM 계층을 상상해 보십시오.

보통 > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

예: [!UICONTROL display] ad가 Facebook에 배치되었으므로 다음 사항을 권장합니다.

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

용어/채널은 복제되지 않으며 이 경우 utm_term은 사용되지 않습니다.

질문이 있는 경우 Adobe 계정 팀(계정 관리자)에 연락하거나 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
