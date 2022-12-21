---
unique-page-id: 18874722
description: 테스트 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 테스트 우수 사례
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# 테스트 우수 사례 {#best-practices-for-testing}

Adobe Analytics Mobile Apps 또는 Analytics Premium에서는 [!DNL Marketo Measure] JavaScript가 제대로 작동합니다.

## 권장되는 테스트 프로세스 {#recommended-test-process}

1. 시크릿 브라우저를 사용하거나 각 양식 제출 테스트 간에 쿠키를 지웁니다 _및_ 매번 다른 이메일 주소를 사용합니다.

   >[!TIP]
   >
   >가장 좋은 방법은 테스트라는 것을 나타내는 내용이 포함된 가짜 이메일을 사용하고, 하루 중 시간을 사용하는 것입니다. For example: `testing830am@test.com`.

1. 검색 엔진에서 검색 시작(예: `google.com`)로 이동하거나 직접 양식으로 이동합니다.

1. 고유한 이메일 주소를 사용하여 웹 사이트에서 양식을 제출합니다.

1. 양식을 제출하는 페이지의 URL과 사용된 이메일 주소를 기록합니다.

1. CRM에서 만든 레코드(리드 또는 연락처)를 찾아 해당 양식 제출을 위해 터치포인트를 적절히 만들었는지 확인합니다.

>[!NOTE]
>
>을(를) 사용할 수 있습니다 [!DNL Marketo Measure] 리드 와 같은 스톡 보고서 [!DNL Marketo Measure] 터치포인트를 사용하여 페이지 레이아웃을 업데이트하도록 선택한 경우 리드/연락처 페이지 레이아웃을 살펴봅니다 [!DNL Marketo Measure] 세부 사항. 이 작업은 데이터를 처리하는 데 시간이 걸릴 수 있습니다.
