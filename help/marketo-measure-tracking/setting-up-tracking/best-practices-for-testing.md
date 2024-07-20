---
unique-page-id: 18874722
description: 테스트 모범 사례 - [!DNL Marketo Measure]
title: 테스트 우수 사례
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# 테스트 우수 사례 {#best-practices-for-testing}

[!DNL Marketo Measure] JavaScript이 제대로 작동하는지 확인하려면 다양한 유형의 양식을 모두 테스트해야 합니다.

## 권장되는 테스트 프로세스 {#recommended-test-process}

1. 시크릿 브라우저를 사용하거나 각 양식 제출 테스트 _과(와)_ 간에 쿠키를 지웁니다. 매번 다른 전자 메일 주소를 사용합니다.

   >[!TIP]
   >
   >가장 좋은 방법은 하루 중 시간뿐만 아니라 테스트임을 나타내는 것을 포함하는 가짜 이메일을 사용하는 것입니다. 예: `testing830am@test.com`.

1. 검색 엔진(예: `google.com`)에서 검색을 시작하거나 양식으로 바로 이동합니다.

1. 고유한 이메일 주소를 사용하여 웹 사이트에 양식을 제출합니다.

1. 양식을 제출할 페이지의 URL과 사용된 이메일 주소를 기록합니다.

1. 해당 양식 제출을 위해 CRM(리드 또는 연락처)에서 만든 레코드를 찾아 터치포인트가 적절하게 생성되었는지 확인합니다.

>[!NOTE]
>
>[!DNL Marketo Measure] 접점이 있는 리드와 같은 [!DNL Marketo Measure] 스톡 보고서를 사용하거나 [!DNL Marketo Measure] 세부 정보로 페이지 레이아웃을 업데이트하도록 선택한 경우 리드/연락처 페이지 레이아웃을 볼 수 있습니다. 이 작업을 수행하려면 데이터를 처리하는 데 시간이 걸릴 수 있습니다.
