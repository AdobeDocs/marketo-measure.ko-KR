---
description: API 연결 모범 사례 - [!DNL Marketo Measure]
title: API 연결 우수 사례
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 0%

---

# API 연결 우수 사례 {#best-practices-for-api-connections}

## 개요 {#overview}

[!DNL Marketo Measure]에서 [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads] 및 LinkedIn에 API 연결을 제공합니다. 이러한 API 연결을 통해 [!DNL Marketo Measure]은(는) 광고 플랫폼에서 다양한 데이터를 가져와서 Buyer Touchpoint 데이터에 보고할 수 있습니다. 이러한 API 연결의 주요 기능은 지출 데이터를 자동으로 가져와서 사용자와 팀이 ROI 보고를 위해 데이터를 수동으로 업로드하는 데 소요되는 시간과 노력을 절약하는 것입니다. [!DNL Marketo Measure]이(가) 이러한 채널을 추적하는 데 이러한 API 연결을 설정해야 하는 것은 아니지만, 보고를 개선하는 중요한 세부 정보를 제공합니다.

[!DNL Marketo Measure] API 연결은 귀하 계정의 중요한 측면이며 모범 사례 권장 사항은 귀하와 귀하의 팀이 당사의 연결을 최대한 활용하는 데 도움이 됩니다.

## 우수 사례 {#best-practice}

연결하는 광고 플랫폼에 관계없이 다음 지침을 염두에 두어야 합니다.

* 관리자를 사용하여 연결
* 하나의 플랫폼에 대해 여러 광고 계정을 연결할 수 있습니다.
* 가능한 모든 광고 계정을 연결하여 지출 보고를 최대한 자동화합니다
* 사용 가능한 경우 항상 추적 템플릿을 구현합니다. 템플릿은 광고 계정 연결이 끊어지더라도 [!DNL Marketo Measure]에서 세분화된 광고 세부 정보를 가져올 수 있도록 합니다

각 [!DNL Marketo Measure] API를 최적화하려면 다음 모범 사례를 준수하십시오.

**[!DNL Facebook]**: 자동 태깅으로 연결

자동 태그 지정을 활성화하기 전에 광고 내역을 csv로 내보냅니다. 자동 태그 지정을 활성화하면 [!DNL Marketo Measure]에서 태그 지정한 모든 광고의 전환 기록 및 소셜 증명이 재설정됩니다.

모범 사례 권장 사항에 따라 [!DNL Marketo Measure] [!DNL Facebook] API는 다음을 수행할 수 있습니다.

* 필요한 [!DNL Marketo Measure] 매개 변수 `_bf ={creative}`을(를) 사용하여 모든 [!DNL Facebook] 광고에 자동 태그 지정
* 모든 활성 [!DNL Facebook] 광고에서 광고 비용 정보 다운로드

>[!NOTE]
>
>[!DNL Facebook]에 대한 추적 템플릿이 없습니다. API는 자동 태그 지정(_bf) 매개 변수를 사용하여 광고 세부 정보를 수집합니다.

**AdWords**: 계정 수준에서 추적 템플릿을 구현하고 자동 태그 지정을 사용하도록 설정합니다.

[!DNL Marketo Measure]에서는 모든 광고에 대해 광고 기록이 중단되거나 삭제될 위험 없이 매개 변수를 추가하거나 뺄 수 있으므로 계정 수준, 캠페인 수준 또는 광고 그룹 수준 추적 템플릿을 사용하는 것이 좋습니다.

모범 사례 권장 사항에 따라 [!DNL Marketo Measure] AdWords API는 다음을 수행할 수 있습니다.

* `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`의 [!DNL Marketo Measure] 매개 변수로 모든 AdWords 광고에 자동 태그 지정
* 모든 활성 AdWords 광고에 대한 광고 비용 정보 다운로드

**Bing**: 계정 수준에서 추적 템플릿을 구현하고 자동 태그 지정을 사용하도록 설정합니다.

[!DNL Bing] API 연결을 설정할 때 다른 API 연결과 달리 광고 기록이 손실될 위험이 없습니다.

모범 사례 권장 사항에 따라 [!DNL Marketo Measure] Bing API는 다음을 수행할 수 있습니다.
* `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`의 다음 매개 변수로 모든 Bing 광고에 자동 태그 지정
* 모든 활성 Bing 광고의 광고 비용 정보 다운로드

**LinkedIn**: 자동 태깅으로 연결

자동 태깅을 활성화하면 공유가 다시 생성되어 새 크리에이티브에 배치되고 이전 크리에이티브가 보관됩니다.

모범 사례 권장 사항에 따라 [!DNL Marketo Measure] LinkedIn API는 다음을 수행할 수 있습니다.

* 필요한 [!DNL Marketo Measure] 매개 변수 _bl={creativeId}을(를) 사용하여 광고 유형 스폰서 콘텐츠인 모든 LinkedIn 광고에 자동 태그를 지정합니다. 이 매개 변수는 [!DNL Marketo Measure]에서 캠페인 및 광고 정보를 확인할 수 있도록 Creative ID를 가져옵니다.
* 모든 활성 광고 및 지원되는 [!DNL LinkedIn]개 광고에서 광고 비용 정보 다운로드

>[!NOTE]
>
>[!DNL LinkedIn]에 대한 추적 템플릿이 없습니다. API는 자동 태그 지정(_bl) 매개 변수를 사용하여 가능한 모든 광고 세부 정보를 수집합니다.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

모범 사례를 따르면 연결이 끊어진 경우 데이터가 손실되지 않도록 보호하지만, 가능하면 정기적으로 월별 연결을 검토하는 것이 좋습니다. 이는 [!DNL Marketo Measure] 앱의 [!UICONTROL Connections] 섹션을 간단하게 시각적으로 확인하여 연결이 끊어진 계정에 표시하며 빨간색 키 아이콘이 없는지 확인합니다.

API 연결 계정의 연결이 끊어진 경우 [!DNL Marketo Measure]에서 지출 데이터를 가져오거나 새 광고에 태그를 지정할 수 없습니다. 가능한 경우 항상 추적 템플릿을 구현하는 것이 좋습니다. 템플릿은 광고 계정 연결이 끊어지더라도 [!DNL Marketo Measure]이(가) 광고에 태그를 지정하고 세분화된 광고 세부 정보를 가져올 수 있도록 합니다. 다시 연결되면 지출 데이터가 다시 채워지고 유료 채널 보고에 미치는 영향이 최소화됩니다.

단절 및 재허가의 이유는 다음과 같습니다.

* 연결된 개인 계정에 대한 암호 변경
* 그 사람은 더 이상 회사에 있지 않습니다
* API 업데이트

팀에서 위의 시나리오를 경험한 경우 [!DNL Marketo Measure] 앱에서 API 연결을 확인하여 다시 인증할 필요가 없는지 확인하십시오.

>[!MORELIKETHIS]
>
>* [통합 광고 플랫폼(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [입찰 관리 도구의 영향 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API 매개 변수 설명](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API 개요](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [연결된 API 계정 다시 인증](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
