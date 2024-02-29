---
description: API 연결 우수 사례 - [!DNL Marketo Measure]
title: API 연결 우수 사례
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# API 연결 우수 사례 {#best-practices-for-api-connections}

## 개요 {#overview}

[!DNL Marketo Measure] 에서 API 연결 제공 [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]및 LinkedIn에 전송됩니다. 이러한 API 연결을 통해 [!DNL Marketo Measure] 광고 플랫폼에서 다양한 데이터를 가져와서 구매자 터치포인트 데이터에 보고할 수 있습니다. 이러한 API 연결의 주요 기능은 지출 데이터를 자동으로 가져와서 사용자와 팀이 ROI 보고를 위해 데이터를 수동으로 업로드하는 데 소요되는 시간과 노력을 절약하는 것입니다. 이러한 API 연결은 다음에 대해 필수가 아닙니다. [!DNL Marketo Measure] 이러한 채널을 추적하지만, 보고를 향상시키는 중요한 세부 정보를 제공합니다.

다음 [!DNL Marketo Measure] API 연결은 귀하의 계정에서 매우 중요한 측면이며 모범 사례 권장 사항은 귀하와 귀하의 팀이 당사의 연결을 최대한 활용하는 데 도움이 될 것입니다.

## 우수 사례 {#best-practice}

연결하는 광고 플랫폼에 관계없이 다음 지침을 염두에 두어야 합니다.

* 관리자를 사용하여 연결
* 하나의 플랫폼에 대해 여러 광고 계정을 연결할 수 있습니다.
* 가능한 모든 광고 계정을 연결하여 지출 보고를 최대한 자동화합니다
* 사용 가능한 경우 항상 추적 템플릿을 구현합니다. 템플릿은 광고 계정의 연결이 끊어진 경우에도 [!DNL Marketo Measure] 세분화된 광고 세부 정보를 가져올 수 있음

각각 최적화하려면 [!DNL Marketo Measure] API에서 다음 모범 사례를 따릅니다.

**[!DNL Facebook]**: 자동 태깅으로 연결

자동 태그 지정을 활성화하기 전에 광고 내역을 csv로 내보냅니다. 자동 태그 지정을 활성화하면 태그 지정된 모든 광고의 전환 내역과 소셜 증명이 재설정됩니다. [!DNL Marketo Measure].

모범 사례 권장 사항을 따르면 [!DNL Marketo Measure] [!DNL Facebook] API는 다음을 수행할 수 있습니다.

* 모두 자동 태그 지정 [!DNL Facebook] 필요한 광고 [!DNL Marketo Measure] 매개 변수 `_bf ={creative}`
* 모든 활성 항목에 대한 광고 비용 정보 다운로드 [!DNL Facebook] 광고

>[!NOTE]
>
>에 대한 추적 템플릿이 없습니다. [!DNL Facebook], API는 자동 태그 지정(_bf) 매개 변수를 사용하여 광고 세부 정보를 수집합니다.

**애드워즈**: 계정 수준에서 추적 템플릿을 구현하고 자동 태깅 활성화

[!DNL Marketo Measure] 는 광고 기록이 중단되거나 삭제될 위험 없이 모든 광고에 대한 매개 변수를 추가하거나 뺄 수 있으므로 계정 수준, 캠페인 수준 또는 광고 그룹 수준 추적 템플릿을 사용할 것을 권장합니다.

모범 사례 권장 사항을 따르면 [!DNL Marketo Measure] AdWords API는 다음을 수행할 수 있습니다.

* 를 사용하여 모든 AdWords 광고에 자동 태그 지정 [!DNL Marketo Measure] 매개 변수 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 모든 활성 AdWords 광고에 대한 광고 비용 정보 다운로드

**빙**: 계정 수준에서 추적 템플릿을 구현하고 자동 태깅 활성화

을(를) 설정할 때 광고 기록이 손실될 위험이 없습니다. [!DNL Bing] 다른 API 연결과 달리 API 연결입니다.

모범 사례 권장 사항을 따르면 [!DNL Marketo Measure] Bing API는 다음을 수행할 수 있습니다.
* 다음 매개 변수를 사용하여 모든 Bing 광고에 자동 태그 지정 `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 모든 활성 Bing 광고의 광고 비용 정보 다운로드

**LinkedIn**: 자동 태깅으로 연결

자동 태깅을 활성화하면 공유가 다시 생성되어 새 크리에이티브에 배치되고 이전 크리에이티브가 보관됩니다.

모범 사례 권장 사항을 따르면 [!DNL Marketo Measure] LinkedIn API는 다음 작업을 수행할 수 있습니다.

* 필요한 경우 광고 유형 스폰서 콘텐츠인 모든 LinkedIn 광고에 자동 태그 지정 [!DNL Marketo Measure] 매개 변수 _bl={creativeId}. 이 매개 변수는 크리에이티브 ID를 가져오며 [!DNL Marketo Measure] 를 클릭하여 캠페인 및 크리에이티브 정보를 해결합니다.
* 모든 활성 및 지원되는 항목에 대한 광고 비용 정보 다운로드 [!DNL LinkedIn] 광고

>[!NOTE]
>
>에 대한 추적 템플릿이 없습니다. [!DNL LinkedIn], API는 자동 태그 지정(_bl) 매개 변수를 사용하여 가능한 모든 광고 세부 정보를 수집합니다.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

모범 사례를 따르면 연결이 끊어진 경우 데이터가 손실되지 않도록 보호하지만, 가능하면 정기적으로 월별 연결을 검토하는 것이 좋습니다. 이는 의 간단한 시각적 검사입니다. [!UICONTROL Connections] 의 섹션 [!DNL Marketo Measure] 앱에서 빨간색 키 아이콘이 없는지 확인하여 연결이 끊긴 계정에 신호를 보냅니다.

API 연결 계정의 연결이 끊기면 [!DNL Marketo Measure] 에서 지출 데이터를 가져오거나 새 광고에 태그를 지정할 수 없습니다. 가능한 경우 항상 추적 템플릿을 구현하는 것이 좋습니다. 템플릿은 광고 계정의 연결이 끊어진 경우에도 [!DNL Marketo Measure] 는 여전히 광고에 태그를 지정하고 세분화된 광고 세부 정보를 가져올 수 있습니다. 다시 연결되면 지출 데이터가 다시 채워지고 유료 채널 보고에 미치는 영향이 최소화됩니다.

단절 및 재허가의 이유는 다음과 같습니다.

* 연결된 개인 계정에 대한 암호 변경
* 그 사람은 더 이상 회사에 있지 않습니다
* API 업데이트

팀이 위의 시나리오 중 하나를 경험한 경우,에서 API 연결을 확인하십시오. [!DNL Marketo Measure] 다시 인증할 필요가 없는지 확인하기 위한 앱.

>[!MORELIKETHIS]
>
>* [통합 광고 플랫폼(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [입찰 관리 도구의 영향 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API 매개 변수 설명](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API 개요](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [연결된 API 계정 다시 인증](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
