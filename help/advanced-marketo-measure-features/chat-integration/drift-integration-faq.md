---
unique-page-id: 27656441
description: 드리프트 통합 FAQ - [!DNL Marketo Measure] - 제품 설명서
title: 드리프트 통합 FAQ
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# 드리프트 통합 FAQ {#drift-integration-faq}

의 일부로 [!DNL Marketo Measure] Drift와 통합하여 가장 자주 묻는 질문 중 일부를 간략하게 설명했습니다. 아래에 요약되지 않은 질문이 있는 경우 Adobe 계정 팀(계정 관리자) 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**통합은 어떻게 활성화됩니까?**

에 대한 드리프트 채팅 추적 [!DNL Marketo Measure] 은 기본적으로 활성화되어 있습니다. 어떤 이유로든 비활성화하려는 경우(기본적으로 드리프트 채팅에서 터치포인트를 만들지 않는 경우),에 추가 속성을 추가해야 합니다. [!DNL Marketo Measure] 아래에 굵게 표시된 Javascript 구현:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

을 사용하는 경우 [!DNL Google Tag Manager] 을(를) 로드하려면 [!DNL Marketo Measure] 스크립트. 드리프트 채팅이 터치포인트에 적격하지 않도록 제외하려면 다음을 추가해야 합니다. `<span>` 다음 바로 뒤에 [!DNL Marketo Measure] 스크립트:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**통합은 어떤 작업을 수행합니까?**

이제 통합이 허용합니다. [!DNL Marketo Measure] 최종 사용자가 드리프트 채팅에서 이메일 주소를 제공하는 시기를 추적합니다. 여기에서 &quot;웹 채팅&quot;의 터치포인트 유형과의 상호 작용에서 터치포인트를 만듭니다. 이 통합을 통해 마케터는 채팅 상호 작용의 성능을 이해하고, 사람들이 이러한 채팅과 상호 작용하도록 유도하는 채널/하위 채널/캠페인을 파악할 수 있습니다.

**Campaign 동기화 규칙을 통해 드리프트를 추적하는 경우 어떻게 합니까?**

드리프트 채팅 상호 작용을 위한 터치포인트를 만들기 위한 캠페인 동기화 규칙이 있는 경우, 해당 CRM 캠페인에 이러한 특정 최종 사용자를 추가하는 것을 중지해야 합니다. 그렇지 않고 기능 비트가 활성화되면 하나의 드리프트 채팅 상호 작용을 위한 CRM Campaign 터치포인트 및 디지털 터치포인트를 만듭니다.

**CRM 캠페인을 통해 드리프트를 추적하는 경우 어떻게 합니까?**

드리프트 채팅 상호 작용을 위한 터치포인트를 만들기 위한 CRM 캠페인이 있는 경우, 터치포인트 종료 날짜를 해당 특정 캠페인에 설정해야 합니다(터치포인트 종료 날짜는 웹 채팅 통합 기능 비트가 활성화된 날짜여야 함).

**Activities를 통해 Drift를 추적하는 경우 어떻게 합니까?**

드리프트 채팅 상호 작용에 대한 터치포인트를 만들기 위한 활동 규칙이 있는 경우, 규칙에 논리를 더 추가해야 합니다. 터치포인트의 중복을 방지하려면 작업 생성 날짜 필드를 사용하여 논리를 추가해야 합니다(예: CrmTask.CreatedDate가 기능 비트가 활성화된 날짜보다 작음). 예를 들어 아래 스크린샷 을 참조하십시오.

![](assets/activity-rule-drift.png)
