---
description: API 연결에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: API 연결에 대한 우수 사례
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 0%

---

# API 연결에 대한 우수 사례 {#best-practices-for-api-connections}

## 개요 {#overview}

[!DNL Marketo Measure] 에서는 API 연결을 제공합니다 [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads], 및 LinkedIn . 이러한 API 연결은 [!DNL Marketo Measure] 를 입력하여 Buyer Touchpoint 데이터에서 보고할 수 있는 광고 플랫폼에서 다양한 데이터를 가져옵니다. 이러한 API 연결의 주요 기능은 비용 데이터를 자동으로 가져오므로 ROI 보고를 위해 데이터를 수동으로 업로드하는 데 드는 시간과 노력을 절약할 수 있는 기능입니다. 이러한 API 연결을 설정하는 것은 에 필수가 아닙니다 [!DNL Marketo Measure] 이러한 채널을 추적하기 위해 사용할 수 있지만 보고 기능을 향상시키는 중요한 세부 정보를 제공합니다.

다음 [!DNL Marketo Measure] API 연결은 계정의 중요한 측면이며 Adobe의 우수 사례 추천은 사용자와 팀이 Adobe의 연결을 최대한 활용할 수 있도록 도와줍니다.

## 우수 사례 {#best-practice}

연결하는 광고 플랫폼에 관계없이 다음 지침을 반드시 기억하십시오!

* 관리자를 사용하여 연결
* 하나의 플랫폼에 대한 여러 광고 계정을 연결할 수 있습니다
* 가능한 모든 광고 계정을 연결하여 비용 보고를 최대한 자동화합니다
* 사용 가능한 경우 항상 추적 템플릿을 구현합니다. 템플릿은 광고 계정 연결이 끊어진 경우에도 [!DNL Marketo Measure] 은 여전히 세부적인 광고 세부 사항을 가져올 수 있습니다

각 [!DNL Marketo Measure] API입니다. 다음 모범 사례를 따르십시오.

**[!DNL Facebook]**: 자동 태깅과 연결

자동 태깅을 활성화하기 전에 광고 내역을 csv로 내보냅니다. 자동 태그 지정을 활성화하면 [!DNL Marketo Measure].

우수 사례 추천을 따르면, [!DNL Marketo Measure] [!DNL Facebook] API는 다음을 수행할 수 있습니다.

* 모두 자동 태그 지정 [!DNL Facebook] 필요한 광고 [!DNL Marketo Measure] 매개 변수 `_bf ={creative}`
* 모든 활성 상태의 광고 비용 정보 다운로드 [!DNL Facebook] 광고

>[!NOTE]
>
>에 대한 추적 템플릿이 없습니다 [!DNL Facebook]를 설정하는 경우 API는 자동 태그(_bf) 매개 변수를 사용하여 광고 세부 사항을 수집합니다.

**AdWords**: 계정 수준에서 추적 템플릿을 구현하고 자동 태그 지정을 활성화합니다

[!DNL Marketo Measure] 광고 기록 중단 또는 삭제 위험 없이 모든 광고에 대한 매개 변수를 추가 및 빼는 것을 허용하므로 계정 수준, 캠페인 수준 또는 광고 그룹 수준 추적 템플릿을 사용하는 것이 좋습니다.

우수 사례 추천을 따르면, [!DNL Marketo Measure] AdWords API는 다음 작업을 수행할 수 있습니다.

* 모든 AdWords 광고에 를 사용하여 자동 태그 지정 [!DNL Marketo Measure] 매개 변수 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 모든 활성 AdWords 광고에 대한 광고 비용 정보를 다운로드합니다

**Bing**: 계정 수준에서 추적 템플릿을 구현하고 자동 태그 지정을 활성화합니다

을 설정할 때 광고 내역을 잃을 위험은 없습니다 [!DNL Bing] 일부 다른 API 연결과 달리 API 연결입니다.

우수 사례 추천을 따르면, [!DNL Marketo Measure] Bing API는 다음 작업을 수행할 수 있습니다.
* 다음 매개 변수를 사용하여 모든 Bing Ads에 태그를 자동 지정합니다. `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 모든 활성 Bing 광고에서 광고 비용 정보를 다운로드합니다

**linkedIn**: 자동 태깅과 연결

자동 태깅을 활성화하면 공유 가 다시 만들어지고 새 크리에이티브에 배치되며 이전 크리에이티브가 보관됩니다.

우수 사례 추천을 따르면, [!DNL Marketo Measure] linkedIn API는 다음을 수행할 수 있습니다.

* 필요한 경우 광고 유형 스폰서 컨텐츠인 모든 LinkedIn 광고에 태그를 자동 지정합니다 [!DNL Marketo Measure] 매개 변수 _bl={creativeId}. 이 매개 변수가 허용하는 광고 ID를 가져옵니다 [!DNL Marketo Measure] campaign과 크리에이티브 정보를 해결하기 위한 것입니다.
* 모든 활성 상태 및 지원되는 모든 광고 비용 정보 다운로드 [!DNL LinkedIn] 광고

>[!NOTE]
>
>에 대한 추적 템플릿이 없습니다 [!DNL LinkedIn]를 설정하는 경우 API는 자동 태그(_bl) 매개 변수를 사용하여 가능한 모든 광고 세부 정보를 수집합니다.

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

모범 사례를 따르면 연결이 끊어진 경우 데이터가 손실되지 않도록 보호되지만, 가능하면 매월 정기적으로 연결을 검토할 것을 권장합니다. 이 확인은 [!UICONTROL Connections] 섹션 [!DNL Marketo Measure] 앱에서 빨간색 키 아이콘이 없고 연결이 끊어진 계정을 시그널링합니다.

API에 연결된 계정 연결이 끊기면, [!DNL Marketo Measure] 에서 비용 데이터를 새 광고에서 가져오거나 태그를 지정할 수 없습니다. 따라서 가능한 경우 항상 추적 템플릿을 구현하는 것이 좋습니다. 템플릿은 광고 계정 연결이 끊어진 경우에도 [!DNL Marketo Measure] 는 여전히 광고에 태그를 지정하고 세부 광고 세부 사항을 가져올 수 있습니다. 다시 연결되면 지출 데이터가 다시 채워지고 유료 채널 보고의 중단은 최소화됩니다.

연결 해제 및 재승인 이유는 다음과 같습니다.

* 연결된 개인 계정에 대한 암호 변경
* 그 사람은 더 이상 회사에 있지 않습니다
* API 업데이트

팀이 위의 시나리오를 경험하는 경우 [!DNL Marketo Measure] 앱을 사용하여 재인증할 필요가 없습니다.

>[!MORELIKETHIS]
>
>* [통합 광고 플랫폼(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [입찰 관리 도구가 영향을 미치는 방식 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API 매개 변수 설명](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API 개요](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords 통합 개요](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [연결된 API 계정 재인증](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)

