---
unique-page-id: 18874722
description: 테스트 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 테스트 우수 사례
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# 테스트 우수 사례 {#best-practices-for-testing}

다음과 같은 여러 유형의 양식을 모두 테스트해야 합니다 [!DNL Marketo Measure] JavaScript가 제대로 작동하는 중입니다.

## 권장되는 테스트 프로세스 {#recommended-test-process}

1. 시크릿 브라우저를 사용하거나 각 양식 제출 테스트 간에 쿠키를 지웁니다. _및_ 매번 다른 이메일 주소를 사용합니다.

   >[!TIP]
   >
   >가장 좋은 방법은 하루 중 시간뿐만 아니라 테스트임을 나타내는 것을 포함하는 가짜 이메일을 사용하는 것입니다. For example: `testing830am@test.com`.

1. 검색 엔진에서 검색을 시작합니다(예: `google.com`) 또는 양식으로 바로 이동합니다.

1. 고유한 이메일 주소를 사용하여 웹 사이트에 양식을 제출합니다.

1. 양식을 제출하는 페이지의 URL과 사용된 이메일 주소를 기록합니다.

1. 해당 양식 제출을 위해 CRM(리드 또는 연락처)에서 만든 레코드를 찾아 터치포인트가 적절하게 생성되었는지 확인합니다.

>[!NOTE]
>
>다음을 사용할 수 있습니다. [!DNL Marketo Measure] 다음과 같은 잠재 고객 보고서 [!DNL Marketo Measure] 터치 포인트를 사용하거나 리드/연락처 페이지 레이아웃을 살펴보십시오. [!DNL Marketo Measure] 세부 정보. 이 작업을 수행하려면 데이터를 처리하는 데 시간이 걸릴 수 있습니다.
