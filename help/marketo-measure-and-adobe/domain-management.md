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

Experience Cloud 인터페이스에서 [!DNL Marketo Measure]을(를) 실행하는 IMS 사용 테넌트의 경우 [!DNL Marketo Measure]은(는) 사용자가 자신의 도메인 목록을 관리할 수 있는 인터페이스를 제공합니다. [!DNL Marketo Measure] 사용자는 먼저 [Adobe Admin Console](https://adminconsole.adobe.com/)에서 추적할 도메인을 확인해야 합니다. Admin Console에서 도메인이 확인되면 [!DNL Marketo Measure]이(가) 이러한 도메인을 웹 사이트 트래픽 추적에 사용하는지 여부를 관리할 수 있습니다.

## Admin Console에서 도메인 추가 {#adding-domains-in-admin-console}

Adobe Admin Console에 대한 액세스 권한이 있는 IMS 사용자는 자신이 소유한 도메인을 추가하고 확인할 수 있습니다. 도메인 유효성 검사에는 각 도메인에 대한 DNS 레코드를 추가한 다음 Admin Console이 해당 레코드를 확인하도록 허용하는 작업이 포함됩니다.

![](assets/domain-management-1.png)

도메인 추가 지침은 [Admin Console 설명서](https://helpx.adobe.com/kr/enterprise/using/add-domains-directories.html)에서 찾을 수 있습니다. 도메인이 추가되면 [디렉터리에 연결](https://helpx.adobe.com/kr/enterprise/using/add-domains-directories.html#link-domains-to-directoies)되어야 합니다.

## [!DNL Marketo Measure]에서 도메인 관리 {#managing-domains-in-marketo-measure}

도메인이 Admin Console에 추가되면 [!DNL Marketo Measure]이(가) 이 레코드를 정기적으로 데이터베이스에 동기화합니다. 이러한 동기화는 매일 밤 수행되며 사용자가 [!DNL Marketo Measure] UI에서 **[!UICONTROL Domains]** 페이지를 방문할 때마다 수행됩니다. 기본적으로 [!DNL Marketo Measure]에서 가져오는 모든 레코드는 비활성화되며 테넌트는 각 도메인을 수동으로 활성화해야 합니다.

![](assets/domain-management-2.png)

**[!UICONTROL Integration]** > **[!UICONTROL Domains]** 페이지에서 Admin Console에 등록한 모든 도메인이 상태와 함께 표시됩니다. 각 도메인을 활성화하거나 비활성화할 수 있습니다. 도메인이 활성화되어 있으면 [!DNL Marketo Measure] 추적은 해당 도메인에서 보이는 모든 트래픽을 수집합니다. 도메인이 비활성화되면 [!DNL Marketo Measure]은(는) 해당 도메인에서 들어오는 모든 트래픽을 무시하고 터치포인트나 다른 데이터를 만들지 않습니다. [!DNL Marketo Measure]이(가) 도메인 사용 불능을 확인하고 결과를 경고합니다.

![](assets/domain-management-3.png)

도메인 전환의 영향은 즉각적이고 변경 사항은 소급 적용되지 않습니다. 앞으로 [!DNL Marketo Measure]은(는) 설정된 기간 후에 비활성화된 도메인에서 데이터를 제거합니다.

## 상태 {#statuses}

Admin Console 상태는 다음과 같이 분류됩니다.

* **확인됨**: 이 도메인은 Admin Console에서 확인됩니다.
* **확인되지 않음**: 이 도메인은 Admin Console에서 완전히 확인되지 않았으며 [!DNL Marketo Measure]에서 추적할 수 없습니다.
* **잘못됨**: 이 도메인이 만료되었거나 Admin Console에서 제거되었을 수 있습니다. [!DNL Marketo Measure]의 추적 데이터가 삭제 플래그가 지정되었습니다.
* **레거시**: 이 도메인은 [!DNL Marketo Measure]에 만들어졌으며 Admin Console에 없습니다.

추적 상태는 다음과 같습니다.

* **ACTIVE**: [!DNL Marketo Measure]이(가) 이 도메인에서 데이터를 받는 중입니다.
* **사용 안 함**: 이 도메인은 추적에 사용할 수 있지만 사용할 수 없습니다.
* **사용할 수 없음**: 이 도메인은 확인되지 않았으므로 추적에 사용할 수 없습니다.

개별 상태 항목 위로 마우스를 가져가면 해당 상태를 자세히 설명하는 도구 설명이 트리거됩니다.

## FAQ {#faq}

**Admin Console에서 도메인이 제거되면 어떻게 됩니까?**

Admin Console에서 도메인이 제거되면 [!DNL Marketo Measure]이(가) 해당 도메인을 삭제된 것으로 표시합니다. [!DNL Marketo Measure]은(는) 이 도메인에서 트래픽 추적을 즉시 중지하지만 이전에 수집된 데이터는 제거하지 않습니다.

**도메인을 사용할 수 없는 이유는 무엇입니까?**

이 페이지에서 도메인을 선택할 수 없는 몇 가지 이유가 있습니다. Admin Console에서 도메인이 확인되지 않으면 [!DNL Marketo Measure]에서 사용할 수 없습니다. 마찬가지로 도메인이 현재 [!DNL Marketo Measure] 테넌트와 다른 Adobe 조직에서 소유한 경우 선택하지 못할 수 있습니다.

**이 목록에서 도메인을 제거하려면 어떻게 해야 합니까?**

도메인에 &quot;사용&quot; 스위치가 꺼져 있으면 [!DNL Marketo Measure]이(가) 이를 무시하므로 [!DNL Marketo Measure]에서 효과적으로 제거됩니다. [!DNL Marketo Measure]에서 도메인을 영구적으로 제거하려면 [!DNL Marketo Measure]에서 Admin Console을 사용하지 않도록 설정한 다음 도메인에서 제거해야 합니다.
