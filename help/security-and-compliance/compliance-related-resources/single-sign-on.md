---
unique-page-id: 18874761
description: 단일 사인온 - [!DNL Marketo Measure]
title: 단일 사인온
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 0%

---

# 단일 사인온 {#single-sign-on}

SSO(Single Sign-On)를 위한 SAML(보안 설정 마크업 언어)을 사용하면 사용자가 다음에 로그인할 때 회사의 ID 공급자를 통해 인증할 수 있습니다. [!DNL Marketo Measure] 앱. SSO를 통해 사용자는 별도의 앱을 인증할 필요 없이 한 번만 인증할 수 있습니다. SAML은 모든 사용자가 [!DNL Salesforce] 또는 [!DNL Google] 조직 내의 계정입니다. 크기를 조정하려면 [!DNL Marketo Measure] 는 회사 id 공급자를 지원할 수 있는 SAML 솔루션을 개발했습니다.

>[!CAUTION]
>
>이 문서에서는 SSO(단일 인증) 및 고급 CRM 사용자 관리에 대해 간략히 설명합니다. 계정이 프로비저닝된 경우 **2020/9/10 이후**, SSO 및 Identity Management이 다음 내에 설정되므로 이 문서를 무시하십시오. [Adobe Admin Console for your [!DNL Marketo Measure] 통합](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>회사에서 다른 ID 공급자(예: Ping ID, Okta)를 사용할 수 있습니다. 다음 설정 지침 및 UI에 사용되는 용어가 ID 공급자에서 사용하는 용어와 직접 일치하지 않을 수 있습니다.

## 요구 사항 {#requirements}

* 에서 AccountAdmin 권한이 있는 사용자 [!DNL Marketo Measure] 앱
* 고객의 ID 공급자에 대한 관리 액세스 권한이 있는 사용자

## 시작하기 {#getting-started}

시작하려면 의 설정 > 보안 > 인증 페이지로 이동합니다. [!DNL Marketo Measure] 응용 프로그램. 그런 다음 로그인 유형을 사용자 정의 SSO로 전환하여 구성 옵션을 확인합니다. 변경 사항은 인증을 테스트하고 **[!UICONTROL Save]** 페이지 하단에 있는 단추입니다.

![](assets/single-sign-on-1.png)

## 프로세스 {#process}

[!DNL Marketo Measure] SSO(Single Sign-On)를 사용하려면 인증 설정을 일련의 단계로 구성해야 인증 설정이 잠기지 않을 수 있습니다. [!DNL Marketo Measure] 계정입니다.

다음을 설정합니다. [!DNL Marketo Measure] ID 공급자의 응용 프로그램입니다. 연습은 아래 나열된 외부 설명서를 참조하십시오.

    a. 단일 사인온 URL, 수신자 URL 또는 대상 URL, SAML Assertion ACS(고객 서비스) URL을 입력하라는 메시지가 표시되면 [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)을 사용합니다.
    
    b. 대상 제한 URL 또는 애플리케이션 정의 고유 식별자를 묻는 메시지가 표시되면 [https://BizibleLPM](https://biziblelpm/)을 사용합니다.

에서 사용자 정의 SSO로 전환 [!DNL Marketo Measure] 애플리케이션

    a. 계정에 대해 청구 그룹을 활성화하면 다음으로 이동할 수 있습니다. [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b. 기본적으로 로그인 유형은 &quot;CRM 사용자&quot;로 설정됩니다.
    
    c. 로그인 유형을 &quot;사용자 정의 SSO&quot;로 전환하여 구성 프로세스를 시작합니다.

ID 공급자 구성에 대한 연결 설정을 입력합니다

    a. ID 공급자가 필수 구성 필드를 가져올 IdP 메타데이터 .xml 문서를 제공할 수 있습니다. .xml 문서의 내용을 로드하거나 ID 공급자 구성 프로세스에서 얻은 출력에서 아래 세 개의 필드를 채웁니다. **둘 다 완료할 필요는 없습니다.**
    
    i. IdP URL: [!DNL Marketo Measure] 에 사용자를 인증하려면 을(를) 가리켜야 합니다. [!DNL Marketo Measure] 응용 프로그램. 경우에 따라 &quot;리디렉션 URL&quot;이라고도 합니다.
    아.. IdP 발급자: ID 공급자의 고유 식별자입니다. 경우에 따라 &quot;외부 키&quot;라고도 합니다.
    iii. IdP 인증서: 를 허용하는 공개 키 [!DNL Marketo Measure] 모든 ID 공급자 응답의 서명을 확인하고 유효성을 검사합니다.

사용자의 토큰 만료를 분 단위로 설정합니다.

    a. [!DNL Marketo Measure] 은 1분에서 1440분까지의 정수를 허용합니다. 사용자의 세션 시간이 초과되면 새 페이지로 이동하면 로그오프됩니다.

사용자 속성 설정을 설정하여 해당 이름, 성 및 이메일 주소에 매핑합니다.

    a. SAML 속성을 입력하여 [!DNL Marketo Measure] 은(는) 전달된 정보를 통해 사용자를 인식할 수 있습니다.
    
    i. 이메일 속성: ID 공급자가 사용자의 이메일 주소에 사용하는 속성 이름을 제공합니다.
    아.. 이름 속성: ID 공급자가 사용자의 이름에 사용하는 속성 이름을 제공합니다.
    iii. 성 속성: ID 공급자가 사용자의 성에 사용하는 속성 이름을 제공합니다.
    
    b. 힌트: 지금 SAML 구성을 테스트하는 경우 이 섹션에 사용할 수 있는 이메일, 이름 및 성 속성을 구문 분석합니다.

![](assets/single-sign-on-2.png)

사용자 역할 설정을 설정하여 IdP에서 분류된 해당 역할 또는 그룹에 매핑합니다.

    a. 고객은 할당할 수 있습니다 [!DNL Marketo Measure] id 공급자에 정의된 그룹을 기반으로 하는 사용자 역할. SAML 속성을 입력하여 [!DNL Marketo Measure] 은(는) 사용자의 역할 및 그룹을 다음에 매핑할 수 있습니다. [!DNL Marketo Measure] 사용자 권한. 다음 역할이 유지되도록 설정하는 것이 좋습니다. [!DNL Marketo Measure] 관리자는 계정을 업데이트할 수 있는 충분한 권한이 있습니다.
    
    b. 매핑된 역할이나 그룹이 없는 경우, 기본 설정은 ID 공급자의 모든 직원에게 표준 사용자 액세스 권한이 있다는 것입니다.
    
    난... [!DNL Marketo Measure] 표준 사용자: 다음에 대한 읽기 전용 액세스 권한이 필요한 사용자에 대한 역할 또는 그룹 값(SSO 공급자)을 제공합니다. [!DNL Marketo Measure] 응용 프로그램.
    아.. [!DNL Marketo Measure] 계정 관리자 사용자: 다음에 대한 관리 액세스 권한이 필요한 사용자의 역할 또는 그룹 값(SSO 공급자)을 제공합니다. [!DNL Marketo Measure] 응용 프로그램. 즉, 역할은 계정과 관련된 구성 및 설정을 변경할 수 있는 액세스 권한이 있습니다.
    iii. IdP에 &quot;Bizible Standard User&quot; 또는 &quot;Bizible Account Admin User&quot; 속성에 입력한 값이 들어 있는 정확한 이름이 &quot;그룹&quot;인 속성이 있어야 합니다.
    
    c. 여러 역할 또는 그룹을 역할에 매핑해야 하는 경우 각 값을 쉼표로 구분하여 입력합니다.

![](assets/single-sign-on-3.png)

단일 사인온 구성 테스트

    a. 저장 을 누르기 전에 [!UICONTROL Test SAML Authentication] 단추를 클릭하여 설정이 올바르게 구성되었는지 확인합니다.
    
    b. &quot;실패&quot; 오류가 표시되면 메시지를 따라 다시 시도하십시오.

![](assets/single-sign-on-4.png)

설정을 저장하고 동료가 사용할 수 있도록 합니다. [!UICONTROL Single Sign On] 새 사용자 지정 로그인 URL과 함께.

    a. 중요: 새 인증 설정을 저장하고 나면 CRM 사용자의 로그인을 비활성화하고 사용자 지정 SSO를 활성화했으므로 새 페이지로 이동하면 세션이 종료될 수 있습니다.

![](assets/single-sign-on-5.png)

사용해 보세요!

    a. 새 사용자 지정 로그인 URL을 사용하고 [!DNL Marketo Measure] ID 공급자 자격 증명이 있는 응용 프로그램.
    
    b. 형식은 &#39;https://apps.adobe.com/business/[accountName]&#39;과 같이 표시됩니다.
    
    c. 축하합니다! 에 SSO(Single Sign-On)를 설정했습니다. [!DNL Marketo Measure] 계정 신청!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>SSO를 구성한 후에는 내에서 사용자를 더 이상 추가할 필요가 없습니다. [!DNL Marketo Measure] 응용 프로그램. 사용자 프로비저닝은 ID 공급자 내에서 직접 처리해야 합니다.

## CRM 사용자(고급 설정) {#crm-users-advanced-setup}

기본적으로 모든 계정은 [!DNL Marketo Measure] CRM 자격 증명을 사용하는 응용 프로그램. 경우에 따라 계정 소유자는 특정 역할에 대한 액세스를 제한하고 활성 CRM 라이선스가 있는 모든 사용자에게 열리지 말아야 합니다. 고급 설정을 사용하면 CRM 역할 및 그룹을 매핑할 수 있습니다. [!DNL Marketo Measure] 사용자 권한.

매핑된 역할이나 그룹이 없으면 기본 설정은 CRM의 모든 활성 라이선스에 표준 사용자 액세스 권한이 있는 것입니다.

* [!DNL Marketo Measure] 표준 사용자: 다음에 대한 읽기 전용 액세스 권한을 가져야 하는 사용자의 역할 또는 그룹 값을 제공하십시오. [!DNL Marketo Measure] 응용 프로그램.
* [!DNL Marketo Measure] 계정 관리자 사용자: 다음에 대한 관리 액세스 권한이 필요한 사용자의 역할 또는 그룹 값을 제공합니다. [!DNL Marketo Measure] 응용 프로그램. 즉, 역할은 계정과 관련된 구성 및 설정을 변경할 수 있는 액세스 권한이 있습니다.

여러 역할 또는 그룹을 역할에 매핑해야 하는 경우 각 값을 쉼표로 구분하여 입력합니다.

**Salesforce 역할**

대상 [!DNL Salesforce] 역할, 각 역할의 이름을 사용합니다. 모든 역할은 다음에서 찾을 수 있습니다. [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] 메뉴 아래의 제품에서 사용할 수 있습니다.

![](assets/6.png)

**Dynamics 역할**

대상 [!DNL Dynamics] 역할, 각 보안 역할의 이름을 사용합니다. 모든 보안 역할은 [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] 메뉴 아래의 제품에서 사용할 수 있습니다.

![](assets/7.png)

![](assets/8.png)

**Google 사용자**

사용자 정의 SSO가 설정되면 [!UICONTROL Users] 페이지가 Google 로그인과 함께 추가된 외부 사용자만 표시하도록 업데이트됩니다. 액세스 권한이 있는 모든 사용자는 SSO 구성을 통해 정의되므로 여기에 추가 외부 사용자가 나열됩니다.

![](assets/9.png)

유효함 [!DNL Google] 계정을 추가할 수 있으며 사용자 역할이 정의되어 있어야 합니다.

## 외부 링크 {#external-links}

* [옥타](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Id ping](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
