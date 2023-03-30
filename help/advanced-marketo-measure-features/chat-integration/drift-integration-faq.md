---
unique-page-id: 27656441
description: 드리프트 통합 FAQ - [!DNL Marketo Measure] - 제품 설명서
title: 드리프트 통합 FAQ
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# 드리프트 통합 FAQ {#drift-integration-faq}

의 일부로 [!DNL Marketo Measure] Lift와의 통합을 통해 가장 자주 묻는 질문 중 몇 가지를 간략하게 설명했습니다. 아래에 요약되지 않은 질문이 있는 경우 Adobe 계정 팀(계정 관리자)에 문의하거나 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**통합은 어떻게 활성화됩니까?**

채트 추적 대상 [!DNL Marketo Measure] 이 기본적으로 활성화되어 있습니다. 어떤 이유로든 이를 비활성화하고(기본적으로 이동 채팅에서 터치포인트를 만들지 않으려는 경우), 사용자 [!DNL Marketo Measure] Javascript 구현은 아래에 굵게 표시되어 있습니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

를 사용하는 사용자 [!DNL Google Tag Manager] 를 로드하려면 [!DNL Marketo Measure] 스크립트, Tr프트 채팅을 터치 포인트 자격이 없는 상태에서 제외하려면 다음에 추가해야 합니다 `<span>` 바로 [!DNL Marketo Measure] 스크립트:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**통합에서 수행하는 작업**

이제 통합이 가능합니다 [!DNL Marketo Measure] 최종 사용자가 드리프트 채팅에서 자신의 이메일 주소를 제공하는 시기를 추적합니다. 거기에서 터치포인트 유형의 &quot;웹 채팅&quot;을 사용하여 이러한 상호 작용으로 터치포인트를 만듭니다. 이 통합을 통해 마케터는 이러한 채팅과 상호 작용하도록 유도하는 채널/하위 채널/캠페인과 함께 채팅 상호 작용의 성과를 이해할 수 있습니다.

**Campaign 동기화 규칙을 통해 드리브를 추적하는 경우 어떻게 합니까?**

드리프트 채팅 상호 작용을 위한 터치포인트를 만들기 위해 캠페인 동기화 규칙이 적용되는 경우 해당 CRM 캠페인에 해당 최종 사용자를 추가하지 않도록 해야 합니다. 그렇지 않으면 기능 비트가 활성화되면 하나의 드리프트 채팅 상호 작용에 대한 CRM Campaign 터치포인트 및 디지털 터치포인트를 만듭니다.

**CRM 캠페인을 통해 드리브를 추적하면 어떻게 됩니까?**

Tr프트 채팅 상호 작용을 위한 터치포인트를 만들기 위한 CRM 캠페인이 있는 경우, 터치 포인트 종료 날짜를 해당 특정 캠페인에서 설정해야 합니다(터치 포인트 종료 날짜는 웹 채팅 통합 기능 비트가 활성화된 날짜여야 함).

**활동을 통해 이동을 추적하면 어떻게 합니까?**

드리프트 채팅 상호 작용을 위한 터치포인트를 만들기 위한 활동 규칙이 적용되는 경우 규칙에 추가 로직 조각을 추가해야 합니다. 터치 포인트의 중복을 방지하기 위해 작업 생성 날짜 필드를 사용하여 논리를 추가해야 합니다(IE CrmTask.CreatedDate는 기능 비트가 활성화된 날짜보다 작음). 예를 들어 아래 스크린샷을 참조하십시오.

![](assets/activity-rule-drift.png)
