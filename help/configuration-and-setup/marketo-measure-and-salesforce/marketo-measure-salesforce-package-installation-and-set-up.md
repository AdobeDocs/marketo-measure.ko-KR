---
description: "[!DNL Marketo Measure] Salesforce 패키지 설치 및 설정 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] [!DNL Salesforce] 패키지 설치 및 설정"
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce 패키지 설치 및 설정 {#marketo-measure-salesforce-package-installation-and-set-up}

설치하기 전에 [!DNL Marketo Measure] [!DNL Salesforce] 기본 패키지에서 처음 설치할 것인지 확인해야 합니다. [!DNL Salesforce] Salesforce 프로덕션 인스턴스로 이동하기 전에 샌드박스 를 만듭니다.

>[!NOTE]
>
>한 번 [!DNL Marketo Measure] 계정이 [!DNL Salesforce] 프로덕션 인스턴스의 경우 뒤로 이동하고 샌드박스에 연결할 수 없습니다. 또한, [!DNL Marketo Measure] 계정은 하나만 연결할 수 있습니다 [!DNL Salesforce] 프로덕션 인스턴스.

다음 [!DNL Marketo Measure] 기본 패키지에는 다음이 포함됩니다.

* 7 사용자 지정 [!DNL Marketo Measure] 개체
* 사용자 지정 [!DNL Marketo Measure] 필드
* 25년 [!DNL Stock] 보고서

[!DNL Marketo Measure] 표준 을 읽을 수 있음 [!DNL Salesforce] 그러나 객체, 필드 및 레코드는 [!DNL Marketo Measure] 는 데이터를 업데이트하거나 푸시하지 않습니다. 에서 수집한 모든 데이터 [!DNL Marketo Measure] Javascript가 [!DNL Marketo Measure] 사용자 정의 개체 및 필드.

아래 절차에 따라 을(를) 설치하십시오. [!DNL Marketo Measure Salesforce] 기본 패키지

1. Incognito 브라우저를 사용하여 [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} 로그인하고

1. 에 를 설치합니다. [!DNL Marketo Measure] 샌드박스 또는 프로덕션에 있는 패키지

1. 에 로그인합니다. [!DNL Salesforce] 관리자로.

1. 선택 **[!UICONTROL Install]모든 사용자**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 설치가 완료되면 볼 수 있습니다.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

설치를 완료하면 [[!DNL Salesforce] 페이지 레이아웃](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} 사용 [!DNL Marketo Measure] 원하는 경우 필드를 선택합니다.

>[!NOTE]
>
>다음 문서를 참조하십시오 [!DNL Marketo Measure] 만든 권한 집합 및 [사용 방법](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## 설치 [!DNL Marketo Measure] 대시보드 패키지 {#install-marketo-measure-dashboard-package}

다음 [!UICONTROL Dashboard] 확장 패키지에는 미리 빌드된 3개의 대시보드가 포함되어 있습니다. 설치를 권장합니다 [!UICONTROL within] 모든 사용자를 위한 프로덕션.

1. 에서 패키지 설치 [[!DNL Salesforce] Appexchange](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}.

1. 선택 **[!UICONTROL Install for All Users]**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-3.png)

## 만들기 [!DNL Marketo Measure] 프로필 및 사용자 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] 연결된 데이터를 통해 전송 및 수신 [!DNL Salesforce] 내 사용자 [!DNL Marketo Measure] 앱.

터치 포인트 데이터를 [!DNL Salesforce] 예를 들어 연결된 사용자는 [!DNL Marketo Measure] 사용자 지정 객체(예: Buyer Touchpoint 및 Buyer Attribution Touchpoint)와 표준 [!DNL Salesforce] 리드 및 연락처와 같은 객체

만들기 [!DNL Marketo Measure] Salesforce로 데이터를 푸시할 때 유효성 검사 오류가 발생하지 않도록 하기 위한 프로필입니다.

1단계: 특정 만들기 [!DNL Marketo Measure] 프로필

1. 다음 권한을 지정하십시오.

* &quot;[!DNL Marketo Measure] 관리자 권한 집합&quot;
   * 관리 권한 집합에서는 SFDC 관리자가 레코드를 작성, 읽기, 쓰기, 삭제할 수 있는 기능을 제공합니다. [!DNL Marketo Measure] 개체.
* &quot;변환된 리드 보기 및 편집 권한 집합&quot;
   * 이렇게 하면 [!DNL Marketo Measure] 연락처로 전환한 후에 리드를 장식하기 위해. 이 권한 세트가 활성화되어 있지 않으면 상당한 데이터 추적 차이가 있을 수 있습니다.

>[!NOTE]
>
>이 프로필은 시스템 관리자 프로필의 클론일 수 있습니다.

2단계: 전용 만들기 [!DNL Marketo Measure] 사용자의 영향을 추적할 수 있습니다. [!DNL Marketo Measure] 설정 [!DNL Salesforce] 인스턴스

1. 새 [!DNL Marketo Measure] 해당 사용자에 대한 프로필.

1. 사용자 수준 권한으로 &quot;마케팅 사용자&quot;를 활성화합니다.

* 다음 [!UICONTROL Marketing User] 확인란을 통해 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 사용자는 캠페인 및 고급 캠페인 설정만 보고, 단일 리드 또는 연락처에 대한 캠페인 내역을 편집하고, 캠페인 보고서를 실행할 수 있습니다. [!DNL Marketo Measure] campaign 개체를 읽고 쓸 수 있어야 합니다.

3단계: 모든 트리거, 워크플로우 및 프로세스에서 이 프로필 제외

4단계: 에 로그인 [!DNL Marketo Measure] 계정 및 재인증 [!DNL Salesforce] 새 사용자와 연결

1. apps.bizible.com으로 이동한 다음 새 사용자 프로덕션으로 로그인합니다 [!DNL Salesforce] 자격 증명.

1. 선택 **[!UICONTROL Settings]** 내 **[!UICONTROL My Account]** 드롭다운.

1. 선택 **[!UICONTROL Connections]** 내 **[!UICONTROL Integrations]** 그룹화.

1. 연결된 현재 오른쪽에 있는 키 아이콘을 클릭합니다 [!DNL Salesforce] 연결 후 **프로덕션으로 재인증**. 새 사용자 자격 증명으로 다시 로그인합니다(메시지가 표시되면).
