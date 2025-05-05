---
unique-page-id: 37357059
description: Dynamics CRM용  [!DNL Azure Active Directory] 이(가) 있는 OAuth - [!DNL Marketo Measure]
title: Dynamics CRM용  [!DNL Azure Active Directory] 이(가) 있는 OAuth
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# Dynamics CRM용 [!DNL Azure Active Directory]이(가) 있는 OAuth {#oauth-with-azure-active-directory-for-dynamics-crm}

## 영향을 받는 사용자 {#who-s-affected}

이 설정은 AAD([!DNL Azure Active Directory]) 계정으로 Dynamics CRM을 사용하는 새 [!DNL Marketo Measure] 고객 또는 기존 사용자 이름과 암호에서 OAuth를 사용하여 [!DNL Azure Active Directory] (으)로 마이그레이션하려는 고객을 위한 것입니다.

>[!NOTE]
>
>이러한 시나리오 모두에 대해 [!DNL Marketo Measure]에서 데이터 공급자로서 Dynamics 인스턴스에 쉽게 연결할 수 있도록 AAD가 여기에 설정되어 있습니다.

## 새 애플리케이션 설정 {#set-up-new-application}

1. [Azure 포털](https://portal.azure.com/#home)에 로그인하세요.

1. 페이지 오른쪽 상단에서 계정을 클릭한 다음 디렉터리 전환 탐색을 클릭하고 적절한 테넌트를 선택하여 Azure AD 테넌트를 선택합니다. 계정에 Azure AD 테넌트가 하나만 있거나 이미 적절한 Azure AD 테넌트를 선택한 경우 이 단계를 건너뜁니다.

   ![](assets/setup-2.png)

1. 검색 창에서 &quot;[!DNL Azure Active Directory]&quot;을(를) 검색하고 열 이름을 클릭합니다.

   ![](assets/setup-3.png)

1. 왼쪽 메뉴에서 **[!UICONTROL App Registrations]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-4.png)

1. 맨 위에 있는 **[!UICONTROL New Registration]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-5.png)

1. 프롬프트에 따라 응용 프로그램을 만듭니다. 웹 응용 프로그램이든 공용 클라이언트(모바일 및 데스크톱) 응용 프로그램이든 상관없지만 웹 응용 프로그램이나 공용 클라이언트 응용 프로그램에 대한 특정 예제를 보려면 [빠른 시작](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview)을 확인하십시오.\
   a. 이름은 애플리케이션 이름이며 최종 사용자에게 애플리케이션에 대해 설명합니다.\
   b. 지원되는 계정 유형에서 조직 디렉터리와 개인 Microsoft 계정의 계정을 선택합니다.\
   c. 리디렉션 URI를 제공합니다. 웹 애플리케이션의 경우 사용자가 로그인할 수 있는 앱의 기본 URL입니다. 예: `http://localhost:12345`. 공용 클라이언트(모바일 및 데스크톱)의 경우 Azure AD는 토큰 응답을 반환하는 데 이 토큰을 사용합니다. 응용 프로그램에 해당하는 값을 입력합니다. 예: `http://MyFirstAADApp`.

1. 등록을 완료하면 Azure AD는 응용 프로그램에 고유한 클라이언트 식별자(응용 프로그램 ID)를 할당합니다. 다음 섹션에서 이 값이 필요하므로 애플리케이션 페이지에서 이 값을 복사합니다.

1. Azure 포털에서 응용 프로그램을 찾으려면 **[!UICONTROL App Registrations]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL All Applications]**&#x200B;을(를) 클릭합니다. 새로 만든 응용 프로그램을 엽니다.

1. 왼쪽 메뉴에서 **[!UICONTROL Authentication]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-9.png)

1. [!DNL Marketo Measure] 리디렉션 URL: `https://apps.bizible.com/OAuth2` 및 `https://apps.bizible.com/OAuth2?identityOnly=true`을(를) 리디렉션 URL 목록에 추가합니다.

   ![](assets/setup-10.png)

1. API 권한 탭으로 이동하여 애플리케이션에 올바른 권한이 할당되었는지 확인합니다.

   ![](assets/setup-10a.png)

1. 여기에서 검색 상자에 &quot;[!UICONTROL enterprise]&quot;을(를) 입력하고 **[!UICONTROL Enterprise Applications]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-11.png)

1. 다시, 응용 프로그램 목록에서 새 응용 프로그램을 찾아 엽니다.

