---
description: 도메인 관리 - [!DNL Marketo Measure] - 제품 설명서
title: 도메인 관리
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# 도메인 관리 {#domain-management}

실행 중인 IMS 사용 테넌트의 경우 [!DNL Marketo Measure] 통합 쉘에서 [!DNL Marketo Measure] 에서는 사용자가 고유한 도메인 목록을 관리할 수 있는 인터페이스를 제공합니다. [!DNL Marketo Measure] 사용자는에서 추적할 도메인을 먼저 확인해야 합니다 [Adobe Admin Console](https://adminconsole.adobe.com/). Admin Console에서 도메인이 확인되면 사용자가 다음을 관리할 수 있습니다 [!DNL Marketo Measure] 는 웹 사이트 트래픽을 추적하기 위해 이러한 도메인을 사용합니다.

## Admin Console에서 도메인 추가 {#adding-domains-in-admin-console}

Adobe Admin Console에 액세스할 수 있는 IMS 사용자는 자신이 소유한 도메인을 추가하고 유효성을 확인할 수 있습니다. 도메인 유효성 검사에는 각 도메인에 대한 DNS 레코드를 추가한 다음 Admin Console이 해당 레코드를 확인할 수 있도록 하는 작업이 포함됩니다.

![](assets/domain-management-1.png)

도메인 추가 지침은 [Admin Console 설명서](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). 도메인을 추가한 후에는 [디렉토리에 연결](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## 의 도메인 관리 [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Admin Console에 도메인이 추가되면, [!DNL Marketo Measure] 이 레코드를 정기적으로 데이터베이스에 동기화합니다. 이러한 동기화는 매일 밤 발생하고 사용자가 를 방문할 때마다 발생합니다 **[!UICONTROL Domains]** 페이지의 [!DNL Marketo Measure] UI. 기본적으로 [!DNL Marketo Measure] 가져오기가 비활성화되고 임차인이 각 도메인을 수동으로 활성화해야 합니다.

![](assets/domain-management-2.png)

설정 **[!UICONTROL Integration]** > **[!UICONTROL Domains]** Admin Console에 등록한 모든 도메인과 해당 상태가 표시됩니다. 각 도메인을 활성화하거나 비활성화할 수 있습니다. 도메인이 활성화된 경우, [!DNL Marketo Measure] 추적은 해당 도메인에 표시되는 모든 트래픽을 수집합니다. 도메인이 비활성화되어 있으면, [!DNL Marketo Measure] 은 해당 도메인에서 오는 것으로 보이는 트래픽을 무시하며 터치포인트나 다른 데이터를 만들지 않습니다. [!DNL Marketo Measure] 또한 도메인의 불능을 확인하고 해당 결과를 경고하게 됩니다.

![](assets/domain-management-3.png)

도메인을 전환하면 즉시 영향을 받게 되며 변경 사항은 소급 적용되지 않습니다. 나중에 [!DNL Marketo Measure] 일정 기간 후에 비활성화된 도메인에서 데이터를 삭제합니다.

## 상태 {#statuses}

Admin Console 상태는 다음과 같이 분류됩니다.

* **유효함**: 이 도메인은 Admin Console에서 확인됩니다
* **확인되지 않음**: 이 도메인은 Admin Console에서 완전히 확인되지 않으며 에서 추적할 수 없습니다 [!DNL Marketo Measure]
* **유효하지 않음**: 이 도메인은 만료되었거나 Admin Console에서 제거되었을 수 있습니다. 의 데이터 추적 [!DNL Marketo Measure] 삭제에 플래그가 지정됨
* **기존**: 이 도메인은 [!DNL Marketo Measure] 및 이 Admin Console에 없습니다

추적 상태는 다음과 같습니다.

* **활성**: [!DNL Marketo Measure] 현재 이 도메인에서 데이터를 받고 있습니다.
* **사용 안 함**: 이 도메인은 추적에 사용할 수 있지만 현재 비활성화되어 있습니다
* **사용할 수 없음**: 이 도메인은 확인되지 않으므로 추적에 사용할 수 없습니다

개별 상태 항목을 마우스로 가리키면 해당 상태를 추가로 설명하는 도구 설명이 트리거됩니다.

## FAQ {#faq}

**Admin Console에서 도메인이 제거되면 어떻게 됩니까?**

Admin Console에서 도메인이 제거되면, [!DNL Marketo Measure] 은(는) 도메인을 삭제된 것으로 표시합니다. [!DNL Marketo Measure] 은 이 도메인에서 트래픽 추적을 즉시 중단하지만 이전에 수집된 데이터는 제거되지 않습니다.

**도메인을 활성화할 수 없는 이유는 무엇입니까?**

이 페이지에서 도메인을 선택할 수 없는 이유는 다음과 같습니다. Admin Console에서 도메인의 유효성을 검사하지 않으면 [!DNL Marketo Measure]. 마찬가지로, 도메인이 현재 조직과 다른 Adobe 조직에 의해 소유한 경우 [!DNL Marketo Measure] 임차인: 선택할 수 없을 수 있습니다.

**이 목록에서 도메인을 제거하려면 어떻게 해야 합니까?**

도메인에 &quot;enabled&quot; 스위치가 꺼져 있으면 [!DNL Marketo Measure] 이 경우 무시되고 [!DNL Marketo Measure]. 에서 도메인을 영구적으로 제거하려면 [!DNL Marketo Measure]에서 비활성화해야 합니다. [!DNL Marketo Measure]를 만든 후 Admin Console에서 제거합니다.
