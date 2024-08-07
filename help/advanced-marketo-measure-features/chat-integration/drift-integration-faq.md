---
unique-page-id: 27656441
description: 드리프트 통합 FAQ - [!DNL Marketo Measure]
title: 드리프트 통합 FAQ
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# 드리프트 통합 FAQ {#drift-integration-faq}

Drift와 [!DNL Marketo Measure] 통합의 일부로 다음과 같은 FAQ가 있습니다. 아래에 요약되지 않은 질문이 있는 경우 Adobe 계정 팀(계정 관리자) 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하십시오.

**통합은 어떻게 활성화됩니까?**

[!DNL Marketo Measure]에 대한 드리프트 채팅 추적이 기본적으로 활성화되어 있습니다. 이를 비활성화하려면(기본적으로 드리프트 채팅에서 터치포인트를 만들지 않으려면) 아래에 굵게 표시된 [!DNL Marketo Measure] Javascript 구현에 추가된 특성을 더 추가하십시오.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

[!DNL Google Tag Manager]을(를) 사용하여 [!DNL Marketo Measure] 스크립트를 로드하는 사용자의 경우, 드리프트 채팅을 터치포인트 대상에서 제외하려면 [!DNL Marketo Measure] 스크립트 바로 뒤에 다음 `<span>`에 추가하십시오.

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**통합은 어떤 작업을 수행합니까?**

이제 통합을 통해 [!DNL Marketo Measure]은(는) 최종 사용자가 드리프트 채팅에서 이메일 주소를 제공하는 시기를 추적할 수 있습니다. 여기에서 &quot;웹 채팅&quot;의 터치포인트 유형과의 상호 작용에서 터치포인트를 만듭니다. 이 통합을 통해 마케터는 채팅 상호 작용의 성능을 이해하고, 사람들이 이러한 채팅과 상호 작용하도록 유도하는 채널/하위 채널/캠페인을 파악할 수 있습니다.

**Campaign 동기화 규칙을 통해 드리프트를 추적하는 경우 어떻게 합니까?**

Drift 채팅 상호 작용을 위한 터치포인트를 만들기 위한 캠페인 동기화 규칙이 있는 경우 해당 CRM 캠페인에 이러한 특정 최종 사용자를 추가하는 것을 중지하십시오. 그렇지 않고 기능 비트가 활성화되면 하나의 드리프트 채팅 상호 작용을 위한 CRM Campaign 터치포인트 및 디지털 터치포인트를 만드십시오.

**CRM 캠페인을 통해 드리프트를 추적하는 경우 어떻게 해야 합니까?**

드리프트 채팅 상호 작용을 위한 터치포인트를 만들기 위한 CRM 캠페인이 있는 경우, 터치포인트 종료 날짜를 해당 특정 캠페인에 설정해야 합니다(터치포인트 종료 날짜는 웹 채팅 통합 기능 비트가 활성화된 날짜여야 함).

**활동을 통해 드리프트를 추적하는 경우 어떻게 해야 합니까?**

Drift 채팅 상호 작용에 대한 터치포인트를 만들기 위한 활동 규칙이 있는 경우 규칙에 추가 논리를 추가해야 합니다. 터치포인트의 중복을 방지하려면 작업 생성 날짜 필드를 사용하여 논리를 추가합니다(예: CrmTask.CreatedDate가 기능 비트가 활성화된 날짜보다 작음). 예를 들어 아래 스크린샷 을 참조하십시오.

![](assets/activity-rule-drift.png)
