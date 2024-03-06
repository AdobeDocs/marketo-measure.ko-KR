---
description: '[!DNL Marketo Measure] Ultimate 구현 안내서 - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Ultimate 구현 안내서'
feature: Integration, Tracking, Attribution
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 0%

---

# [!DNL Marketo Measure] Ultimate 구현 안내서 {#marketo-measure-ultimate-implementation-guide}

이 문서는 Marketo Measure Ultimate의 구현 가이드 역할을 하며, 성공적인 통합 및 활용을 보장하기 위한 명확한 단계와 통찰력을 제공합니다.

## 표준 계층보다 Ultimate 사용 시 주요 차이점 {#main-differences-when-using-ultimate-over-standard-tiers}

AEP를 통해 B2B 데이터 가져오기: 마케터는 AEP를 통해 B2B 데이터(예: 계정, 기회, 연락처, 리드, 캠페인, 캠페인 멤버, 활동)를 가져와야 합니다. 거의 모든 데이터 소스 및 동일한 유형의 여러 데이터 소스에서 수집하여 속성을 위해 모든 데이터를 가져옵니다.

* Salesforce 및 Dynamics뿐만 아니라 거의 모든 CRM에 사용할 수 있습니다.
* 여러 CRM 인스턴스 연결 및/또는 MAP 인스턴스를 하나의 Marketo Measure 인스턴스에 연결합니다.
* 타사 웨비나 등록 및 참가 데이터를 가져옵니다.

Ultimate에서는 더 이상 직접 CRM 및 Marketo Engage 연결을 사용할 수 없습니다.

* Ultimate는 데이터를 CRM에 다시 푸시하지 않습니다. 고객은 Data Warehouse에서 데이터를 사용할 수 있습니다.
* 마케터는 직접 연결을 통해 Ad Platform 데이터를 계속 가져오고 Marketo Measure Javascript를 통해 웹 활동을 추적합니다.

Ultimate 사용자는 AEP가 프로비저닝됩니다. 이미 AEP가 있는 경우 새 인스턴스를 다시 프로비저닝하지 않습니다.

* 제공된 AEP 버전에는 모든 소스 커넥터, 스키마 데이터 모델링, 데이터 세트, Ad Hoc Query Service 및 Marketo Measure 전용 대상이 포함됩니다.

자세히 알아보기 [Marketo Measure Ultimate](/help/marketo-measure-ultimate/marketo-measure-ultimate-overview.md){target="_blank"}.

## 스키마 및 데이터 세트 {#schemas-and-datasets}

