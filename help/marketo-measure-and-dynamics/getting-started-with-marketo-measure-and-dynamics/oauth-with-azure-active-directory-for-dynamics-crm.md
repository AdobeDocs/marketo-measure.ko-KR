---
unique-page-id: 37357059
description: OAuth와 함께 [!DNL Azure Active Directory] Dynamics CRM용 - [!DNL Marketo Measure] - 제품 설명서
title: OAuth와 함께 [!DNL Azure Active Directory] Dynamics CRM용
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# OAuth와 함께 [!DNL Azure Active Directory] Dynamics CRM용 {#oauth-with-azure-active-directory-for-dynamics-crm}

## 영향을 받는 사람 {#who-s-affected}

이 설정은 새로운 것입니다 [!DNL Marketo Measure] Dynamics CRM을 사용하여 고객 [!DNL Azure Active Directory] (AAD) 계정 또는 기존 사용자 이름과 암호 로그인에서 로 마이그레이션하려는 고객용 [!DNL Azure Active Directory] OAuth 포함.

>[!NOTE]
>
>이 두 시나리오 모두에 대해 AAD가 여기에서 Dynamics 인스턴스를 쉽게 연결하도록 설정되어 있습니다 [!DNL Marketo Measure] 를 데이터 공급자로 사용하십시오.

## 새 애플리케이션 설정 {#set-up-new-application}