1. 권한 탭에서 **[!UICONTROL Grant Admin Consent for (instance name)]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-13a.png)

1. **[!UICONTROL Accept]**&#x200B;을(를) 클릭합니다.

   ![](assets/setup-13b.png)

1. &quot;[!UICONTROL Users and Groups]&quot; 탭에서 올바른 &quot;사용자 및 그룹&quot;이 응용 프로그램에 할당되었는지 확인하십시오.

   ![](assets/setup-14.png)

## 응용 프로그램 사용자 생성 {#creating-an-application-user}

애플리케이션 등록이 완료되면 애플리케이션 사용자를 생성할 수 있습니다.

1. 일반 데이터 서비스 환경(`https://[org].crm.dynamics.com`)으로 이동합니다.

1. **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**(으)로 이동합니다.

1. 보기 필터에서 **[!UICONTROL Application Users]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL + New]**&#x200B;을(를) 선택합니다.

1. 응용 프로그램 사용자 양식에 필요한 정보를 입력합니다.

   >[!NOTE]
   >
   >* 사용자 이름 정보는 [!DNL Azure Active Directory]에 있는 사용자와 일치하지 않아야 합니다.
   >
   >* 응용 프로그램 ID 필드에 Azure AD에서 이전에 등록한 앱의 응용 프로그램 ID를 입력합니다.

1. 설정이 올바르면 **[!UICONTROL Save]**&#x200B;을(를) 선택하면 **[!UICONTROL Application ID URI]** 및 **[!UICONTROL Azure AD Object Id]** 필드가 올바른 값으로 자동 채워집니다.

1. 사용자 양식을 종료하기 전에 응용 프로그램 사용자가 원하는 조직 데이터에 액세스할 수 있도록 **[!UICONTROL Manage Roles]**&#x200B;을(를) 선택하고 이 응용 프로그램 사용자에게 보안 역할을 할당하십시오.

## OAuth를 통해 Dynamics 인스턴스 연결 {#connecting-your-dynamics-instance-via-oAuth}

1. Dynamics 연결을 처음 설정할 때 [이 문서](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)에서 &quot;데이터 공급자로서 CRM&quot; 섹션의 1-5단계를 따르십시오.

1. OAuth 자격 증명을 입력하라는 메시지가 표시되면 위의 섹션에 설정된 클라이언트 ID, 클라이언트 암호 및 애플리케이션 ID URI를 입력합니다.

a. Client Id는 위 섹션의 #7단계에 있는 ID입니다. 기록하지 않은 경우 앱 등록 설정에 애플리케이션 ID가 표시됩니다.

b. 클라이언트 암호는 Azure 포털에서 인증서 및 암호로 응용 프로그램에 대해 만든 응용 프로그램 암호입니다.

![](assets/creating-2e.png)

c. 애플리케이션 ID URI는 대상 웹 API(보안 리소스)의 URL입니다. 앱 ID URL을 찾으려면 Azure 포털에서 [!DNL Azure Active Directory]을(를) 클릭하고 응용 프로그램 등록을 클릭한 다음 응용 프로그램의 설정 페이지를 열고 속성을 클릭합니다. `https://graph.microsoft.com`과(와) 같은 외부 리소스일 수도 있습니다. 일반적으로 Dynamics 인스턴스의 URL입니다.

1. **[!UICONTROL Submit]**&#x200B;을(를) 클릭하면 [!DNL Azure Active Directory] (으)로 로그인하라는 메시지가 표시됩니다. 인증에 성공하면 Dynamics 계정이 [!DNL Marketo Measure] 내에서 데이터 공급자로 연결됩니다.

## Dynamics 계정 재인증 {#re-authenticating-your-dynamics-account}

1. [!DNL Marketo Measure] 응용 프로그램에 있는 경우 **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**(으)로 이동합니다.

1. Dynamics 연결 옆에 있는 CRM 섹션에서 키 아이콘을 클릭합니다.

1. 키를 클릭하면 팝업이 나타나고 등록 흐름과 유사하게 클라이언트 ID, 클라이언트 암호 및 애플리케이션 ID URI를 입력하라는 메시지가 표시됩니다.

   ![](assets/re-authenticating-3.png)

1. **[!UICONTROL Submit]**&#x200B;을(를) 클릭하면 [!DNL Azure Active Directory] (으)로 로그인하라는 메시지가 표시됩니다. 인증에 성공하면 [!DNL Marketo Measure] 내에 Dynamics 계정이 다시 인증됩니다.