>[!NOTE]
>
>체크아웃 [스키마의 빌딩 블록](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#building-blocks-of-a-schema){target="_blank"} 스키마, 클래스 및 필드 그룹에 대한 개요입니다.

**XDM 스키마 = 클래스 + 스키마 필드 그룹&#42;**

* 필수 필드는 변경할 수 없습니다. 고객은 필요에 따라 사용자 정의 필드를 만들고 추가할 수 있습니다.
* 계층 구조를 기반으로 한 필드 이름의 예: accountOrganization.annualRevenue.amount

&#42; _스키마는 클래스와 0개 이상의 스키마 필드 그룹으로 구성됩니다. 즉, 필드 그룹을 사용하지 않고 데이터 세트 스키마를 구성할 수 있습니다._

![](assets/marketo-measure-ultimate-implementation-guide-1.png)

[데이터 세트 개요](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target="_blank"}: AEP에 성공적으로 수집된 모든 데이터는 데이터 세트로 Data Lake 내에 보관됩니다. 데이터 집합은 스키마(열) 및 필드(행)를 포함하는 데이터 수집을 위한 저장소 및 관리 구성입니다.

## 스키마 만들기 {#creating-a-schema}

10개의 표준 B2B 스키마를 만들려면 자동 생성 유틸리티를 사용하는 것이 좋습니다.

* 유틸리티를 다운로드하고 설정하는 단계 [은(는) 여기에서 찾을 수 있음](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces.html#set-up-b2b-namespaces-and-schema-auto-generation-utility){target="_blank"}.

이 있는 사용자의 경우 _**CDP 권한**_: 소스 페이지로 이동하여 스키마를 만듭니다.

* 소스에서 데이터 추가 > 템플릿 사용을 선택합니다.

![](assets/marketo-measure-ultimate-implementation-guide-2.png)

* 계정 및 모든 B2B 템플릿을 선택하여 10개의 표준 B2B 스키마를 만듭니다.

![](assets/marketo-measure-ultimate-implementation-guide-3.png)

## 데이터 흐름 {#dataflows}

>[!IMPORTANT]
>
>새 데이터 세트를 추가할 때 기존 데이터 세트를 사용하지 않고 플로우를 만드는 것이 좋습니다.

[데이터 흐름 개요](https://experienceleague.adobe.com/docs/experience-platform/dataflows/home.html){target="_blank"}

**데이터 흐름을 만드는 절차:**

1. 소스를 선택합니다.
1. 기존 계정을 선택하거나 계정을 만듭니다.
1. 소스에서 가져올 사용 가능한 유형 목록에서 데이터 유형을 선택합니다.
1. 기존 데이터 세트를 선택하거나 데이터 세트를 만듭니다.
1. 소스의 필드를 스키마에 매핑합니다.

   >[!NOTE]
   >
   >* 하나의 스키마 유형을 다른 동일한 스키마 유형에 매핑하면 자동으로 수행됩니다.
   >* 시스템의 다른 흐름에서 매핑을 가져올 수도 있습니다.
   >* 하나의 소스 필드를 여러 대상 필드에 매핑할 수 있지만 반대는 수행할 수 없습니다.
   >* 계산된 필드를 만들 수 있습니다([데이터 준비 매핑 함수](https://experienceleague.adobe.com/docs/experience-platform/data-prep/functions.html){target="_blank"}).

   >[!CAUTION]
   >
   >* 데이터 흐름을 편집할 수 있지만 매핑이 변경될 때 데이터가 채워지지 않습니다.
   >* 필수 필드가 NULL이면 전체 흐름이 거부됩니다.

   >[!NOTE]
   >
   >[Marketo Measure Ultimate Data Integrity 요구 사항](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}

1. 데이터 로드 케이던스를 설정합니다.
1. 검토 및 완료.
1. 데이터 흐름 상태에 대한 측정값 UI 설정의 &quot;계정 상태&quot; 페이지를 확인하십시오.

**모니터링:**

소스 > 데이터 흐름 페이지에서 데이터 흐름의 상태를 확인

* 데이터 세트의 활동 세부 정보를 보려면 데이터 세트를 클릭하기만 하면 됩니다.
* 데이터 흐름 오류를 보려면 데이터 흐름을 선택하고 데이터 흐름 실행을 선택한 다음 &quot;오류 진단 미리 보기&quot;를 클릭합니다.

## 데이터 검사 {#data-inspection}

옵션 1: UI에서 직접 쿼리를 실행하려면 데이터 관리 아래의 쿼리 탭에 액세스합니다.

![](assets/marketo-measure-ultimate-implementation-guide-4.png)

옵션 2: [PSQL 다운로드 및 사용](https://experienceleague.adobe.com/docs/experience-platform/query/clients/psql.html){target="_blank"} (더 빠르고 안정적).

## Marketo Measure에 대한 데이터 세트 활성화 {#activate-dataset-for-marketo-measure}

시작하기 전에 측정 UI 설정의 &quot;Experience Platform > 샌드박스 매핑&quot; 섹션으로 이동하여 샌드박스를 매핑합니다.

>[!CAUTION]
>
>선택한 후에는 변경할 수 없습니다.

1. AEP에서 &quot;대상 > Marketo Measure 페이지&quot;로 이동하여 데이터 세트를 내보냅니다.
1. 대상을 구성합니다.
1. 데이터 세트를 활성화합니다.
1. 데이터 흐름 상태에 대한 측정값 UI 설정의 &quot;계정 상태&quot; 페이지를 확인하십시오.

>[!NOTE]
>
>* 지정된 소스의 지정된 엔티티(예: 계정)에 대한 데이터는 하나의 데이터 세트에만 들어갈 수 있습니다. 각 데이터 세트는 하나의 데이터 흐름에만 포함될 수 있습니다. 위반은 런타임에 데이터 흐름을 중지합니다.
>* AEP에서 전체 대상을 삭제하여 측정에서 데이터를 삭제합니다. 비활성화하면 새 데이터 내보내기가 중지되고 이전 데이터가 유지됩니다.
>* 측정값 구성은 대부분 동일하게 보이지만 스테이지 매핑과 같은 일부 부분은 다르게 표시됩니다.
>* 새 데이터 흐름이 플로우 실행을 생성하는 데 몇 시간이 소요되며, 그런 다음 규칙적인 시간 간격으로 발생합니다.

측정에서 기본 통화는 &quot;통화&quot; 섹션에 설정되어야 합니다.

* 다중 통화를 사용하는 경우 AEP에서 통화 전환율 스키마를 채워야 전환용으로 읽고 사용할 수 있습니다.

**스테이지 매핑:**

사용자 데이터에서 단계를 자동으로 가져오지 않으므로 모든 단계를 수동으로 매핑해야 합니다.

* 사용자는 서로 다른 소스의 단계를 매핑할 수 있습니다.

![](assets/marketo-measure-ultimate-implementation-guide-5.png)

단계를 매핑하지 않으면 데이터가 이동할 곳이 없기 때문에 시스템이 작동하지 않습니다.

Marketo Measure Ultimate 고객이고 기본 대시보드 개체를 연락처로 설정한 경우 잠재 고객용 아래 두 필드를 사용하지 마십시오([여기에서 자세히 알아보기](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**캠페인 멤버 규칙:**

데이터 세트를 선택하고 각각에 대한 규칙을 설정합니다.

**경험 이벤트 규칙:**

데이터 세트를 선택하고 활동 유형을 선택합니다.

* 사용자 지정 활동은 아직 지원되지 않습니다.
* 고객에게 사용 가능한 옵션에 맞지 않는 활동이 있는 경우 이를 &quot;즐거운 순간&quot;으로 분류하고 사용자 정의 필드를 사용하여 구분하는 것이 좋습니다.

**오프라인 채널:**

* 데이터 세트별 채널 매핑 규칙은 수행하지 않으므로 이는 전역적입니다.
* 결국 CRM 캠페인 유형과 채널을 모두 일치시켜야 하지만, 현재로서는 해결 방법으로 채널 이름을 두 필드에 모두 매핑할 수 있습니다.
* **채널 규칙: 채워진 데이터에는 단계 전환 데이터가 포함되지 않습니다.**

접점 및 세그먼트 설정은 동일하게 유지됩니다.
