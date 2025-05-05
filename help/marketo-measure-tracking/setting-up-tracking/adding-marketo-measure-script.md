---
unique-page-id: 18874795
description: ' [!DNL Marketo Measure] 스크립트 추가 - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] 스크립트 추가 중'
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# [!DNL Marketo Measure] 스크립트 추가 중 {#adding-marketo-measure-script}

[!DNL Marketo Measure]에서 추적할 [!DNL Marketo Measure] JavaScript을 가능한 한 빨리 모든 웹 속성에 추가해야 합니다. JavaScript이 배포되면 [!DNL Marketo Measure]에서 디지털 데이터 수집을 시작합니다. 이 문서에서는 [!DNL Marketo Measure] JavaScript 배포 방법 및 추가 고려 사항에 대해 간략히 설명합니다.

>[!NOTE]
>
>[!DNL Marketo Measure] JavaScript을 배포하는 것 외에도  [!DNL Adobe Admin Console][&#128279;](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"}에서 모든 적절한 도메인을 요청했는지 확인하십시오.

[!DNL Marketo Measure]을(를) 시작할 때 다음 두 가지 방법으로 웹 사이트에 [!DNL Marketo Measure] JavaScript을(를) 추가할 수 있습니다.

* 하드 코딩
* Tag Management 시스템즈

## 하드 코딩 {#hard-coding}

웹 속성에 [!DNL Marketo Measure] JavaScript을 하드코딩하는 것이 좋습니다. 스크립트를 하드코딩하려면 사이트의 모든 페이지에서 `</head>`을(를) 닫기 전에 스크립트를 배치해야 합니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

JavaScript을 페이지의 `<head>`에 하드코딩하면 [!DNL Marketo Measure] 스크립트가 먼저 로드되고 참조 정보가 누락되지 않습니다. [!DNL Marketo Measure] JavaScript이 비동기적으로 로드됩니다. 하드코딩하는 경우 JavaScript을 Marketing Automation에 수동으로 추가해야 합니다.

>[!TIP]
>
>스크립트가 [GDPR 규격](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}인지 확인하는 방법을 알아봅니다.

## Tag Management 시스템즈 {#tag-management-systems}

하드 코딩을 통해 [!DNL Marketo Measure] JavaScript을 추가할 수 없는 경우 다른 옵션은 [!DNL Google Tag Manager] (GTM) 또는 Tealium과 같은 Tag Management 시스템을 사용하여 [!DNL Marketo Measure] 스크립트를 추가하는 것입니다.

태그 관리 시스템을 사용하여 [!DNL Marketo Measure] JS를 배포하면 스크립트 로드 시간 지연으로 인해 5~10%의 데이터 손실이 발생할 수 있습니다. 기본적으로 태그 관리 도구가 빠르게 로드되지 않으면 [!DNL Marketo Measure] JS도 빠르게 로드되지 않고 첫 번째 레퍼러 정보가 손실될 수 있습니다.

일반적인 방법은 타이밍/리소스 코딩이 하드코딩으로 이동하는 것이 나을 때까지 태그 관리 도구를 통해 [!DNL Marketo Measure] JS를 배포하는 것입니다.

태그 관리 솔루션을 통해 [!DNL Marketo Measure] 스크립트를 추가하려면 태그를 만들고 그 안에 JavaScript을 추가해야 합니다. 이 태그를 추적하려는 웹 사이트의 모든 페이지에 적용합니다.

[!DNL Marketo Measure]은(는) 페이지 보기에서 태그가 실행되도록 하는 것을 권장합니다. 또한 실행 순서에서 [!DNL Marketo Measure]에 가장 높은 우선 순위를 부여하고 [!DNL Marketo Measure] 태그 앞에 동기 스크립트가 없는지 확인하는 것이 가장 좋은 데이터 품질을 보장합니다.

자세한 정보는 [여기에서 찾을 수 있음](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## 추가 고려 사항 {#additional-considerations}

[!DNL Marketo Measure] JavaScript은 도메인을 기반으로 하므로 JavaScript이 페이지에 있고 루트 도메인이 Marketo Measure 계정을 만드는 데 사용된 도메인과 동일한 경우 자동으로 모든 하위 도메인을 처리할 수 있습니다.

그러나 별도의 도메인이나 국제 도메인을 사용하는 경우 [!DNL Marketo Measure] 컨설턴트에게 알리십시오. [!DNL Marketo Measure]이(가) 추가 도메인의 데이터를 계정에 연결할 것을 알 수 있도록 [!DNL Marketo Measure] 끝에서 도메인을 계정에 수동으로 추가해야 합니다. 따라서 별도의/국제 도메인을 [!DNL Marketo Measure] 컨설턴트에게 보내십시오.

서드파티 페이지를 사용하는 경우 [!DNL Marketo Measure] 컨설턴트와 사용 사례에 대해 대화합니다. 일반적으로 필요한 경우 [!DNL Marketo Measure] JavaScript의 사용자 지정 버전을 추가하여 해당 페이지를 추적할 수 있는지 알고 싶을 수 있습니다. 가능하지 않은 경우 CRM Campaign 터치포인트를 통한 추적은 [!DNL Marketo Measure] 컨설턴트와 함께 탐색됩니다.

[!DNL Marketo Measure]이(가) 기여도 분석에 적합하지 않으므로 추적하지 말아야 할 양식이 있습니까? 등록 취소 양식, 고객 로그인 등 이 경우 이 문서[&#128279;](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"}의 제외 코드 을(를) 각 양식에 추가합니다.

비보안 페이지가 있습니까? 보안/비보안 페이지 간을 탐색하면 추적 세션이 중단되므로 이 둘을 보호해야 합니다.

[!DNL Marketo Measure] JavaScript이 항상 적절한 웹 속성에 있어야 한다는 것을 알 수 있도록 웹 팀과 대화해 보십시오. 새 페이지/양식/사이트가 도입된 경우 [!DNL Marketo Measure] JavaScript 배포가 프로토콜의 일부인지 확인하십시오.

JavaScript 설정 중에 [!DNL Web Application Firewall (WAF)] 경고가 트리거되면 사용자는 아래 예와 같이 해당 WAF 규칙을 비활성화하거나 쿠키를 허용 목록 할 수 있습니다.

![](assets/adding-marketo-measure-script-1.png)

## Forms에 각별한 주의 기울이기 {#forms-to-pay-extra-attention-to}

**다중 양식 제출**

* 문제: 단일 양식 제출의 일부로 연결된 양식이 여러 개 있는 경우 전체 양식이 제출되지 않은 경우에도 첫 번째 양식에서 터치포인트를 생성할 수 있습니다.
* 해결 방법: 캐시된 데이터를 기반으로 양식 중 하나가 [!DNL Marketo Measure]에게 사용자를 보고하고 포기 방법을 논의하도록 해야 합니다. 일반적으로 [사용자 코드 보고](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}를 통해 해결할 수 있습니다.

**계정 로그인(생성되지 않음)**

* 문제: [!DNL Marketo Measure]에서는 속성 스토리가 희석되는 경향이 있으므로 후속 계정 로그인에 대한 터치포인트를 만들지 않는 것이 좋습니다.
* 해결 방법: 계정/고객/파트너 로그인 양식에 제외 코드를 추가합니다.

>[!NOTE]
>
>계정 또는 체험판을 만들려면 터치포인트를 만드는 것이 좋습니다.

**자산 다운로드**

* 문제: 자산이 게이팅되면 [!DNL Marketo Measure]에서 양식 채우기로 다운로드를 추적합니다. 자산이 제어되지 않는 경우 사용자 지정 없이 보고할 수 있는 내용에 제한이 있습니다.
* 해결 방법: 에셋을 [!DNL Marketo Measure] JavaScript에서 추적하려면 해당 에셋을 게이트하십시오. 옵션이 아니고 터치포인트를 계속 사용하려는 경우 CRM Campaign 동기화를 대신 고려해 보십시오.

**iFrames**

* 문제: iFrame은 기본적으로 페이지 내에서 페이지로 작동합니다.
* 해결 방법: 양식에 올바르게 연결하려면 iFrame 헤더 내에 [!DNL Marketo Measure] JS를 직접 배포해야 합니다.

**Lightbox**

* Lightbox는 일반적으로 iFrame을 포함하는 팝업입니다
* 해결 방법: [!DNL Marketo Measure] JS는 호스팅된 해당 iFrame의 헤더 내에 배포되어야 합니다.

**페이지에 있는 여러 양식**

* 문제: 페이지에 여러 개의 양식이 호스팅되어 있는 경우 [!DNL Marketo Measure] 양식 URL 필드로 채워진 특정 양식을 구분하지 못할 수 있습니다.
* 해결 방법: 작성된 양식을 알고 있어야 하는 경우 웹 팀과 동적 URL 해시 설정을 살펴보십시오.

**Forms을 `<div>` 형식으로 구성**

* 문제: [!DNL Marketo Measure] JS는 `<div>` 형식으로 구성된 양식을 인식하기 어려우므로 사용자 지정 코드가 필요할 수 있습니다.
* 해결 방법: 웹 개발 팀에서 이러한 [보고서 사용자 템플릿](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}을(를) 사용하여 필요한 코드를 추가할 수 있습니다.

**채팅**

* 문제: 채팅 공급자를 사용하는 경우 특별한 처리가 필요할 수 있습니다.
* 해결 방법: [!DNL Marketo Measure]은(는) Drift, Olark, Livechat, LivePerson 및 SnapEngage와 통합됩니다. 다른 모든 플랫폼은 CRM 캠페인 멤버십을 통해 추적해야 합니다.

**두 번째 도메인**

* 문제: [!DNL Marketo Measure] JavaScript은 도메인별 문제이므로 별도의 또는 국제 도메인에 대해 추가 단계를 수행해야 합니다. [!DNL Marketo Measure] JS는 동일한 루트 도메인에서 하위 도메인을 처리할 수 있습니다.
* 해결 방법: 루트 도메인이 여러 개 있는 경우 [!DNL Marketo Measure]에서 추적하려면 도메인에 JS를 추가하고 [!DNL Marketo Measure] 컨설턴트에게 [!DNL Marketo Measure] 계정에 수동으로 연결해야 하는 도메인을 알려 주십시오.

## [!DNL Marketo Measure] JavaScript 테스트 중 {#testing-marketo-measure-javascript}

[!DNL Marketo Measure] 컨설턴트가 웹 사이트를 스팟 테스트하여 모든 페이지에 [!DNL Marketo Measure] JavaScript이 있는지 확인하는 데 도움을 줍니다. 이 테스트의 일부는 추적이 제대로 반환되는지 확인하기 위해 명확하게 표시된 테스트 세부 사항으로 몇 가지 양식 채우기를 제출하는 것입니다.

그러나 [!DNL Marketo Measure] 컨설턴트가 웹 팀만큼 웹 사이트를 잘 알지 못할 수 있습니다. 따라서 웹 팀이나 다른 적절한 팀이 웹 사이트를 철저히 확인하는 것이 매우 중요합니다. 특히 위에 언급된 것과 같이 사용 중인 복잡한 양식이 있는 경우. 필요한 모든 웹 속성을 올바르게 추적할 수 있도록 귀하의 팀이 궁극적으로 책임을 지지만, 복잡한 양식이나 상황을 알고 있는 경우 [!DNL Marketo Measure] 컨설턴트에게 테스트 지원을 요청할 수 있습니다.

양식을 직접 테스트하려면 다음 단계를 수행합니다.

1. 항상 시크릿 브라우저를 사용하거나 각 양식 제출 테스트 간에 캐시를 지우고 매번 다른 이메일 주소를 사용하십시오.

   a. 가장 좋은 방법은 테스트임을 나타내는 것과 하루 중 시간대를 포함하는 가짜 이메일을 사용하는 것입니다. 예: testing830am@test.com.

1. 양식을 제출하는 페이지의 URL과 사용한 이메일을 기록합니다.

1. 해당 양식 제출을 위해 CRM(리드 또는 연락처)에서 만든 레코드를 찾아 터치포인트가 적절하게 생성되었는지 확인합니다.

   a. 구매자 터치포인트가 있는 리드와 같은 [!DNL Marketo Measure] 스톡 보고서를 사용하거나 [!DNL Marketo Measure] 세부 정보로 페이지 레이아웃을 업데이트하도록 선택한 경우 리드/연락처 페이지 레이아웃을 볼 수 있습니다.

   b. 데이터를 처리하는 데 시간이 걸릴 수 있습니다.
