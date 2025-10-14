---
description: Adobe Admin Console 설정 - Marketo Measure - 제품 설명서
title: Adobe Admin Console 설정
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Adobe Admin Console 설정 {#adobe-admin-console-setup}

[!DNL Marketo Measure]을(를) 사용하는 첫 번째 단계는 프로비저닝된 Adobe Admin Console을 만들고 로그인하는 것입니다. 로그인 지침이 포함된 전자 메일을 받지 못한 경우 [!DNL Marketo Measure] 계정 담당자에게 문의하십시오.

## Adobe Admin Console 및 ID 공급자 설정 {#set-up-your-adobe-admin-console-and-identity-provider}

Adobe 세트 내의 제품으로서 [!DNL Marketo Measure]은(는) Identity Management용 Adobe Admin Console의 모든 기능을 사용합니다. [여기에서 &#x200B;](https://helpx.adobe.com/kr/enterprise/using/admin-console.html)개의 리소스를 더 찾을 수 있습니다.

[Identity Management](https://helpx.adobe.com/kr/enterprise/using/set-up-identity.html)에서 사용할 수 있는 리소스, 모범 사례 및 옵션을 검토하는 것이 좋습니다.

Adobe Admin Console 내에서 Identity Management 설정에 대한 지침과 검토를 보려면 [!DNL Marketo Measure] 계정 담당자에게 문의하십시오.

[!DNL Marketo Measure] 인스턴스로 사용자 인증 및 권한 부여를 용이하게 하려면 Adobe Admin Console 내에서 다음 단계를 수행해야 합니다.

**[!DNL Marketo Measure] 제품 카드 설정**

Adobe Admin Console에 액세스하면 개요 섹션에 [!DNL Marketo Measure] 제품 인스턴스가 표시됩니다.

![](assets/adobe-admin-console-setup-1.png)

[!DNL Marketo Measure] 제품 카드를 클릭하면 모든 [!DNL Marketo Measure] 인스턴스가 표시됩니다. 기본적으로 각 [!DNL Marketo Measure] 인스턴스에는 &#39;[!DNL Marketo Measure]&#39; 접두사가 붙은 자체 프로필이 있습니다. 이 인스턴스 또는 이 인스턴스 내의 다른 프로필에 추가된 모든 관리자 또는 사용자는 [!DNL Marketo Measure]에 로그인할 수 있습니다.

![](assets/adobe-admin-console-setup-2.png)

[!DNL Marketo Measure] 제품 인스턴스 내에서 프로필을 만드는 데 필요한 작업이 없습니다.

[!DNL Marketo Measure]에 액세스할 수 있는 사용자를 추가하려면 아래의 [추가 [!DNL Marketo Measure] 관리자 및 [!DNL Marketo Measure] 사용자](#adding-marketo-measure-admins-and-marketo-measure-users) 섹션을 참조하십시오.

## [!DNL Marketo Measure] 관리자 및 [!DNL Marketo Measure] 사용자 추가 중 {#adding-marketo-measure-admins-and-marketo-measure-users}

다음 단계는 사용자를 추가하여 [!DNL Marketo Measure] 응용 프로그램에 대한 액세스 권한을 부여하는 것입니다. 이 작업은 [!DNL Marketo Measure] 제품 카드의 관리자 및 사용자 디렉터리에서 수행할 수 있습니다.

| 사용자 유형 | 설명 |
|---|---|
| 관리자 | [!DNL Marketo Measure]별 구성 옵션을 업데이트하고 관리할 수 있는 모든 기능을 갖춘 [!DNL Marketo Measure] 응용 프로그램의 관리자 및 고급 사용자입니다. |
| 사용자 | [!DNL Marketo Measure] 응용 프로그램 내에서 읽기 전용 권한이 있는 [!DNL Marketo Measure] 응용 프로그램의 표준 사용자입니다. |

사용자를 해당 그룹에 추가하면 [ID 유형이 나열됩니다](https://helpx.adobe.com/kr/enterprise/using/set-up-identity.html).

>[!NOTE]
>
>[!DNL Marketo Measure] 관리자([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}에서)가 되려면 [!DNL Marketo Measure] 제품 카드 내의 [!DNL Marketo Measure] 제품 프로필에 사용자를 사용자 _및_ 관리자로 추가해야 합니다.

[!DNL Marketo Measure]&#x200B;**에**&#x200B;로그인 중

사용자가 제품 프로필에 추가되면 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}에서 **Adobe ID으로 로그인** 옵션을 선택하여 [!DNL Marketo Measure] 인스턴스에 액세스할 수 있습니다.

![](assets/adobe-admin-console-setup-3.png)
