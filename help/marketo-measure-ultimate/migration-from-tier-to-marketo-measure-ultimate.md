---
description: ' [!DNL Marketo Measure] 계층화된 구독에서  [!DNL Marketo Measure] Ultimate로 이동할 때의 마이그레이션 프로세스에 대해 알아봅니다.'
hide: true
hidefromtoc: true
title: 계층에서  [!DNL Marketo Measure] Ultimate로 마이그레이션
feature: Integration, Tracking, Attribution
source-git-commit: 0c94276bec390bb67dafe5dd679c1a0378a05c85
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# 계층 1-2에서 [!DNL Marketo Measure] Ultimate로 마이그레이션 {#migration-from-tier-to-marketo-measure-ultimate}

Tier 1 또는 2 구독에서 Marketo Measure Ultimate로 이동하는 사용자의 마이그레이션 프로세스에 대해 간략하게 설명합니다(영문).

>[!IMPORTANT]
>
>마이그레이션이 완료될 때까지 기존 계층 인스턴스를 유지합니다.

## 데이터 수집 {#data-collection}

### 웹 트래픽 데이터 {#web-traffic-data}

* JavaScript 배포에는 변경 사항이 필요하지 않습니다.

* 새 Ultimate 인스턴스에서 도메인을 활성화합니다.

* 필요한 경우 티켓을 제출하여 이전 웹 데이터를 마이그레이션하고 재처리합니다.

* 광고 통합은 변경되지 않지만 Ultimate에서 다시 연결하는 것을 잊지 마십시오. 그렇게 하기 전에 계층 테넌트에서 광고 계정의 연결을 끊어야 합니다.

>[!NOTE]
>
>이전 광고 비용 데이터는 가져오지 않습니다. 광고 계정이 다시 연결된 후에만 광고 비용 데이터를 가져옵니다.

### 엔터프라이즈 데이터 연결 {#enterprise-data-connection}

CRM 및 Marketo Engage 연결을 포함하여 AEP의 모든 소스 데이터 연결을 다시 구현합니다.

## 데이터 변환 {#data-transformation}

* 리드-계정 일치 및 예측 참여 점수를 포함한 Account-Based Marketing 기능은 Ultimate에서 사용할 수 없습니다.

   * 그러나 AEP를 통해 리드-계정 일치 결과를 가져와 플랫폼 내에서 사용할 수 있습니다.

* Ultimate에서는 직접 CRM 연결이 없으므로 CRM 기록 단계 전환을 직접 읽지 않고 유추합니다.

   * 영업 기회 기록과 타임스탬프를 읽고 현재 단계를 확인한 다음 과거 단계를 추론합니다.

## 보고 {#reporting}

* Ultimate는 데이터를 CRM으로 다시 푸시하지 않습니다.

   * 데이터를 CRM으로 다시 푸시하려는 경우 Marketo Measure Snowflake에서 CRM으로 데이터를 추출하려면 사용자 지정 ETL 파이프라인이 필요합니다. CRM에서 사용자 지정 데이터 모델을 설정해야 합니다.

* 모든 Discover 대시보드는 Attribution AI 대시보드의 추가로 계층형 솔루션과 동일하게 유지됩니다.