1. 사용자 [Azure 포털](https://portal.azure.com/#home).

1. 페이지의 오른쪽 위 모서리에서 계정을 클릭한 다음, 디렉터리 전환 탐색을 클릭한 다음 적절한 테넌트를 선택하여 Azure AD 테넌트를 선택합니다(계정 아래에 Azure AD 테넌트가 하나만 있거나 해당 Azure AD 테넌트를 이미 선택한 경우 이 단계를 건너뜁니다).

   ![](assets/setup-2.png)

1. &quot; 검색[!DNL Azure Active Directory]&quot; 검색 창에서 열 이름을 클릭합니다.

   ![](assets/setup-3.png)

1. 클릭 **[!UICONTROL App Registrations]** 왼쪽 메뉴에 있습니다.

   ![](assets/setup-4.png)

1. 클릭 **[!UICONTROL New Registration]** 바로 위에요

   ![](assets/setup-5.png)

1. 화면의 지침에 따라 새 응용 프로그램을 만듭니다. 웹 애플리케이션이든 공용 클라이언트(모바일 및 데스크탑) 애플리케이션이든 상관없지만, 웹 애플리케이션이나 공용 클라이언트 애플리케이션에 대한 특정 예를 보려면 [quickstart](https://docs.microsoft.com/en-us/azure/active-directory/develop/v1-overview).\
   a. Name은 응용 프로그램 이름이며 최종 사용자에게 응용 프로그램을 설명합니다.\
   나. 지원되는 계정 유형에서 조직 디렉터리 및 개인 Microsoft 계정의 계정 을 선택합니다.\
   c. 리디렉션 URI를 제공합니다. 웹 애플리케이션의 경우 사용자가 로그인할 수 있는 앱의 기본 URL입니다. For example, `http://localhost:12345`. 공개 클라이언트(모바일 및 데스크톱)의 경우 Azure AD는 이 이벤트를 사용하여 토큰 응답을 반환합니다. 애플리케이션에 해당하는 값을 입력합니다. For example, `http://MyFirstAADApp`.

1. 등록을 완료하면 Azure AD에서 응용 프로그램에 고유한 클라이언트 식별자(응용 프로그램 ID)를 할당합니다. 이 값은 다음 섹션에 있어야 하므로 애플리케이션 페이지에서 복사합니다.

1. Azure 포털에서 응용 프로그램을 찾으려면 **[!UICONTROL App Registrations]**&#x200B;를 클릭한 다음 **[!UICONTROL All Applications]**. 새로 만든 응용 프로그램을 엽니다

1. 클릭 **[!UICONTROL Authentication]** 왼쪽 메뉴에 있습니다.

   ![](assets/setup-9.png)

1. 추가 [!DNL Marketo Measure] 리디렉션 URL: `https://apps.bizible.com/OAuth2` 및 `https://apps.bizible.com/OAuth2?identityOnly=true` 리디렉션 URL 목록에 추가합니다.

   ![](assets/setup-10.png)

1. API 권한 탭으로 이동하여 애플리케이션에 올바른 권한이 할당되었는지 확인합니다.

   ![](assets/setup-10a.png)

1. 여기에서 &quot;&quot;을 입력합니다.[!UICONTROL enterprise]&quot; 검색 상자에서 를 클릭하고 **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. 애플리케이션 목록에서 새 애플리케이션을 찾아서 엽니다.

1. 권한 탭에서 **[!UICONTROL Grant Admin Consent for (instance name)]**.

   ![](assets/setup-13a.png)

1. 클릭 **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. &quot;[!UICONTROL Users and Groups]&quot; 탭에서 유효한 &quot;사용자 및 그룹&quot;이 응용 프로그램에 할당되어 있는지 확인합니다.

   ![](assets/setup-14.png)

## 응용 프로그램 사용자 생성 {#creating-an-application-user}

애플리케이션 등록이 완료되면 애플리케이션 사용자를 만들 수 있습니다.

1. 일반 데이터 서비스 환경(`https://[org].crm.dynamics.com`).

1. 다음으로 이동 **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. 선택 **[!UICONTROL Application Users]** 를 클릭합니다.

1. 선택 **[!UICONTROL + New]**.

1. 애플리케이션 사용자 양식에 필요한 정보를 입력합니다.

   >[!NOTE]
   >
   >* 사용자 이름 정보는 [!DNL Azure Active Directory].
   >
   >* 응용 프로그램 ID 필드에서 Azure AD에서 이전에 등록한 앱의 응용 프로그램 ID를 입력합니다.


1. 설정이 올바른 경우 을 선택한 후 **[!UICONTROL Save]**, **[!UICONTROL Application ID URI]** 및 **[!UICONTROL Azure AD Object Id]** 필드는 올바른 값으로 자동으로 채워집니다.

1. 사용자 양식을 종료하기 전에 **[!UICONTROL Manage Roles]** 응용 프로그램 사용자가 원하는 조직 데이터에 액세스할 수 있도록 보안 역할을 이 응용 프로그램 사용자에게 할당합니다.

## OAuth를 통해 Dynamics 인스턴스 연결 {#connecting-your-dynamics-instance-via-oAuth}

1. 처음으로 Dynamics 연결을 설정할 때 의 &quot;데이터 공급자로 CRM&quot; 섹션 1-5단계를 따르십시오 [이 문서](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. OAuth 자격 증명을 묻는 메시지가 표시되면 위의 섹션에 설정된 클라이언트 ID, 클라이언트 암호 및 응용 프로그램 ID URI를 입력합니다.

a. 클라이언트 ID 는 위의 섹션에서 #7 단계의 ID입니다. 적지 않은 경우 애플리케이션 ID가 앱 등록의 설정에 표시됩니다.

나. 클라이언트 암호는 Azure 포털에서 인증서 및 비밀에서 응용 프로그램의 응용 프로그램 암호입니다.

![](assets/creating-2e.png)

c. Application ID URI는 Target 웹 API(보안 리소스)의 URL입니다. 앱 ID URL을 찾으려면 Azure 포털에서 [!DNL Azure Active Directory]응용 프로그램 등록을 클릭하고 응용 프로그램의 설정 페이지를 연 다음 속성을 클릭합니다. 외부 리소스일 수도 있습니다. `https://graph.microsoft.com`. 일반적으로 Dynamics 인스턴스의 URL입니다.

1. 을 클릭한 후 **[!UICONTROL Submit]**&#x200B;로 로그인하라는 메시지가 표시됩니다 [!DNL Azure Active Directory]. 인증이 성공하면 Dynamics 계정이 내의 데이터 공급자로 연결됩니다 [!DNL Marketo Measure].

## Dynamics 계정 다시 인증 {#re-authenticating-your-dynamics-account}

1. 에 있을 때 [!DNL Marketo Measure] 애플리케이션, **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**.

1. Dynamics 연결 옆에 있는 CRM 섹션에서 키 아이콘을 클릭합니다.

1. 키를 클릭하면 팝업 창이 표시되고 등록 흐름과 마찬가지로 클라이언트 ID, 클라이언트 암호 및 응용 프로그램 ID URI를 입력하라는 메시지가 표시됩니다.

   ![](assets/re-authenticating-3.png)

1. 을 클릭한 후 **[!UICONTROL Submit]**&#x200B;로 로그인하라는 메시지가 표시됩니다 [!DNL Azure Active Directory]. 인증이 성공하면 Dynamics 계정이 내에서 다시 인증됩니다 [!DNL Marketo Measure].
