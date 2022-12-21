---
unique-page-id: 18874570
description: Marketo Measure Framework - Marketo 측정 - 제품 설명서
title: Marketo Measure Framework
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
source-git-commit: 7eb5ef616e3ae77d53056496f9a1b301ce59d6ee
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Marketo Measure Framework {#marketo-measure-framework}

Marketo Measure 프레임워크를 구성하는 4가지 주요 구성 요소에 대해 자세히 알아보십시오. Marketo Measurement는 이러한 애플리케이션을 사용하여 데이터를 추적, 구성 및 저장하고 보고 기능을 제공합니다. Marketo Measurement 프레임워크를 구성하는 네 가지 구성 요소는 다음과 같습니다.

* Marketo Measure의 JavaScript
* CRM 통합
* 타사 애플리케이션/시스템
* Marketo 측정 애플리케이션

## Marketo 측정 JavaScript {#marketo-measure-javascript}

Marketo 측정 JavaScript는 잠재 고객/리드가 조직에 가지고 있는 터치포인트라고도 하는 모든 온라인 마케팅 상호 작용을 추적합니다. 닫기 전에 추가된 사용자 지정 스크립트입니다 `</head>` 태깅 합니다.

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>Marketo Measure JS를 추가하는 방법에 대한 지침은 [여기를 클릭하십시오.](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md).

Marketo Measurement의 JS는 웹 방문(익명의 웹 방문 포함), 일반 트래픽/페이지 탐색, 컨텐츠 다운로드 및 양식 제출의 데이터를 캡처합니다. 이 데이터가 CRM에 푸시되고 각 마케팅 상호 작용이 터치 포인트로 표시됩니다.

## CRM 통합 {#crm-integrations}

Marketo Measurement는 CRM과 통합되므로 Marketo Measure JS에서 캡처한 모든 데이터를 보유하고 구성할 수 있습니다. 현재 Marketo Measure에는 두 개의 CRM과 API 통합이 있습니다.

![](assets/1-2.png)

CRM에서 Marketo 측정 데이터를 표시하면 각 터치 포인트와 관련된 세부 정보를 보고 보고서가 생성되어 채널이 어떻게 작동하는지 파악할 수 있습니다.

## 타사 애플리케이션 {#third-party-applications}

대부분의 마케터는 마케팅 활동을 실행하기 위해 몇 가지 다른 애플리케이션에 의존합니다. Salesforce 및 MS Dynamics 외에도 Marketo Measurement는 13개의 타사 애플리케이션(아래에 나열됨)과 통합됩니다.

![](assets/2-1.png)

위의 애플리케이션을 사용하여 마케팅 활동을 실행하는 경우 해당 계정을 Marketo 측정 계정에 연결할 수 있습니다. 이렇게 하면 Marketo Measurement 계정으로 데이터를 쉽게 추적하고 전송할 수 있습니다.

## Marketo 측정 애플리케이션 {#marketo-measure-application}

Marketo 측정 프로그램은 속성 데이터를 보고 보고하고, 계정 설정을 구성하고, 계정 정보를 업데이트하는 데 사용됩니다. Marketo 측정 앱의 기본 메뉴 항목에는 다음이 포함됩니다.

**계정 구성**

여기에서 회사의 일반 정보를 업데이트하고 Marketo Measure Javascript에 액세스할 수 있습니다.

**설정**

이 메뉴 항목을 사용하면 속성 및 채널 매핑 설정을 구성하고, CRM 및 타사 애플리케이션과의 통합을 관리하고, Marketo Measurement 계정 사용자를 보기/추가하고, 청구 정보를 업데이트할 수 있습니다.

**마케팅 ROI 대시보드**

마케팅 ROI 대시보드 메뉴 항목에서는 채널 성능, 활동 및 비용 측면에서 데이터를 시각화할 수 있습니다.
