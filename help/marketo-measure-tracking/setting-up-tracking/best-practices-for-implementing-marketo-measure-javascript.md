---
description: 구현 모범 사례 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]
title: ' [!DNL Marketo Measure] JavaScript 구현을 위한 모범 사례'
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# [!DNL Marketo Measure] JavaScript 구현을 위한 모범 사례 {#best-practices-for-implementing-marketo-measure-javascript}

## 개요 {#overview}

[!DNL Marketo Measure] JavaScript은 웹 방문자의 디지털 마케팅 상호 작용을 추적하고 온라인 접점 데이터를 만드는 [!DNL Marketo Measure] 기능의 핵심입니다. [!DNL Marketo Measure] JavaScript이 전체 사이트에 올바르게 포괄적으로 배포되면 수집된 세션 데이터가 정확한 접점 데이터를 생성할 수 있습니다.

[!DNL Marketo Measure] JavaScript 배포가 일치하지 않으면 세션 데이터가 중단되어 다음과 같은 결과가 발생할 수 있습니다.

* 잘못된 채널/하위 채널 속성
* 소스 데이터 손실
* 높은 수준의 잘못된 직접 트래픽
* 일관되지 않은 보고

[!DNL Marketo Measure] JavaScript은 [!DNL Marketo Measure] 계정의 기본 부분이며 성공을 위한 키입니다!

## 우수 사례 {#best-practice}

[!DNL Marketo Measure] JavaScript을 구현하고 관리하는 방법은 다음 모범 사례를 참고하십시오.

* 모든 도메인이 [!DNL Marketo Measure] 계정에 나열되는지 확인
   * 도메인과 관련하여 문제가 있는 경우 지원 센터에 문의하십시오.
* 모든 페이지에 JavaScript을 배포합니다.
   * 특정 페이지에만 JavaScript을 배치하면 세션 데이터가 중단되어 [!DNL Marketo Measure] 데이터가 올바르지 않게 됩니다.
* 사이트에서 터치포인트를 만들지 않으려는 양식의 경우 [!DNL Marketo Measure] 제외 스크립트를 추가해야 합니다
   * 이 제외 스크립트는 [!DNL Marketo Measure] 세션 데이터가 중단되지 않고 원본 데이터가 그대로 유지되도록 합니다
      * 제외할 일반적인 양식의 예는 다음과 같습니다.
         * 고객 로그인
         * 암호 찾기 양식
         * 양식 구독 취소
         * 경력 지원 양식
* 아래 나열된 [!DNL Marketo Measure] 스크립트 리소스 추가 섹션의 &quot;추가 고려 사항&quot; 및 &quot;특별히 주의할 Forms&quot; 섹션을 검토하여 특별한 처리가 필요할 수 있는 시나리오를 확인하십시오

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

초기 구현 중에 [!DNL Marketo Measure] JavaScript 설정이 적용되지만 사이트 또는 이를 관리하는 팀을 변경하면 [!DNL Marketo Measure] 추적이 중단될 수 있습니다. [!DNL Marketo Measure] JavaScript이 매년 한 번 올바로 포괄적으로 배포되었는지 확인하는 것이 좋습니다. 또한 조직에 웹 사이트에 대한 변경 프로토콜 문서 유형이 있는 경우 [!DNL Marketo Measure] JavaScript을 모든 새 페이지에 유지/추가해야 한다는 설명이 있는지 확인하십시오.

JavaScript 설정 검토를 트리거할 수 있는 다른 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* 사이트 구조 변경 및 업데이트
* 사이트 마이그레이션
* 도메인 변경 사항
* 기타 회사 및 웹 자산 인수
