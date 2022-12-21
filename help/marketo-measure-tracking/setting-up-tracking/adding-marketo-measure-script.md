---
unique-page-id: 18874795
description: 추가 중 [!DNL Marketo Measure] 스크립트 - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] 스크립트
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 스크립트 {#adding-marketo-measure-script}

[!DNL Marketo Measure] 추적하려는 JavaScript [!DNL Marketo Measure] 는 가능한 한 빨리 모든 웹 속성에 추가해야 합니다. JavaScript가 배포되면, [!DNL Marketo Measure] 에서 디지털 데이터 수집을 시작합니다. 이 문서에서는 배포 방법을 간략하게 설명합니다 [!DNL Marketo Measure] JavaScript 및 고려해야 할 추가 고려 사항입니다.

>[!NOTE]
>
>확실히 [에서 모든 적절한 도메인이 요청됨 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md)배포 외에 {target=&quot;_blank&quot;} [!DNL Marketo Measure] JavaScript.

시작 시 [!DNL Marketo Measure]를 추가할 수 있는 방법에는 두 가지가 있습니다 [!DNL Marketo Measure] 웹 사이트에 JavaScript 추가:

* 하드 코딩
* Tag Management 시스템

## 하드 코딩 {#hard-coding}

가장 좋은 방법은 하드 코딩을 강력히 권장하는 것입니다 [!DNL Marketo Measure] 웹 속성에 JavaScript를 추가합니다. 스크립트를 하드코딩하려면 닫기 전에 스크립트를 배치해야 합니다 `</head>` 클릭합니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

JavaScript를 `<head>` 이 경우 [!DNL Marketo Measure] 스크립트가 먼저 로드되고 참조 정보가 누락되지 않습니다. 다음 [!DNL Marketo Measure] JavaScript는 비동기식으로 로드됩니다. 하드코딩하는 경우, JavaScript를 수동으로 Marketing Automation에 추가해야 합니다.

>[!TIP]
>
>스크립트가 [GDPR 준수](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target=&quot;_blank&quot;}.

## Tag Management 시스템 {#tag-management-systems}

추가할 경우 [!DNL Marketo Measure] 하드 코딩을 통한 JavaScript는 가능하지 않으며 다른 옵션은 [!DNL Marketo Measure] 와 같은 Tag Management 시스템을 사용한 스크립트 [!DNL Google Tag Manager] (GTM) 또는 Tealium.

태그 관리 시스템을 사용하여 을 배포하십시오 [!DNL Marketo Measure] JS는 스크립트 로드 시간 지연으로 인해 5~10%의 데이터 손실을 초래할 수 있습니다. 기본적으로 태그 관리 도구가 충분히 빠르게 로드되지 않으면, [!DNL Marketo Measure] 또한 JS는 충분히 빠르게 로드할 수 없으며 첫 번째 레퍼러 정보를 잃을 수 있습니다.

일반적인 방법은 를 배포하는 것입니다 [!DNL Marketo Measure] 타이밍/리소스가 하드코딩으로 이동하는 것이 더 좋을 때까지 태그 관리 도구를 통해 JS를 사용하십시오.

추가하려면 [!DNL Marketo Measure] 태그 관리 솔루션을 통해 스크립트를 작성하는 경우 새 태그를 만들고 태그 내에 JavaScript를 추가해야 합니다. 이 태그를 추적하려는 웹 사이트의 모든 페이지에 적용합니다.

[!DNL Marketo Measure] 는 모든 페이지 보기에서 태그가 실행되도록 합니다. 게다가, [!DNL Marketo Measure] 실행 순서에서 가장 높은 우선 순위를 가지며 앞에 동기 스크립트가 없는지 확인합니다. [!DNL Marketo Measure] 태그에 가깝게 포함했습니다.

추가 정보는 [여기에서](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target=&quot;_blank&quot;}.

## 추가 고려 사항 {#additional-considerations}

[!DNL Marketo Measure] JavaScript는 도메인 기반이므로, 페이지에 JavaScript가 있고 루트 도메인이 Marketo Measure 계정을 만드는 데 사용되는 도메인과 동일한 한 모든 하위 도메인을 자동으로 처리할 수 있습니다.

그러나 별도의 도메인 또는 국제 도메인을 사용하는 경우에는 [!DNL Marketo Measure] 컨설턴트가 알아요 도메인은 을 의 계정에 수동으로 추가해야 합니다 [!DNL Marketo Measure] 그렇게 [!DNL Marketo Measure] 은 추가 도메인의 데이터를 계정에 연결하는지 확인합니다. 따라서 별도의/국제 도메인을 귀하의 [!DNL Marketo Measure] 컨설턴트.

타사 페이지를 사용하는 경우, 사용 사례에 대해 사용자의 [!DNL Marketo Measure] 컨설턴트. 일반적으로 의 사용자 지정 버전을 추가할 수 있는지 확인해야 합니다 [!DNL Marketo Measure] JavaScript 를 사용하여 적절한 경우 해당 페이지를 추적합니다. 불가능한 경우 CRM Campaign 터치포인트를 통한 추적이 와 함께 탐색됩니다 [!DNL Marketo Measure] 컨설턴트.

추적해서는 안 되는 양식이 있습니까? [!DNL Marketo Measure] 이는 기여도 분석에 적합하지 않으므로(예: 양식 가입 해지, 고객 로그인 등) 그럴 경우 제외 코드를 추가할 수 있습니다 [이 문서](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md)각 양식에 대한 {target=&quot;_blank&quot;}

비보안 페이지가 있습니까? 그런 경우 보안/비보안 페이지 간을 탐색하면 추적 세션이 중단되므로 이러한 쿠키를 보호해야 합니다.

웹 팀이 알 수 있도록 꼭 연락하세요 [!DNL Marketo Measure] JavaScript는 항상 적절한 웹 속성에 있어야 합니다. 새 페이지/양식/사이트가 도입되면 배포를 확인해야 합니다 [!DNL Marketo Measure] JavaScript는 프로토콜의 일부입니다.

다음과 같은 경우 [!DNL Web Application Firewall (WAF)] 경고는 JavaScript 설정 중에 트리거되며 사용자는 아래 예와 같이 해당 WAF 규칙을 비활성화하거나 쿠키를 허용 목록에 추가할 수 있습니다.

![](assets/adding-marketo-measure-script-1.png)

## Forms이 특별히 주의를 기울이기 {#forms-to-pay-extra-attention-to}

**다중 양식 제출**

* 문제: 단일 양식 제출의 일부로 연결된 양식이 여러 개 있는 경우 전체 양식이 제출되지 않더라도 첫 번째 양식이 터치 포인트를 생성할 수 있습니다.
* 솔루션: 양식 중 하나를 강제로 사용자에게 보고해야 합니다 [!DNL Marketo Measure] 캐시된 데이터를 기반으로 중단 사례에 대해 설명합니다. 일반적으로 [보고서 사용자 코드](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;}에서 이 문제를 해결할 수 있습니다.

**계정 로그인(생성 아님)**

* 문제: [!DNL Marketo Measure] 은 속성 스토리를 희석하는 경향이 있으므로 후속 계정 로그인에 대한 터치포인트를 만들지 않는 것을 권장합니다.
* 솔루션: 계정/고객/파트너 로그인 양식에 제외 코드를 추가합니다.

>[!NOTE]
>
>계정 또는 평가판을 만들 터치포인트를 만드는 것이 좋습니다.

**자산 다운로드**

* 문제: 만약 당신의 자산이 통제된다면, [!DNL Marketo Measure] 은 양식 입력으로 다운로드를 추적합니다. 자산이 제한되지 않으면 사용자 지정 없이 보고할 수 있는 항목에 제한이 있습니다.
* 솔루션: 자산을 추적하려면 게이트를 수행하십시오. [!DNL Marketo Measure] JavaScript. 이 옵션이 선택되어 있지 않고 터치포인트를 계속 사용하려면 CRM 캠페인 동기화를 대신 고려해 보십시오.

**iFrames**

* 문제: 프레임은 기본적으로 페이지 내에서 페이지로 작동합니다.
* 솔루션: 다음 [!DNL Marketo Measure] 양식에 올바르게 첨부하려면 iFrame 헤더 내에 JS를 직접 배포해야 합니다.

**Lightbox**

* Lightbox는 일반적으로 iFrame을 포함하는 팝업입니다
* 솔루션: a [!DNL Marketo Measure] JS는 호스팅된 iFrame의 헤더 내에 배포해야 합니다.

**한 페이지의 여러 양식**

* 문제: 한 페이지에 여러 개의 양식이 호스팅되어 있는 경우 양식마다 [!DNL Marketo Measure] 양식 URL 필드.
* 솔루션: 어떤 양식이 입력되었는지 알고 있어야 하는 경우에는 웹 팀과 함께 동적 URL 해싱 설정을 살펴보십시오.

**Forms 구성 `<div>` 포맷**

* 문제: [!DNL Marketo Measure] JS에서는 `<div>` 형식을 지정하여 사용자 지정 코드가 필요할 수 있습니다.
* 솔루션: 다음 [보고서 사용자 템플릿](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md)웹 개발 팀에서 {target=&quot;_blank&quot;} 코드를 사용하여 필요한 코드를 추가할 수 있습니다.

**채팅**

* 문제: 채팅 공급자를 사용하는 경우 특수 처리가 필요할 수 있습니다.
* 솔루션: [!DNL Marketo Measure] Lift, Olark, Livechat, LivePerson 및 SnapEngage와 통합됩니다. 다른 모든 플랫폼은 CRM 캠페인 멤버십을 통해 추적해야 합니다.

**두 번째 도메인**

* 문제: [!DNL Marketo Measure] JavaScript는 도메인별로 다르므로 별도의 도메인 또는 국제 도메인에 대해 추가 단계를 수행해야 합니다. 참고 사항 [!DNL Marketo Measure] JS는 동일한 루트 도메인에서 하위 도메인을 처리할 수 있습니다.
* 솔루션: 여러 루트 도메인을 소유하고 있는 경우에서 추적하려는 경우 [!DNL Marketo Measure] 는 반드시 도메인에 JS를 추가하고 [!DNL Marketo Measure] 컨설턴트는 사용자와 수동으로 연결해야 하는 도메인을 알고 있습니다 [!DNL Marketo Measure] 계정이 필요합니다.

## 테스트 [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

사용자 [!DNL Marketo Measure] 컨설턴트는 웹 사이트를 테스트하여 해당 웹 사이트를 확인할 수 있도록 지원합니다 [!DNL Marketo Measure] JavaScript가 모든 페이지에 있습니다. 이 테스트의 일부에는 추적이 제대로 반환되도록 명확하게 표시된 테스트 세부 사항이 포함된 몇 가지 양식 채우기가 제출됩니다.

그러나, [!DNL Marketo Measure] 컨설턴트는 웹 팀만큼 웹 사이트에 익숙하지 않을 수 있습니다. 이러한 이유로, 웹 팀이나 다른 적절한 팀이 위에 언급된 것과 같이 복잡한 양식이 있는 경우 특히 웹 사이트를 철저히 확인하는 것이 중요합니다. 팀은 궁극적으로 필요한 모든 웹 속성이 제대로 추적되도록 해야 하지만, 복잡한 양식이나 상황을 알고 있는 경우 [!DNL Marketo Measure] 테스트에 대한 도움이 필요한 컨설턴트입니다.

양식을 직접 테스트하려면 다음 단계를 수행하십시오.

1. 항상 시크릿 브라우저를 사용하거나 각 양식 제출 테스트 간에 캐시를 지웁니다. 매번 다른 이메일 주소를 사용하십시오.

   a. 가장 좋은 방법은 테스트라는 것을 나타내는 내용이 포함된 가짜 이메일을 사용하는 것입니다. 예: testing830am@test.com

1. 양식을 제출하는 페이지의 URL과 사용된 이메일을 기록합니다.

1. CRM에서 만든 레코드(리드 또는 연락처)를 찾아 해당 양식 제출을 위해 터치포인트를 적절히 만들었는지 확인합니다.

   a. 을(를) 사용할 수 있습니다 [!DNL Marketo Measure] 구매자 터치포인트가 있는 리드와 같은 스톡 보고서를 보거나, 페이지 레이아웃을 업데이트하도록 선택한 경우 리드/연락처 페이지 레이아웃을 확인합니다. [!DNL Marketo Measure] 세부 사항.

   나. 이 작업은 데이터가 처리되는 데 시간이 걸릴 수 있습니다.
