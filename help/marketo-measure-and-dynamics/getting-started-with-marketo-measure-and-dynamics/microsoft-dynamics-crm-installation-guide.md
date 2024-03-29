---
unique-page-id: 18874763
description: "[!DNL Microsoft Dynamics] CRM 설치 안내서 - Marketo Measure - 제품 설명서"
title: "[!DNL Microsoft Dynamics] CRM 설치 안내서"
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM 설치 안내서 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

## 지원되는 버전 {#supported-versions}

[!DNL Marketo Measure] 는 다음을 지원합니다 [!DNL Microsoft Dynamics CRM] 버전:

* [!DNL Microsoft Dynamics 2016] (온라인 및 온-프레미스)
* [!DNL Microsoft Dynamics 365] (온라인 및 온-프레미스)

연결 및 인증의 경우 [!DNL Marketo Measure] 는 다음 ADFS(Active Directory Federated Services) 버전을 지원합니다.

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 관리 솔루션 설치 {#install-the-managed-solution}

[다운로드 및 설치](assets/marketo-measure-dynamics-extension.zip) dynamics CRM 내의 zip 파일입니다.

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** (버튼) > **[!UICONTROL Choose File]**.

![](assets/1.png)

>[!NOTE]
>
>다음 두 스크린샷은 솔루션 업그레이드 중에 촬영되었기 때문에 사용자 스크린샷과 약간 다를 수 있습니다.

![](assets/2.png)

![](assets/3.png)

## 만들기 [!DNL Marketo Measure] 사용자 {#creating-a-marketo-measure-user}

CRM에 있는 다른 사용자와 관련된 문제를 방지하기 위해 데이터를 내보내고 가져올 Dynamics 내에서 &quot;애플리케이션 사용자&quot;로 전용 Marketo Measure 사용자를 만드는 것이 좋습니다. 사용자 이름 및 암호와 끝점 URL을 기록해 두십시오. [!DNL Marketo Measure] 계정입니다.

## 보안 역할 {#security-roles}

조직에서 Dynamics 보안 역할을 사용하는 경우 연결된 사용자 또는 전용 [!DNL Marketo Measure] 필요한 엔티티에 대한 충분한 읽기/쓰기 권한이 사용자에게 있습니다.

보안 역할은 다음과 같습니다. **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**.

대상 [!DNL Marketo Measure] 사용자 지정 엔티티, 모든 엔티티에 대한 모든 권한이 필요합니다.

>[!NOTE]
>
>영업 기회를 종료하는 사용자도 전체 권한이 필요합니다.

![](assets/4.png)

Dynamics 표준 엔티티의 경우 다음을 참조하십시오. [!DNL Marketo Measure] Dynamics 스키마 문서. 높은 수준에서 [!DNL Marketo Measure] 는 특정 엔터티에서 읽기를 수행하여 적절한 데이터를 수집하고 관리 솔루션과 함께 설치된 사용자 지정 필드에 씁니다. 표준 레코드는 생성되지 않으며 표준 필드는 업데이트되지 않습니다.

## 페이지 레이아웃에 터치포인트 포함: {#include-touchpoints-on-page-layouts}

1. 각 엔티티에 대해 양식 편집기로 이동합니다. 다음 중 하나에서 찾을 수 있습니다. **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**. 또는 레코드를 보는 동안 설정에서 찾을 수 있습니다.

   * 구성할 엔티티: Account, Opportunity, Contact, Lead 및 Campaign

   * 캠페인을 구성하려면 다음에서 &quot;캠페인 동기화&quot; 옵션을 켜야 합니다. **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**.

   ![](assets/5.png)

1. 페이지 레이아웃: 먼저 &quot;[!UICONTROL One Column]&quot;터치포인트를 라이브로 만들려는 섹션의 타일을 지정합니다. 이 새 열에서 Account, Opportunity, Contact 및 Lead 엔티티 내의 각 양식에 추가된 하위 그리드가 필요합니다.

   ![](assets/6.png)

   ![](assets/7.png)

1. 서브그리드에서 렌더링해야 하는 개체(구매자 속성 접점 또는 구매자 접점)를 선택합니다. 이는 개체 관계에 따라 다릅니다. 필요한 경우 [편집] 단추를 눌러 표시되는 열을 변경합니다. 기본 레이아웃은 관리되는 솔루션에 의해 설정됩니다.

   구매자 속성 접점 하위 그리드 - 계정, 기회 및 연락처\
   구매자 접점 하위 그리드 - 리드 및 연락처

   ![](assets/8.png)

1. 양식 업데이트가 완료되면 변경 사항을 게시하고 저장합니다.

## 스키마 관련 고려 사항 {#schema-related-considerations}

**매출**

[!DNL Marketo Measure] 는 기본적으로 표준 실제 수익 필드를 가리킵니다. 이 옵션을 사용하지 않는 경우 맞춤형 워크플로우가 필요하므로 매출에 대해 솔루션 엔지니어나 성공 관리자에게 보고하는 방법을 설명합니다.

**종료 날짜**

[!DNL Marketo Measure] 는 즉시 사용할 수 있도록 실제 종료 날짜 필드를 지정합니다. 이 필드를 사용하지 않거나 예상 종료 날짜 필드도 사용하는 경우 솔루션 엔지니어나 성공 관리자에게 프로세스를 설명하십시오. 두 필드를 모두 처리하려면 사용자 지정 워크플로우가 필요할 수 있습니다.

## 연결 및 데이터 공급자 구성 {#configuring-your-connections-and-data-providers}

에 로그인한 후 [!DNL Marketo Measure] Adobe Admin Console에서 애플리케이션으로 설정되었으며, 다음 단계는 다양한 데이터 연결을 설정하는 것입니다.

**데이터 공급자로서의 CRM**

1. 내 [!DNL Marketo Measure] account, 클릭 **[!UICONTROL My Account]** 드롭다운 및 선택 **[!UICONTROL Settings]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 아래 [!UICONTROL Integrations] 왼쪽 탐색 메뉴에서 **[!UICONTROL Connections]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 다음을 클릭합니다. **[!UICONTROL Set Up New CRM Connection]** 단추를 클릭합니다.

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 다음 [!UICONTROL Microsoft Dynamics CRM]를 클릭하고 **[!UICONTROL Connect]** 단추를 클릭합니다.

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 선택 [!UICONTROL Credentials] 또는 [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >OAuth에 대한 자세한 내용은 [이 문서](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). 프로세스에 대해 궁금한 사항은 다음 주소로 문의하십시오. [!DNL Marketo Measure] 계정 담당자.

1. 이 예에서는 자격 증명을 선택했습니다. 자격 증명을 입력하고 **[!UICONTROL Next]**.

연결 후 CRM/맵 연결 목록에 Dynamics 연결의 세부 정보가 표시됩니다.

**광고 계정 연결**

광고 계정을 [!DNL Marketo Measure], 다음 사이트를 방문하여 시작 [!UICONTROL Connections] 내의 탭 [!DNL Marketo Measure] 응용 프로그램.

1. 위에서 1 및 2단계를 수행합니다 _데이터 공급자로서의 CRM_ 섹션.

1. 다음을 클릭합니다. **[!UICONTROL Set up New CRM Connection]** 단추를 클릭합니다.

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 원하는 플랫폼을 선택합니다.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

대상 [!DNL Marketo Measure] 웹 활동을 추적하려면 여러 단계를 설정해야 합니다.

1. 다음을 클릭합니다. **[!UICONTROL My Account]** 드롭다운 및 선택 **[!UICONTROL Account Configuration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 전화 번호를 입력합니다. 웹 사이트의 경우 다음에 사용되는 주 루트 도메인을 입력합니다. [!DNL Marketo Measure] 웹 사이트에서 추적. 클릭 **[!UICONTROL Save]** 완료 시.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >여러 루트 도메인을 추가하려면 [!DNL Marketo Measure] 계정 담당자.

1. 다음 [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) 전체 사이트 및 랜딩 페이지에 배치해야 합니다. 랜딩 페이지의 헤드 내에서 스크립트를 하드코딩하거나 다음과 같은 Tag Management 시스템을 통해 추가하는 것이 좋습니다. [Google 태그 관리자](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >기본적으로, [!DNL Marketo Measure] 작업이 데이터를 CRM으로 보낼 때마다 API 크레딧당 200개의 레코드를 내보냅니다. 대부분의 고객은 이렇게 함으로써 사용한 API 크레딧 간의 최적의 균형을 확보할 수 있습니다. [!DNL Marketo Measure] 및 CRM의 CPU 리소스 요구 사항입니다. 그러나 워크플로우 및 트리거와 같이 복잡한 CRM 구성을 사용하는 고객의 경우 배치 크기를 줄이면 CRM 성능을 향상시키는 데 도움이 될 수 있습니다. 이를 위해, [!DNL Marketo Measure] 고객이 CRM 내보내기 일괄 처리 크기를 구성할 수 있습니다. 이 설정은 의 설정 > CRM > 일반 페이지에서 사용할 수 있습니다 [!DNL Marketo Measure] 웹 애플리케이션과 고객은 200(기본값), 100, 50 또는 25의 배치 크기 중에서 선택할 수 있습니다.
   >
   >이 설정을 수정할 때는 배치 크기가 작을수록 CRM에서 더 많은 API 크레딧을 사용한다는 점을 유의하십시오. CRM에서 CPU 시간 초과 또는 높은 CPU 로드가 발생하는 경우에만 배치 크기를 줄이는 것이 좋습니다.

   >[!NOTE]
   >
   >Marketo Measure에서 Dynamics로 데이터 내보내기를 비활성화하면 기존 데이터가 제거되지 않습니다. 기존 데이터를 제거하는 데 도움이 필요하면 Dynamics 지원에 문의하십시오.

   >[!MORELIKETHIS]
   >
   >[오류 알림](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
