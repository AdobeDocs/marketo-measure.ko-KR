---
description: 에 대한 우수 사례 [!DNL Marketo Measure] CRM 패키지 - [!DNL Marketo Measure] - 제품 설명서
title: 에 대한 우수 사례 [!DNL Marketo Measure] CRM 패키지
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 에 대한 우수 사례 [!DNL Marketo Measure] CRM 패키지 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

## 개요 {#overview}

[!DNL Marketo Measure] 은 두 가지 모두와 통합됩니다. [!DNL Salesforce] 및 [!DNL Microsoft Dynamics], 이 문서는 [!DNL Marketo Measure] 용으로 설계된 CRM 패키지에 대한 우수 사례 [!DNL Salesforce].

구현 중에 다음 두 패키지가 [!DNL Salesforce] 인스턴스.

기본 패키지: 사용자 지정 개체 및 필드를 포함하는 기본 패키지입니다. 모든 사용자를 위해 프로덕션 내에 설치하는 것이 좋습니다.
Dashboard Extension Package: 3개의 사전 설치된 대시보드가 포함된 Dashboard Extension 패키지입니다. 모든 사용자를 위해 프로덕션 내에 설치하는 것이 좋습니다. 이는 선택 사항이지만 고객이 설치하기를 권장합니다.

이 패키지를 통해 [!DNL Marketo Measure] 사용자가 자신의 전체 터치포인트 데이터에 쉽게 액세스 [!DNL Salesforce] 인스턴스. 이러한 패키지가 올바르게 구성되어 있는지 확인하는 것은 페이지 레이아웃, 권한 집합, 보고서 및 대시보드가 사용자에게 표시되는지 확인하는 데 중요합니다. [!DNL Marketo Measure] 예상대로 사용자를 지정합니다.

## 우수 사례 {#best-practice}

의 구현 및 관리와 관련된 경우 [!DNL Marketo Measure] [!DNL Salesforce] 패키지화, 다음 모범 사례를 염두에 두십시오.

* 필요한 모든 팀원이 [!DNL Marketo Measure] 보고서 폴더 1-3개가 있어야 합니다. [!DNL Marketo Measure] 폴더(아래에 설명되어 있음). 액세스 권한을 열려면 패키지를 설치한 사람이 보고서 폴더를 적절한 사용자 또는 역할과 공유해야 합니다.
   * **구매자 접점 보고서** - 모든 사용자가 사용 가능
   * **[!DNL Marketo Measure]계정 기반 마케팅 보고서** - 보고서는 계층 2 이상의 고객에게만 작성됩니다.
   * **구매자 터치포인트 대시보드** - 이 패키지는 선택 사항이지만 모든 사용자가 사용할 수 있습니다.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

CRM 패키지 설정은 초기 구현 중에 포함되지만 1년에 한 번 CRM 패키지 설정을 검토하는 것이 좋습니다. 이 검토를 통해 모든 페이지 레이아웃이 올바르게 설정되고 적절한 모든 팀원이 다음에 액세스할 수 있는지 확인합니다. [!DNL Marketo Measure] 보고서 및 대시보드.

리뷰를 트리거할 수있는 다른 이유 ...

* 새 팀원 추가
* 내 업데이트 [!DNL Salesforce] 페이지 레이아웃
* 마이그레이션 대상 [!DNL Salesforce] Classic에서 Lighting으로
* 로 업그레이드 [!DNL Marketo Measure] 약정
* 에 최신 버전의 구매자 접점 패키지가 설치되어 있는지 확인합니다. [!DNL Salesforce]

>[!NOTE]
>
>Marketo Measure에서 Salesforce로 데이터 내보내기를 비활성화하면 기존 데이터가 제거되지 않습니다. 제거하려면 의 단계를 따르십시오. [이 Salesforce 도움말 문서](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [구매자 접점 패키지 업데이트](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 사용 권한 집합](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [보고서 및 대시보드 폴더 공유](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [Marketo Measure을 Salesforce에 연결](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
