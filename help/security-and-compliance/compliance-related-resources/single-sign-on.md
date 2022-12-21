---
unique-page-id: 18874761
description: 단일 사인온 - [!DNL Marketo Measure] - 제품 설명서
title: 단일 사인온
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 0%

---

# 단일 사인온 {#single-sign-on}

SSO(Single Sign-On)용 SAML(보안 어설션 마크업 언어)을 사용하면 사용자가 회사에 로그인할 때 회사의 ID 공급자를 통해 인증할 수 있습니다. [!DNL Marketo Measure] 앱. SSO를 사용하면 별도의 앱을 인증하지 않고도 한 번만 인증할 수 있습니다. SAML은 모든 사용자에게 [!DNL Salesforce] 또는 [!DNL Google] 조직 내 계정. 스케일링하려면 [!DNL Marketo Measure] 는 회사 ID 공급자를 지원할 수 있는 SAML 솔루션을 개발했습니다.

>[!CAUTION]
>
>이 문서에서는 SSO(Single Sign On) 및 고급 CRM 사용자 관리에 대해 설명합니다. 계정이 프로비저닝된 경우 **후 9/10/2020** SSO 및 Identity Management이 JavaScript에서 설정되므로 이 문서를 무시하십시오 [Adobe Admin Console for your [!DNL Marketo Measure] 통합](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>회사에서는 서로 다른 ID 공급자(예: Ping Identity, Okta)를 사용할 수 있습니다. 다음 설정 지침 및 UI에서 사용되는 용어는 ID 공급자가 사용하는 용어와는 직접 일치하지 않을 수 있습니다.

## 요구 사항 {#requirements}

* 에서 AccountAdmin 권한이 있는 사용자 [!DNL Marketo Measure] 앱
* 고객의 ID 공급자에 대한 관리자 액세스 권한이 있는 사용자

## 시작하기 {#getting-started}

시작하려면 아래의 설정 > 보안 > 인증 페이지로 이동합니다 [!DNL Marketo Measure] 응용 프로그램. 그런 다음 로그인 유형을 사용자 지정 SSO로 전환하여 구성 옵션을 확인합니다. 변경 사항은 인증을 테스트하고 **[!UICONTROL Save]** 단추 를 클릭합니다.

![](assets/single-sign-on-1.png)

## 프로세스 {#process}

[!DNL Marketo Measure] Single Sign On을 사용하려면 사용자가 잠기지 않도록 따라야 할 중요한 일련의 단계로 인증 설정을 구성해야 합니다 [!DNL Marketo Measure] 계정이 필요합니다.

설정 [!DNL Marketo Measure] ID 공급자의 응용 프로그램입니다. 연습은 아래 나열된 외부 설명서를 참조하십시오.

    a. 단일 사인온 URL 또는 수신자 URL 또는 대상 URL을 묻는 메시지가 표시되면 [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)을 사용하십시오
    
    나. 대상 제한 URL 또는 응용 프로그램 정의 고유 식별자를 묻는 메시지가 표시되면 [https://BizibleLPM](https://biziblelpm/)을 사용합니다

에서 사용자 지정 SSO로 전환 [!DNL Marketo Measure] 애플리케이션

    a. 계정에 대해 청구 그룹이 활성화되면 이제 다음 위치로 이동할 수 있습니다. [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    나. 기본적으로 로그인 유형은 &quot;CRM 사용자&quot;로 설정됩니다.
    
    c. 구성 프로세스를 시작하려면 로그인 유형을 &quot;사용자 지정 SSO&quot;로 전환합니다.

ID 공급자 구성에 대한 연결 설정을 입력합니다

    a. ID 공급자는 필요한 구성 필드를 가져오는 IdP 메타데이터 .xml 문서를 제공할 수 있습니다. .xml 문서의 내용을 로드하거나 ID 공급자 구성 프로세스 중에 얻은 출력에서 아래의 세 필드를 채웁니다. **두 작업을 모두 완료할 필요는 없습니다.**
    
    나. IdP URL: 다음 URL을 사용하는 URL [!DNL Marketo Measure] 사용자를 [!DNL Marketo Measure] 응용 프로그램. 경우에 따라 &quot;리디렉션 URL&quot;이라고도 합니다.
    ii. IdP 발급자: ID 공급자의 고유 식별자입니다. 경우에 따라 &quot;외부 키&quot;라고도 합니다.
    3. IdP 인증서: 를 허용하는 공개 키 [!DNL Marketo Measure] 모든 ID 공급자 응답의 서명을 확인하고 검증하려면

사용자에 대한 토큰 만료를 분 단위로 설정합니다.

    a. [!DNL Marketo Measure] 1분에서 140분 사이의 정수를 허용합니다. 사용자의 세션 시간이 초과되면 새 페이지로 이동하면 사용자가 로그아웃됩니다.

사용자 특성 설정을 설정하고 각 이름, 성 및 이메일 주소에 매핑합니다.

    a. SAML 속성을 입력하여 [!DNL Marketo Measure] 는 전달된 정보를 통해 사용자를 인식할 수 있습니다.
    
    나. 전자 메일 속성: ID 공급자가 사용자의 이메일 주소에 사용하는 속성 이름을 입력합니다.
    ii. 이름 속성: ID 공급자가 사용자의 이름에 사용하는 속성 이름을 입력합니다.
    3. 성 속성: ID 공급자가 사용자의 성에 사용하는 속성 이름을 입력합니다.
    
    나. 힌트: 지금 SAML 구성을 테스트하는 경우 이 섹션에 사용할 수 있는 이메일, 이름 및 성 속성을 구문 분석합니다.

![](assets/single-sign-on-2.png)

사용자 역할 설정을 설정하고 IdP에서 분류된 각 역할 또는 그룹에 매핑합니다.

    a. 고객은 다음을 지정할 수 있습니다 [!DNL Marketo Measure] 사용자 역할은 ID 제공자에 정의된 그룹을 기반으로 합니다. SAML 속성을 입력하여 [!DNL Marketo Measure] 사용자의 역할 및 그룹을 [!DNL Marketo Measure] 사용자 권한. 이러한 역할을 설정하여 [!DNL Marketo Measure] 관리자는 계정을 업데이트할 수 있는 충분한 권한이 있습니다.
    
    나. 매핑된 역할이나 그룹이 없으면 기본 설정은 ID 공급자의 모든 직원이 표준 사용자 액세스 권한을 갖게 된다는 것입니다.
    
    나. [!DNL Marketo Measure] 표준 사용자: SSO 공급자에서 역할에 대한 읽기 전용 액세스 권한을 가져야 하는 사용자의 역할 또는 그룹 값을 제공합니다 [!DNL Marketo Measure] 응용 프로그램.
    ii. [!DNL Marketo Measure] 계정 관리자 사용자: SSO 공급자에서 역할에 대한 관리자 액세스 권한이 있어야 하는 사용자에 대한 역할 또는 그룹 값을 제공합니다 [!DNL Marketo Measure] 응용 프로그램. 즉, 역할에 따라 계정과 관련된 변경 구성 및 설정에 액세스할 수 있습니다.
    3. IdP에 &quot;Bizible Standard User&quot; 또는 &quot;Bizible Account Admin User&quot; 속성에 입력한 값을 포함하는 &quot;groups&quot;의 정확한 이름을 가진 특성이 있어야 합니다.
    
    c. 역할에 여러 역할 또는 그룹을 매핑해야 하는 경우 각 값을 쉼표로 구분하여 입력합니다.

![](assets/single-sign-on-3.png)

Single Sign On 구성 테스트

    a. 저장 을 누르기 전에 [!UICONTROL Test SAML Authentication] 단추를 클릭하여 설정이 올바르게 구성되었는지 확인합니다.
    
    나. &quot;실패&quot; 오류가 표시되면 메시지를 따라 다시 시도하십시오.

![](assets/single-sign-on-4.png)

설정을 저장하고 동료에게 [!UICONTROL Single Sign On] 새 사용자 지정 로그인 URL로 사용.

    a. 중요 사항: 새 인증 설정을 저장하면 CRM 사용자에 의해 로그인을 비활성화하고 사용자 지정 SSO를 활성화했으므로 새 페이지로 이동하면 세션이 종료될 수 있습니다.

![](assets/single-sign-on-5.png)

사용해 보세요!

    a. 새 사용자 지정 로그인 URL을 사용하고, [!DNL Marketo Measure] ID 공급자 자격 증명이 있는 응용 프로그램입니다.
    
    나. 형식은 &#39;https://apps.adobe.com/business/[accountName]&#39;과 비슷합니다
    
    c. 축하합니다! 에 단일 사인온을 설정했습니다. [!DNL Marketo Measure] 계정 지원!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>SSO를 구성한 후에는 더 이상 [!DNL Marketo Measure] 응용 프로그램. 사용자 프로비저닝은 ID 공급자 내에서 직접 처리해야 합니다.

## CRM 사용자(고급 설정) {#crm-users-advanced-setup}

기본적으로 모든 계정이 [!DNL Marketo Measure] 응용 프로그램에서 CRM 자격 증명을 사용하여 응용 프로그램을 만듭니다. 경우에 따라 계정 소유자가 특정 역할에 대한 액세스를 제한해야 하며 활성 CRM 라이선스가 있는 모든 사용자에게 이 역할을 열지 않아야 합니다. 고급 설정을 사용하여 CRM 역할 및 그룹을 [!DNL Marketo Measure] 사용자 권한.

매핑된 역할이나 그룹이 없으면 기본 설정은 CRM의 모든 활성 라이선스에 표준 사용자 액세스 권한이 있다는 것입니다.

* [!DNL Marketo Measure] 표준 사용자: 에 대한 읽기 전용 액세스 권한이 있어야 하는 사용자에게 역할 또는 그룹 값을 제공합니다 [!DNL Marketo Measure] 응용 프로그램.
* [!DNL Marketo Measure] 계정 관리자 사용자: 에 대한 관리자 액세스 권한이 있어야 하는 사용자의 역할 또는 그룹 값을 제공합니다. [!DNL Marketo Measure] 응용 프로그램. 즉, 역할에 따라 계정과 관련된 변경 구성 및 설정에 액세스할 수 있습니다.

여러 역할이나 그룹을 역할에 매핑해야 하는 경우 각 값을 쉼표로 구분하여 입력합니다.

**Salesforce 역할**

대상 [!DNL Salesforce] 역할에서 각 역할의 이름을 사용합니다. 모든 역할은 [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] 메뉴 아래의 제품에서 사용할 수 있습니다.

![](assets/6.png)

**Dynamics 역할**

대상 [!DNL Dynamics] 역할에서는 각 보안 역할의 이름을 사용합니다. 모든 보안 역할은 [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] 메뉴 아래의 제품에서 사용할 수 있습니다.

![](assets/7.png)

![](assets/8.png)

**Google 사용자**

사용자 지정 SSO가 설정되면 [!UICONTROL Users] Google 로그인으로 추가된 외부 사용자만 표시하도록 페이지가 업데이트됩니다. 액세스 권한이 있는 모든 사용자는 SSO 구성을 통해 정의되므로 여기에 추가 외부 사용자가 나열됩니다.

![](assets/9.png)

유효함 [!DNL Google] 계정을 추가할 수 있으며 사용자 역할이 정의되어 있어야 합니다.

## 외부 링크 {#external-links}

* [Okta](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping Id](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
