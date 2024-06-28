---
description: "[!DNL Marketo Measure] Salesforce 패키지 설치 및 설정 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] [!DNL Salesforce] 패키지 설치 및 설정"
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce 패키지 설치 및 설정 {#marketo-measure-salesforce-package-installation-and-set-up}

설치하기 전에 [!DNL Marketo Measure] [!DNL Salesforce] 기본 패키지에서 먼저 설치할지 여부를 [!DNL Salesforce] Salesforce 프로덕션 인스턴스로 이동하기 전에 샌드박스 를 사용하십시오.

>[!NOTE]
>
>한 번 [!DNL Marketo Measure] 계정이 다음에 연결됨: [!DNL Salesforce] 프로덕션 인스턴스는 뒤로 이동하여 샌드박스에 연결할 수 없습니다. 또한 [!DNL Marketo Measure] 계정은 하나에만 연결할 수 있습니다. [!DNL Salesforce] 프로덕션 인스턴스.

다음 [!DNL Marketo Measure] 기본 패키지에는 다음이 포함됩니다.

* 7 사용자 정의 [!DNL Marketo Measure] 오브젝트
* 사용자 정의 [!DNL Marketo Measure] 필드
* 25 [!DNL Stock] 보고서

[!DNL Marketo Measure] 표준 읽기 가능 [!DNL Salesforce] 그러나 오브젝트, 필드 및 레코드는 [!DNL Marketo Measure] 는 데이터를 업데이트하거나 푸시하지 않습니다. 에서 수집한 모든 데이터 [!DNL Marketo Measure] JavaScript는 [!DNL Marketo Measure] 사용자 지정 개체 및 필드.

아래 단계에 따라 [!DNL Marketo Measure Salesforce] 기본 패키지.

1. 시크릿 브라우저를 사용하여 [Salesforce AppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} 로그인합니다.

1. 에 설치 [!DNL Marketo Measure] 샌드박스 또는 프로덕션의 패키지

1. 에 로그인 [!DNL Salesforce] 관리자로서.

1. 선택 **[!UICONTROL Install]모든 사용자용**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 설치가 완료되면 이를 볼 수 있습니다.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

설치를 완료한 후 를 업데이트할 수 있습니다. [[!DNL Salesforce] 페이지 레이아웃](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} (으)로 [!DNL Marketo Measure] 원하는 경우 필드.

>[!NOTE]
>
>에 대해 읽기 [!DNL Marketo Measure] 권한 집합을 만들고 [사용 방법](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## 만들기 [!DNL Marketo Measure] 프로필 및 사용자 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] 연결된 을(를) 통해 데이터 전송 및 수신 [!DNL Salesforce] 다음 내의 사용자 [!DNL Marketo Measure] 앱.

터치포인트 데이터를 로 푸시하려면 [!DNL Salesforce] 인스턴스: 연결된 사용자는 다음에 대한 액세스 권한이 있어야 합니다. [!DNL Marketo Measure] 사용자 지정 개체(예: Buyer Touchpoint 및 Buyer Attribution Touchpoint)와 표준 [!DNL Salesforce] 잠재 고객 및 연락처 등의 객체.

만들기 [!DNL Marketo Measure] 프로필 을 사용하십시오.

1단계: 특정 만들기 [!DNL Marketo Measure] 프로필

1. 다음 권한을 할당합니다.

* &quot;[!DNL Marketo Measure] 관리자 권한 집합&quot;
   * 관리 권한 집합은 SFDC 관리자에게 레코드 만들기, 읽기, 쓰기 및 삭제 기능을 제공합니다. [!DNL Marketo Measure] 개체.
* &quot;전환된 잠재 고객 권한 집합 보기 및 편집&quot;
   * 이렇게 하면 [!DNL Marketo Measure] 잠재 고객을 연락처로 전환한 후 장식합니다. 이 권한 집합을 활성화하지 않으면 상당한 데이터 추적 간격이 발생할 수 있습니다.

>[!NOTE]
>
>이 프로필은 시스템 관리자 프로필의 복제본일 수 있습니다.

2단계: 전용 만들기 [!DNL Marketo Measure] 의 영향을 추적할 수 있는 사용자 [!DNL Marketo Measure] 다음에 대한 [!DNL Salesforce] 인스턴스

1. 새 항목 할당 [!DNL Marketo Measure] 해당 사용자에 대한 프로필입니다.

1. 사용자 수준 권한으로 &quot;마케팅 사용자&quot;를 활성화합니다.

* 다음 [!UICONTROL Marketing User] 확인란을 통해 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 사용자는 캠페인 및 고급 캠페인 설정만 보고, 단일 리드 또는 연락처에 대한 캠페인 내역을 편집하고, 캠페인 보고서를 실행할 수 있습니다. [!DNL Marketo Measure] 캠페인 개체를 읽고 쓸 수 있어야 합니다.

3단계: 모든 트리거, 워크플로우 및 프로세스에서 이 프로필 제외

4단계: 다음에 로그인 [!DNL Marketo Measure] 계정 및 재인증 [!DNL Salesforce] 새 사용자와의 연결

1. apps.bizible.com으로 이동한 다음 새 사용자 프로덕션으로 로그인합니다. [!DNL Salesforce] 자격 증명.

1. 선택 **[!UICONTROL Settings]** 다음 범위 내 **[!UICONTROL My Account]** 드롭다운.

1. 선택 **[!UICONTROL Connections]** 다음 범위 내 **[!UICONTROL Integrations]** 그룹화.

1. 현재 연결된 항목 오른쪽에 있는 키 아이콘 을 클릭합니다 [!DNL Salesforce] 연결 및 선택 **프로덕션으로 재인증**. 새 사용자 자격 증명으로 다시 로그인합니다(메시지가 표시되면).

>[!MORELIKETHIS]
>
>* [통합 권한 개요](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
>
>* [Adobe Admin Console 설정](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
