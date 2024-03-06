---
unique-page-id: 18874570
description: Marketo Measure 프레임워크 - Marketo Measure - 제품 설명서
title: Marketo Measure 프레임워크
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
feature: Fundamentals
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# Marketo Measure 프레임워크 {#marketo-measure-framework}

Marketo Measure 프레임워크를 구성하는 4가지 주요 구성 요소에 대해 자세히 알아보십시오. Marketo Measure은 이러한 애플리케이션을 사용하여 데이터를 추적, 구성 및 관리하고 보고 기능을 제공합니다. Marketo Measure 프레임워크를 구성하는 네 가지 구성 요소는 다음과 같습니다.

* Marketo Measure JavaScript
* CRM 통합
* 타사 애플리케이션/시스템
* Marketo Measure 애플리케이션

## Marketo Measure JavaScript {#marketo-measure-javascript}

Marketo Measure JavaScript는 잠재 고객/잠재 고객이 조직과 맺고 있는 모든 온라인 마케팅 상호 작용(터치포인트라고도 함)을 추적합니다. 닫기 전에 추가되는 사용자 지정 스크립트입니다 `</head>` 를 클릭하여 웹 사이트의 모든 페이지에 태그를 추가합니다.

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>Marketo Measure JS를 추가하는 방법에 대한 지침은 [여기를 클릭하십시오](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md).

Marketo Measure의 JS는 웹 방문(익명 웹 방문 포함), 일반 트래픽/페이지 탐색, 콘텐츠 다운로드 및 양식 제출의 데이터를 캡처합니다. 이 데이터는 CRM에 푸시되고 각 마케팅 상호 작용은 터치포인트로 표시됩니다.

## CRM 통합 {#crm-integrations}

Marketo Measure은 CRM과 통합되어 Marketo Measure JS에서 캡처하는 모든 데이터를 수용하고 구성합니다. 현재 Marketo Measure에는 두 개의 CRM과 API 통합이 있습니다.

![](assets/1-2.png)

CRM에 Marketo Measure 데이터를 표시하면 각 터치포인트와 관련된 세부적인 정보를 보고 채널의 실적을 파악하는 보고서를 생성할 수 있습니다.

## 서드파티 애플리케이션 {#third-party-applications}

대부분의 마케터는 마케팅 활동을 실행하기 위해 몇 가지 다른 애플리케이션에 의존합니다. Salesforce 및 MS Dynamics 외에도 Marketo Measure은 13개의 타사 응용 프로그램(아래 목록)과 통합됩니다.

![](assets/2-1.png)

위의 애플리케이션을 사용하여 마케팅 활동을 실행하는 경우 이러한 계정을 Marketo Measure 계정에 연결할 수 있습니다. 이렇게 하면 데이터를 쉽게 추적하고 Marketo Measure 계정으로 전송할 수 있습니다.

## Marketo Measure 애플리케이션 {#marketo-measure-application}

Marketo Measure 애플리케이션을 사용하여 속성 데이터를 보고 보고하고, 계정 설정을 구성하고, 계정 정보를 업데이트합니다. Marketo Measure 앱의 기본 메뉴 항목은 다음과 같습니다.

**계정 구성**

여기서 회사의 일반 정보를 업데이트하고 Marketo Measure Javascript에 액세스할 수 있습니다.

**설정**

이 메뉴 항목을 사용하면 속성 및 채널 매핑 설정을 구성하고 CRM 및 타사 애플리케이션과의 통합을 관리하며 Marketo Measure 계정 사용자를 확인/추가하고 청구 정보를 업데이트할 수 있습니다.

**마케팅 ROI 대시보드**

마케팅 ROI 대시보드 메뉴 항목에서는 채널 성능, 활동 및 비용 측면에서 데이터를 시각화할 수 있습니다.
