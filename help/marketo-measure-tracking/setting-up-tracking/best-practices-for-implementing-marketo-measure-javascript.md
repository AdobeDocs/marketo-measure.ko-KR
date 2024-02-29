---
description: 구현을 위한 우수 사례 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]
title: 구현을 위한 우수 사례 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# 구현을 위한 우수 사례 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 개요 {#overview}

다음 [!DNL Marketo Measure] JavaScript는 웹 방문자의 디지털 마케팅 상호 작용을 추적하고 [!DNL Marketo Measure] 온라인 터치포인트 데이터를 만드는 기능. 사용 [!DNL Marketo Measure] 전체 사이트에 걸쳐 정확하고 종합적으로 배포된 JavaScript를 사용하면 수집된 세션 데이터가 정확한 접점 데이터를 생성할 수 있습니다.

배포 불일치 [!DNL Marketo Measure] JavaScript로 인해 세션 데이터에 중단으로 인해 다음이 발생할 수 있습니다.

* 잘못된 채널/하위 채널 속성
* 소스 데이터 손실
* 높은 수준의 잘못된 직접 트래픽
* 일관되지 않은 보고

[!DNL Marketo Measure] JavaScript는 [!DNL Marketo Measure] 계정 및 성공 열쇠입니다!

## 우수 사례 {#best-practice}

의 구현 및 관리와 관련된 경우 [!DNL Marketo Measure] JavaScript에서는 다음 모범 사례를 염두에 두십시오.

* 모든 도메인이 [!DNL Marketo Measure] account
   * 도메인과 관련하여 문제가 있는 경우 지원 센터에 문의하십시오.
* 모든 페이지에 JavaScript를 배포합니다.
   * 특정 페이지에만 JavaScript를 배치하면 세션 데이터가 중단되어 올바르지 않게 됩니다 [!DNL Marketo Measure] 데이터
* 사이트에서 터치포인트를 만들지 않으려는 양식의 경우 [!DNL Marketo Measure] 제외 스크립트
   * 이 제외 스크립트는 [!DNL Marketo Measure] 세션 데이터는 중단되지 않고 소스 데이터가 그대로 유지됩니다
      * 제외할 일반적인 양식의 예는 다음과 같습니다.
         * 고객 로그인
         * 암호 찾기 양식
         * 양식 구독 취소
         * 경력 지원 양식
* 추가 의 &quot;추가 고려 사항&quot; 및 &quot;특별히 주의를 기울일 Forms&quot; 섹션을 검토하십시오 [!DNL Marketo Measure] 특수 처리가 필요할 수 있는 시나리오를 확인하기 위해 아래 나열된 스크립트 리소스

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

을(를) 설정하는 동안 [!DNL Marketo Measure] JavaScript는 초기 구현 중에 적용되므로 이를 관리하는 사이트 또는 팀을 변경하면 [!DNL Marketo Measure] 추적. 다음을 확인하는 것이 좋습니다. [!DNL Marketo Measure] JavaScript는 1년에 한 번 올바로 포괄적으로 배포됩니다. 또한 조직에 웹 사이트에 대한 변경 프로토콜 설명서 유형이 있는 경우 다음을 설명하는 부분이 있는지 확인합니다. [!DNL Marketo Measure] JavaScript는 모든 새 페이지에 유지/추가해야 합니다.

JavaScript 설정 검토를 트리거할 수 있는 다른 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* 사이트 구조 변경 및 업데이트
* 사이트 마이그레이션
* 도메인 변경 사항
* 기타 회사 및 웹 자산 인수
