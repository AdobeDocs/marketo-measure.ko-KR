---
unique-page-id: 18874602
description: 마케팅 채널 비용 - [!DNL Marketo Measure] - 제품 설명서
title: 마케팅 채널 비용
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---

# 마케팅 채널 비용 {#marketing-channel-costs}

사용의 가장 기본적인 이점 중 하나 [!DNL Marketo Measure] 은 원하는 만큼 세부적인 기능을 사용하여 마케팅 활동을 매출에 미치는 영향에 직접 연결할 수 있습니다. 터치 포인트 수준에서 투자 수익률을 확인할 수 있습니다. 이러한 이점을 활용하려면 채널 비용을 [!DNL Marketo Measure] 앱. ROI 보고서는 **마케팅 ROI 대시보드** in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[지침에 직접 이동하려면 여기를 클릭하십시오.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

다음 [!DNL Marketo Measure] 마케팅 비용 기능을 사용하면 고객이 모든 채널, 하위 채널 및 캠페인에서 비용을 업로드할 수 있습니다. 고객이 더 많은 데이터를 추가할수록 수익 속성 대시보드에서 ROI 보고를 더 많이 할 수 있습니다.

직접 광고 연결에서 보고 및 가져오는 비용은 가장 세부적인 수준에서 자동으로 가져오므로 업로드할 필요가 없습니다. 여기에는 Google AdWords, Bing Ads, Doubleclick 및 Facebook와의 현재 통합이 포함되어 있습니다.

[FAQ로 직접 이동하려면 여기를 클릭하십시오 .](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## 정의 {#definitions}

**캠페인별 비용**

가장 세분화된 수준에서 고객이 각 채널 내에서 그룹화된 개별 캠페인별로 비용을 입력할 수 있습니다. CRM 캠페인의 경우, [!DNL Marketo Measure] 은(는) 캠페인 ID를 별도의 열로 가져와서 CRM에서 오프라인 캠페인 비용을 이 표에 매핑하는 데 도움이 됩니다. 이 수준에서 비용을 추가하면 고객이 캠페인 ROI를 보고 캠페인별로 성능을 최적화할 수 있습니다.

모든 캠페인의 합계는 하위 채널 또는 채널에 입력된 값까지 합산할 필요가 없지만 하위 채널 또는 채널에 입력된 값보다 클 수는 없습니다. 합계가 하위 채널 또는 채널에 입력한 값보다 작은 경우, [!DNL Marketo Measure] &quot;기타&quot;에 대한 행을 자동으로 추가하여 차이를 막고 간격을 채웁니다.

**하위 채널별 비용**

더 높은 수준에서 고객은 채널 아래에 그룹화된 하위 채널별로 비용을 입력할 수 있습니다. 이 수준에서 비용을 추가하면 고객이 하위 채널 ROI를 보고 하위 채널별로 성능을 최적화할 수 있습니다.

모든 하위 채널의 합계는 채널에 입력된 값까지 합산할 필요가 없지만 채널에 입력된 값보다 클 수는 없습니다. 합계가 채널에 입력한 값보다 작은 경우, [!DNL Marketo Measure] &quot;기타&quot;에 대한 행을 자동으로 추가하여 차이를 막고 간격을 채웁니다.

**채널별 비용**

가장 높은 수준에서 고객이 채널별로 비용을 입력할 수 있습니다. 이 수준에서 비용을 추가하면 고객이 채널 ROI를 보고 채널별 성능을 최적화할 수 있습니다.

**날짜 선택기**

기본 날짜 범위는 [!DNL Marketo Measure] 최대 현재 월까지입니다. 비용이 정확한지 확인하기 위해, 향후 달의 비용을 입력할 수 없지만, 파트너 관계 전에 몇 개월 동안의 비용을 입력할 수 있습니다. [!DNL Marketo Measure].

**필터**

마케팅 비용 테이블에서 결과 범위를 좁히려면 맨 위에 있는 채널을 선택하여 다른 채널을 필터링합니다. 이는 팀이 단일 채널에 중점을 둘 때 유용합니다.

**검색**

검색 상자를 사용하여 채널, 하위 채널 또는 캠페인에서 일치하는 텍스트를 찾습니다.

**현재 비용 다운로드**

다운로드한 CSV가 현재 화면에서 결과를 가져오므로 적용된 모든 날짜, 필터 또는 검색이 그대로 다운로드됩니다.

**CSV 업로드**

브라우저에 표시되는 보기에 관계없이, 필터링된 보기나 모든 날짜 및 채널이 있는 기본 보기인 경우 모든 CSV를 업로드할 수 있습니다.

가장 일반적인 오류는 날짜 열 포맷입니다. 날짜 형식이 변경되면 Excel과 Google 시트 간을 이동할 때 의도적으로 발생할 수 있습니다. 날짜는 MM-YY여야 하며, 따라서 9월 12일이나 5월 12일, 05-12가 아니라 9월 12일(12일)이어야 합니다.

## 시작하기 전에 {#before-you-begin}

[!DNL Marketo Measure] 은 사용 또는 확장할 수 있는 13개의 기본 채널과 함께 제공됩니다. 또한 고유한 마케팅 구조를 수용하도록 최대 40개의 온라인 및 오프라인 채널을 만들 수 있습니다. 이를 기반으로 온라인 및 오프라인 채널도 지원하기 위해 총 200개의 하위 채널을 만들 수 있습니다.

[!DNL Marketo Measure] 는 Bing Ads 및 Google AdWords와 같은 API 통합이 있는 플랫폼에서 마케팅 채널 비용을 자동으로 다운로드합니다. 와 통합되지 않은 플랫폼에 대한 비용 [!DNL Marketo Measure] 수동으로 업로드해야 합니다. 비용 데이터를 업로드하기 전에 마케팅 채널을 설정해야 합니다.

## 마케팅 비용 업로드 {#uploading-marketing-costs}

마케팅 채널 및 규칙이 설정되거나 업데이트되면 관련 비용을 업로드할 수 있습니다. 이렇게 하려면 아래 단계를 수행합니다.

**1단계: 에서 마케팅 지출 페이지로 이동합니다 [!DNL Marketo Measure] 앱.**

로 이동합니다. **[!UICONTROL My Account]** 메뉴에서 **[!UICONTROL Settings]** 그런 다음 **[!UICONTROL Marketing Spend]** 왼쪽 사이드바 아래의 옵션 **[!UICONTROL Reporting]** 섹션을 참조하십시오.

![](assets/1.png)

**2단계: 현재 비용 CSV 다운로드**

화면 오른쪽으로 이동하고 을 클릭합니다. **[!UICONTROL Download Current Costs].** 이 옵션을 사용하면 CSV 형식으로 스프레드시트를 다운로드할 수 있습니다.

![](assets/2.png)

**3단계: CSV 파일 열기 및 변경**

파일을 가져와서 Google 시트, Apple 번호, Microsoft Excel 또는 선택한 소프트웨어를 사용하여 열 수 있습니다. [!DNL Marketo Measure] Google 시트 사용을 권장합니다.

시트를 가져온 후 채널 및 하위 채널에 비용 추가 또는 기존 정보 업데이트와 같이 원하는 변경을 수행합니다.

시트에서 논리 규칙을 확인합니다. 각 행에는 채널과 하위 채널 중 하나를 (.)로 구분하여 포함해야 합니다 끝에 점을 두어라. 이 형식을 일관되게 사용하는 것이 중요합니다.

예를 들어, Facebook을 하위 채널로 나타내고 소셜 을 채널로 나타내려면 다음과 같이 규칙을 작성해야 합니다. &quot;Social.Facebook.&quot; 마찬가지로, 오프라인 이벤트를 추적하려면 채널 구문은 다음과 같아야 합니다. &quot;Events.Big Conference.&quot; 아래 이미지에 예제가 나와 있습니다.

![](assets/3.png)

_추가 참고 사항_:

문서를 업로드할 때 문제가 발생할 수 있으므로 스프레드시트에서 날짜를 수정하지 마십시오.

필드를 비워 두지 마십시오. 추가할 달러 값이 없는 경우에도 달러 금액으로 $0를 입력합니다.

Bing Ads 및 Google AdWords 비용은 [!DNL Marketo Measure] 는 이러한 플랫폼과 API 연결에서 이 데이터를 자동으로 가져옵니다.

**4단계: 파일을 CSV 형식으로 저장**

Google Sheet에서 작업하는 경우 먼저 파일을 다운로드하십시오. 월별 데이터를 제외하거나 삭제하지 마십시오. 이 경우 CSV 파일을 업로드하려고 할 때 문제가 발생할 수 있습니다. [!DNL Marketo Measure] 나중에.

**5단계: CSV 파일 업로드**

로 이동합니다. **[!UICONTROL Cost]** 섹션 [!DNL Marketo Measure] 앱을 클릭하고 **[!UICONTROL Upload.CSV]**. 시스템이 새로 고치고 새 정보를 반영합니다.

## FAQ {#faq}

**숫자가 CSV에 표시되는 이유는 무엇입니까**

채널 또는 하위 채널처럼 높은 수준에서 값을 입력하지 않으면 [!DNL Marketo Measure] 은 자동으로 하위 수준의 합계를 얻습니다. 이 값은 파일을 업로드하면 표시됩니다. 또한 1차 하위 구성요소 합계가 상위에 대해 입력한 값보다 작은 경우 [!DNL Marketo Measure] 합계의 차이를 보여주는 &quot;기타&quot; 행을 추가합니다.

**표시된 목록에서 캠페인은 어떻게 결정됩니까?**

현재, 우리의 결과는 우리가 본 캠페인이 터치포인트로 크레딧을 받습니다. 캠페인의 활동이 있는 경우 발생한 터치포인트 날짜를 기반으로 해당 캠페인을 표시합니다.

**이동할 행과 열이 너무 많습니다. 보기를 통합할 수 있습니까?**

날짜 범위를 변경하거나 채널을 필터링하거나 값을 검색하는 기능을 사용하여 테이블의 결과를 필요에 맞게 통합할 수 있습니다.

**파일을 업로드할 수 없는 이유는 무엇입니까?**

에는 서로 다른 권한 세트가 있습니다 [!DNL Marketo Measure] 앱. 파일을 업로드하려면 &quot;AccountAdmin&quot;이어야 합니다. 이 문제를 해결하려면 AccountAdmin에서 액세스를 요청하거나 AccountAdmin이 사용자를 대신하여 파일을 업로드하도록 하십시오. 사용자 및 해당 역할 목록은 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
