---
unique-page-id: 27656737
description: 보고서 마케팅 비용 - [!DNL Marketo Measure] - 제품 설명서
title: 보고서 마케팅 비용
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 보고서 마케팅 비용 {#report-marketing-spend}

## 마케팅 지출 테이블 {#marketing-spend-table}

이제 마케팅 비용 테이블에는 각 채널, 하위 채널 및 캠페인 행에 대한 통화를 표시하는 새 열이 포함됩니다. 이 새 열은 복수 통화가 활성화되어 있지 않더라도 모든 고객에 대해 표시됩니다.

이제 표에 여러 통화가 혼합되어 있습니다. 채널, 하위 채널 또는 캠페인의 합계를 단일 통화로 가져와야 하는 경우 마케팅 비용 대시보드를 참조하십시오.

## 업로드 비용 {#upload-costs}

사용자가 비용 파일을 다운로드하면 파일에 각 행에 대한 통화가 있는 새 열이 포함됩니다. 허용되는 통화는 CRM에 설정 및 저장된 통화뿐입니다. 통화에 대한 3자로 된 단축 코드(예: USD, CAD, JPY, EUR)를 알고 있어야 하며, 파일을 인식할 수 없는 통화로 업로드하는 경우 파일 업로드가 실패합니다.

## 광고 통합으로 인한 비용 {#costs-from-ad-integrations}

When [!DNL Marketo Measure] AdWords, Bing, Facebook 또는 Doubleclick와 같은 연결된 플랫폼에서 비용을 가져오므로 보고된 통화도 사용합니다. 마케팅 비용 표에 표시될 때 채널, 하위 채널 및 캠페인과 함께 통화가 표시됩니다.

광고 공급자의 통화가 CRM에서 가져온 통화와 일치하지 않는 경우, 에 &quot;혼합 통화&quot; 오류가 표시될 수 있습니다. [!DNL Marketo Measure Discover] 그 통화에 대한 변환을 할 수 없었기 때문입니다. 이 문제를 해결하려면 CRM 관리자가 알 수 없는 통화에 대한 전환을 추가해야 합니다.

## 전환된 마케팅 지출로 마이그레이션 {#migrate-to-converted-marketing-spend}

마케팅 지출은 지금까지 단일(USD) 통화로만 사용되어 왔기 때문에 보고된 모든 비용을 새 통화로 변경하는 데 필요한 작업이 적습니다. 계정에 여러 통화가 활성화되어 있지 않더라도 USD 이외의 단일 회사 통화가 있는 경우 이 마이그레이션을 만들어야 합니다.

1. 현재 지출 파일을 CSV로 다운로드
1. 통화 열에 &quot;[!UICONTROL USD]&quot;를 가정된 통화로 사용합니다. 수동으로 모든 &quot;[!UICONTROL USD]&quot; 또는 Find+Replace를 사용하여 모든 &quot;[!UICONTROL USD]&quot; 인스턴스를 &quot;[!UICONTROL EUR]&quot; 또는 &quot;[!UICONTROL GBP]&quot;을 예로 들 수 있습니다.
1. 파일을 저장한 다음 다시 [!DNL Marketo Measure].
1. 이제 보고된 모든 비용이 새 통화로 표시됩니다.
