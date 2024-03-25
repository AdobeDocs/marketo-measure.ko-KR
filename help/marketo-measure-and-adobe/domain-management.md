---
description: 도메인 관리 - [!DNL Marketo Measure]
title: 도메인 관리
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 4c68fa08797c252a89ba097c723fb8afee82451f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# 도메인 관리 {#domain-management}

실행 중인 IMS 지원 테넌트의 경우 [!DNL Marketo Measure] Experience Cloud 인터페이스에서 [!DNL Marketo Measure] 는 사용자가 도메인 목록을 관리할 수 있도록 하는 인터페이스를 제공합니다. [!DNL Marketo Measure] 사용자는에서 추적하려는 도메인을 먼저 확인해야 합니다. [Adobe Admin Console](https://adminconsole.adobe.com/). Admin Console에서 도메인이 확인되면 사용자는 다음을 관리할 수 있습니다. [!DNL Marketo Measure] 은 웹 사이트 트래픽을 추적하는 데 이러한 도메인을 사용합니다.

## Admin Console에서 도메인 추가 {#adding-domains-in-admin-console}

Adobe Admin Console에 대한 액세스 권한이 있는 IMS 사용자는 자신이 소유한 도메인을 추가하고 확인할 수 있습니다. 도메인 유효성 검사에는 각 도메인에 대한 DNS 레코드를 추가한 다음 Admin Console이 해당 레코드를 확인하도록 허용하는 작업이 포함됩니다.

![](assets/domain-management-1.png)

도메인 추가 지침은 [Admin Console 설명서](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). 도메인이 추가되면 다음과 같아야 합니다. [디렉터리에 연결됨](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies).

## 에서 도메인 관리 [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Admin Console에 도메인이 추가되면 [!DNL Marketo Measure] 이 레코드를 정기적으로 데이터베이스에 동기화합니다. 이러한 동기화는 야간에 발생하며 사용자가 를 방문할 때마다 발생합니다. **[!UICONTROL Domains]** 페이지의 [!DNL Marketo Measure] UI. 기본적으로 [!DNL Marketo Measure] 가져오기는 비활성화되며 테넌트가 각 도메인을 수동으로 활성화해야 합니다.

![](assets/domain-management-2.png)

다음에서 **[!UICONTROL Integration]** > **[!UICONTROL Domains]** 페이지에는 Admin Console에 등록한 모든 도메인이 상태와 함께 표시됩니다. 각 도메인을 활성화하거나 비활성화할 수 있습니다. 도메인이 활성화되어 있으면 [!DNL Marketo Measure] 추적은 해당 도메인에 표시되는 모든 트래픽을 수집합니다. 도메인이 비활성화된 경우 [!DNL Marketo Measure] 은 해당 도메인에서 오는 트래픽을 무시하고 터치포인트 또는 기타 데이터를 만들지 않습니다. [!DNL Marketo Measure] 도메인 비활성화 확인 및 결과 경고:

![](assets/domain-management-3.png)

도메인 전환의 영향은 즉각적이고 변경 사항은 소급 적용되지 않습니다. 미래에는 [!DNL Marketo Measure] 은(는) 설정된 기간 후에 비활성화된 도메인에서 데이터를 제거합니다.

## 상태 {#statuses}

Admin Console 상태는 다음과 같이 분류됩니다.

* **확인됨**: 이 도메인은 Admin Console에서 확인됩니다.
* **확인되지 않음**: 이 도메인은 Admin Console에서 완전히 확인되지 않았으며, 추적에 적합하지 않습니다. [!DNL Marketo Measure]
* **잘못됨**: 이 도메인이 만료되었거나 Admin Console에서 제거되었을 수 있습니다. 에서 데이터 추적 [!DNL Marketo Measure] 삭제 플래그가 지정되었습니다.
* **레거시**: 이 도메인은에서 생성되었습니다. [!DNL Marketo Measure] 및 이(가) Admin Console에 없습니다.

추적 상태는 다음과 같습니다.

* **활성**: [!DNL Marketo Measure] 은(는) 이 도메인에서 데이터를 받고 있습니다.
* **비활성화됨**: 이 도메인은 추적에 사용할 수 있지만 비활성화되어 있습니다.
* **사용할 수 없음**: 이 도메인은 확인되지 않으므로 추적에 사용할 수 없습니다.

개별 상태 항목 위로 마우스를 가져가면 해당 상태를 자세히 설명하는 도구 설명이 트리거됩니다.

## FAQ {#faq}

**Admin Console에서 도메인이 제거되면 어떻게 됩니까?**

Admin Console에서 도메인이 제거되면 [!DNL Marketo Measure] 은 도메인을 삭제된 것으로 표시합니다. [!DNL Marketo Measure] 이 도메인에서 즉시 트래픽 추적을 중지하지만 이전에 수집된 데이터는 제거되지 않습니다.

**도메인을 활성화할 수 없는 이유는 무엇입니까?**

이 페이지에서 도메인을 선택할 수 없는 몇 가지 이유가 있습니다. Admin Console에서 도메인의 유효성을 검사하지 못한 경우에서 해당 도메인을 사용할 수 없습니다 [!DNL Marketo Measure]. 마찬가지로 도메인이 현재와 다른 Adobe 조직에서 소유한 경우 [!DNL Marketo Measure] 테넌트입니다. 선택할 수 없습니다.

**이 목록에서 도메인을 제거하려면 어떻게 합니까?**

도메인에 &quot;활성화&quot; 스위치가 꺼져 있는 경우 [!DNL Marketo Measure] 무시하며에서 효과적으로 제거됩니다. [!DNL Marketo Measure]. 에서 도메인을 영구적으로 제거하려면 [!DNL Marketo Measure]에서 비활성화해야 합니다. [!DNL Marketo Measure]을 클릭한 다음 Admin Console에서 제거합니다.
