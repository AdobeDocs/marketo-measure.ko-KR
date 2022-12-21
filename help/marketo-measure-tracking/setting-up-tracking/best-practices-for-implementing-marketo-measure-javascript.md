---
description: 구현 우수 사례 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure] - 제품 설명서
title: 구현 우수 사례 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
source-git-commit: cf144eb4bc9282ae6a260acd3735f24644292a19
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# 구현 우수 사례 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 개요 {#overview}

다음 [!DNL Marketo Measure] JavaScript는 웹 방문자를 디지털 마케팅 상호 작용을 추적하고 를 [!DNL Marketo Measure] 온라인 터치 포인트 데이터를 만드는 기능. 사용 [!DNL Marketo Measure] 전체 사이트에 올바로 그리고 포괄적으로 배포된 JavaScript는 수집된 세션 데이터가 정확한 터치 포인트 데이터를 생성하도록 해줍니다.

배포 시 일치하지 않음 [!DNL Marketo Measure] JavaScript로 인해 세션 데이터가 중단되어 다음과 같은 결과가 발생할 수 있습니다.

* 잘못된 채널/하위 채널 속성
* 소스 데이터 손실
* 높은 수준의 잘못된 직접 트래픽
* 보고가 일관되지 않음

[!DNL Marketo Measure] JavaScript는 [!DNL Marketo Measure] 성공을 위한 영업 활용 방안

## 우수 사례 {#best-practice}

의 구현 및 관리 [!DNL Marketo Measure] JavaScript에서 다음의 모범 사례를 기억하십시오.

* 모든 도메인이 [!DNL Marketo Measure] account
   * 도메인과 관련된 문제가 있는 경우 지원 센터에 문의하십시오
* 모든 페이지에 JavaScript를 배포합니다.
   * 특정 페이지에만 JavaScript를 삽입하면 세션 데이터가 중단되어 잘못된 오류가 발생합니다 [!DNL Marketo Measure] 데이터
* 터치포인트를 만들지 않으려는 사이트의 양식의 경우 를 추가해야 합니다 [!DNL Marketo Measure] 스크립트 제외
   * 이 제외 스크립트는 [!DNL Marketo Measure] 세션 데이터는 중단되지 않고 소스 데이터가 제자리에 남아 있습니다
      * 제외할 일반적인 양식의 예는 다음과 같습니다.
         * 고객 로그인
         * 암호 양식 분실
         * 양식 가입 해지
         * 경력 신청 양식
* 추가의 &quot;추가 고려 사항&quot; 및 &quot;추가 고려 사항&quot;에 대한 Forms 섹션을 검토합니다 [!DNL Marketo Measure] 아래 나열된 스크립트 리소스는 특수 처리가 필요할 수 있는 시나리오를 확인하려면 확인하십시오

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

을 설정하는 동안 [!DNL Marketo Measure] JavaScript는 초기 구현 중에 다루며, 사이트 또는 이를 관리하는 팀을 변경하면 로 인해 중단될 수 있습니다 [!DNL Marketo Measure] 추적. 을 확인하는 것이 좋습니다 [!DNL Marketo Measure] JavaScript가 매년 1회 정확하고 종합적으로 배포됩니다. 또한 조직에 웹 사이트에 대한 변경 프로토콜 설명서가 있는 경우 이러한 내용이 있는지 확인하십시오 [!DNL Marketo Measure] JavaScript는 모든 새 페이지에 보존/추가해야 합니다.

JavaScript 설정 검토를 트리거할 수 있는 기타 이유는 다음과 같습니다.

* 마케팅 팀의 이직률
* 사이트 구조 변경 및 업데이트
* 사이트 마이그레이션
* 도메인 변경 사항
* 다른 회사 및 웹 자산 획득
