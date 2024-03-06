---
unique-page-id: 27656737
description: 보고서 마케팅 지출 - [!DNL Marketo Measure]
title: 보고서 마케팅 지출
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# 보고서 마케팅 지출 {#report-marketing-spend}

## 마케팅 지출 테이블 {#marketing-spend-table}

마케팅 지출 테이블에는 각 채널, 하위 채널 및 캠페인 행에 대한 통화를 표시하는 새 열이 포함되어 있습니다. 이 새 열은 여러 통화가 활성화되지 않은 경우에도 모든 고객에 대해 표시됩니다.

표에는 다양한 통화가 섞여 있습니다. 채널, 하위 채널 또는 캠페인의 합계를 단일 통화로 얻으려면 마케팅 지출 대시보드를 참조하십시오.

## 비용 업로드 {#upload-costs}

사용자가 비용 파일을 다운로드할 때 파일에는 각 행의 통화가 포함된 새 열도 포함됩니다. 허용되는 통화는 CRM에 설정되어 저장된 통화뿐입니다. 통화에 대한 3자로 된 단축 코드(USD, CAD, JPY, EUR)를 알고 있어야 하며 파일을 인식할 수 없는 통화로 업로드한 경우에는 파일 업로드가 실패합니다.

## 광고 통합 비용 {#costs-from-ad-integrations}

날짜 [!DNL Marketo Measure] 는 AdWords, Bing, Facebook 또는 Doubleclick과 같은 연결된 플랫폼에서 비용을 가져오며 보고된 통화도 사용합니다. 통화는 마케팅 지출 테이블에 표시될 때 채널, 하위 채널 및 캠페인과 함께 표시됩니다.

광고 공급자의 통화가 CRM에서 가져온 통화와 일치하지 않으면에서 &quot;혼합 통화&quot; 오류가 표시될 수 있습니다. [!DNL Marketo Measure Discover]. 이 문제를 해결하려면 CRM 관리자가 알 수 없는 통화에 대한 전환을 추가해야 합니다.

## 변환된 마케팅 지출로 마이그레이션 {#migrate-to-converted-marketing-spend}

마케팅 지출은 지금까지 단일 (USD) 통화로만 수행되었기 때문에 보고된 모든 지출을 새 통화로 변경하는 데 필요한 작업이 적습니다. 계정에 여러 통화가 활성화되지 않았더라도 USD가 아닌 단일 법인 통화가 있다면 이 마이그레이션을 수행해야 합니다.

1. 현재 지출 파일을 CSV로 다운로드
1. 통화 열에 &quot;&quot;가 표시됩니다.[!UICONTROL USD]를 가정 통화로 사용합니다. 다음 중 하나의 항목을 모두 수동으로 바꿀 수 있습니다.[!UICONTROL USD]&quot;또는 Find+Replace를 사용하여 &quot;[!UICONTROL USD]&quot;인스턴스가 고유한 회사 통화로 변경되었습니다(예:&quot;).[!UICONTROL EUR]&quot; 또는 &quot;[!UICONTROL GBP]&quot;.
1. 파일을 저장한 다음 다시 업로드하십시오. [!DNL Marketo Measure].
1. 이제 보고된 모든 비용이 새 통화로 표시됩니다.
