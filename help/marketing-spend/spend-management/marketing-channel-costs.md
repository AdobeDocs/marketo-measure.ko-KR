---
unique-page-id: 18874602
description: 마케팅 채널 비용 - [!DNL Marketo Measure] - 제품 설명서
title: 마케팅 채널 비용
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---

# 마케팅 채널 비용 {#marketing-channel-costs}

를 사용할 때의 가장 기본적인 이점 중 하나 [!DNL Marketo Measure] 은 원하는 만큼 세분화하여 마케팅 노력을 매출에 미치는 영향과 직접 연결할 수 있는 기능입니다. 접점 수준에서 투자 수익률을 볼 수 있다. 이러한 이점을 활용하려면 채널 비용을 [!DNL Marketo Measure] 앱. ROI 보고서는 자동으로 만들어지고 **마케팅 ROI 대시보드** 위치: [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[지침으로 직접 이동하려면 여기를 클릭하십시오.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

다음 [!DNL Marketo Measure] 마케팅 지출 기능을 사용하면 고객이 모든 채널, 하위 채널 및 캠페인에 지출을 업로드할 수 있습니다. 고객이 추가한 데이터가 많을수록 매출 기여도 분석 대시보드에 표시될 수 있는 ROI 보고가 늘어납니다.

직접 광고 연결에서 보고 및 가져온 비용은 가장 세분화된 수준에서 자동으로 투입되며 업로드할 필요가 없습니다. 여기에는 Google AdWords, Bing Ads, Doubleclick 및 Facebook과의 현재 통합이 포함됩니다.

[FAQ로 직접 이동하려면 여기를 클릭하십시오.](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## 정의 {#definitions}

**캠페인별 지출**

가장 세분화된 수준에서 고객은 해당 채널 내에 그룹화된 개별 캠페인별로 지출을 입력할 수 있습니다. CRM 캠페인의 경우, [!DNL Marketo Measure] 은(는) CRM의 오프라인 캠페인 지출을 이 테이블에 매핑하는 데 도움이 되는 별도의 열로 캠페인 ID를 가져옵니다. 이 수준에서 지출을 추가하면 고객이 Campaign ROI를 보고 Campaign별 성과를 최적화할 수 있습니다.

모든 캠페인의 합계는 서브채널 또는 채널에 입력된 값까지 합산할 필요는 없지만 서브채널 또는 채널에 입력된 값보다 클 수는 없습니다. 합계가 서브채널 또는 채널에 입력된 값보다 작은 경우 [!DNL Marketo Measure] 은(는) 차이점을 커버하고 공백을 채우도록 &quot;기타&quot;에 대한 행을 자동으로 추가합니다.

**하위 채널별 지출**

상위 수준에서 고객은 채널 아래에 그룹화된 하위 채널별로 지출을 입력할 수 있습니다. 이 수준에서 지출을 추가하면 고객이 하위 채널 ROI를 보고 하위 채널별 성능을 최적화할 수 있습니다.

모든 하위 채널의 합계는 채널에 입력한 모든 값까지 합산할 필요는 없지만 채널에 입력한 모든 값보다 클 수는 없습니다. 합계가 채널에 입력한 값보다 작은 경우 [!DNL Marketo Measure] 은(는) 차이점을 커버하고 공백을 채우도록 &quot;기타&quot;에 대한 행을 자동으로 추가합니다.

**채널별 소비**

가장 높은 수준에서 고객은 채널별로 지출을 입력할 수 있습니다. 이 수준에서 지출을 추가하면 고객이 채널 ROI를 확인하고 채널별 성능을 최적화할 수 있습니다.

**날짜 선택**

기본 날짜 범위는 시작 날짜부터 [!DNL Marketo Measure] 이번 달까지. 원가가 정확한지 확인하기 위해, 미래의 달에는 원가를 입력할 수 없지만, 파트너쉽을 체결하기 전 달의 원가를 입력할 수 있습니다. [!DNL Marketo Measure].

**필터**

마케팅 지출 표에서 결과 범위를 좁히려면 맨 위에서 채널을 선택하여 다른 채널을 필터링합니다. 이 기능은 팀이 단일 채널에 초점을 맞추고 있는 경우 유용합니다.

**검색**

검색 상자를 사용하여 채널, 하위 채널 또는 캠페인에서 일치하는 텍스트를 찾습니다.

**현재 비용 다운로드**

다운로드한 CSV는 현재 화면의 결과를 가져옵니다. 즉, 적용된 날짜, 필터 또는 검색이 그대로 다운로드됩니다.

**CSV 업로드**

브라우저에 있는 보기에 관계없이, 필터링된 보기이거나 모든 날짜 및 채널이 있는 기본 보기인 경우 CSV를 업로드할 수 있습니다.

가장 일반적인 오류는 날짜 열의 형식입니다. 이 오류는 날짜 형식을 변경하면 발생하고 Excel 및/또는 Google 시트 간에 이동할 경우 의도적으로 발생할 수 있습니다. 날짜는 9월 12일이 아니라 9월 12일, 5월 12일이 아니고 05-12일이 아닌 MM-YY여야 함을 명심하십시오.

## 시작하기 전에 {#before-you-begin}

[!DNL Marketo Measure] 에는 을 사용하거나 확장할 수 있는 13개의 기본 채널이 포함되어 있습니다. 또한 고유한 마케팅 구조에 맞게 최대 40개의 온라인 및 오프라인 채널을 만들 수 있습니다. 이를 기반으로 총 200개의 하위 채널을 만들어 이러한 온라인 및 오프라인 채널도 지원할 수 있습니다.

[!DNL Marketo Measure] 는 Bing Ads 및 Google AdWords와 같이 API 통합이 있는 플랫폼에서 마케팅 채널 비용을 자동으로 다운로드합니다. 와 통합되지 않은 플랫폼 비용 [!DNL Marketo Measure] 은(는) 수동으로 업로드해야 합니다. 비용 데이터를 업로드하기 전에 마케팅 채널을 설정해야 합니다.

## 마케팅 비용 업로드 {#uploading-marketing-costs}

마케팅 채널 및 규칙을 설정하거나 업데이트하면 관련 비용을 업로드할 수 있습니다. 이렇게 하려면 아래 단계를 수행합니다.

**1단계: 의 마케팅 지출 페이지로 이동 [!DNL Marketo Measure] 앱.**

로 이동 **[!UICONTROL My Account]** 메뉴, 클릭 **[!UICONTROL Settings]** 다음 위치로 이동 **[!UICONTROL Marketing Spend]** 왼쪽 사이드바의 옵션 **[!UICONTROL Reporting]** 섹션.

![](assets/1.png)

**2단계: 현재 비용 CSV 다운로드**

화면 오른쪽으로 이동하여 **[!UICONTROL Download Current Costs].** 이 옵션을 사용하면 스프레드시트를 CSV 형식으로 다운로드할 수 있습니다.

![](assets/2.png)

**3단계: CSV 파일 열기 및 변경**

파일을 가져와 Google Sheets, Apple Numbers, Microsoft Excel 또는 선택한 소프트웨어를 사용하여 열 수 있습니다. [!DNL Marketo Measure] 는 Google Sheets 사용을 권장합니다.

시트를 가져온 후에는 채널 및 하위 채널에 비용을 추가하거나 기존 정보를 업데이트하는 등 원하는 대로 변경합니다.

시트에서 논리 규칙을 확인합니다. 각 행에는 채널과 그 하위 채널 중 하나를 (.)로 구분하여 포함해야 합니다. 끝에 점이 있습니다. 이 형식을 일관되게 사용하는 것이 중요합니다.

예를 들어 Facebook을 하위 채널로 표시하고 소셜을 채널로 표시하려면 규칙을 &quot;Social.Facebook&quot;로 작성해야 합니다. 마찬가지로 오프라인 이벤트를 추적하려면 채널 구문이 &quot;Events.Big Conference&quot;여야 합니다. 아래 이미지에 예가 나와 있습니다.

![](assets/3.png)

_추가 참고 사항_:

스프레드시트의 날짜는 문서를 업로드할 때 문제가 발생할 수 있으므로 수정하지 마십시오.

필드를 비워 두지 마십시오. 추가할 달러 값이 없더라도 달러 금액으로 $0를 입력합니다.

다음 이유로 Bing Ads 및 Google AdWords 비용을 입력하거나 업데이트할 필요가 없습니다. [!DNL Marketo Measure] 는 이러한 플랫폼과의 API 연결에서 이 데이터를 자동으로 가져옵니다.

**4단계: CSV 형식으로 파일 저장**

Google Sheets에서 작업 중인 경우 먼저 파일을 다운로드해야 합니다. CSV 파일을에 업로드하려고 할 때 문제가 발생하므로 매월 데이터를 제외하거나 삭제하지 마십시오. [!DNL Marketo Measure] 나중에.

**5단계: CSV 파일 업로드**

로 이동 **[!UICONTROL Cost]** 의 섹션 [!DNL Marketo Measure] 앱 및 클릭 **[!UICONTROL Upload.CSV]**. 시스템이 새로 고침되고 새 정보가 반영됩니다.

## FAQ {#faq}

**CSV에 숫자가 표시되는 이유**

채널 또는 부채널 과 같은 상위 수준에 값을 입력하지 않으면 [!DNL Marketo Measure] 파일이 업로드되면 표시되는 하위 수준의 합계가 자동으로 표시됩니다. 또한 1차 하위 구성요소의 합계가 상위에 대해 입력한 값보다 작은 경우 [!DNL Marketo Measure] &quot;기타&quot; 행을 추가하여 합계의 차이를 표시합니다.

**내가 보고 있는 목록에서 캠페인은 어떻게 결정됩니까?**

현재 당사의 결과는 터치포인트로 인정받은 적이 있는 캠페인을 나열합니다. Campaign의 활동이 있는 경우, 발생한 터치포인트 날짜에 따라 해당 Campaign이 표시됩니다.

**건너뛸 행과 열이 너무 많습니다. 보기를 통합할 수 있습니까?**

날짜 범위를 변경하거나 채널을 필터링하거나 값을 검색할 수 있으므로 표의 결과를 사용자의 요구 사항에 맞게 통합할 수 있습니다.

**파일을 업로드할 수 없는 이유는 무엇입니까?**

다음 내에 다른 권한 집합이 있습니다. [!DNL Marketo Measure] 앱. 파일을 업로드하려면 &quot;AccountAdmin&quot;이어야 합니다. 이 문제를 해결하려면 AccountAdmin에게 액세스를 요청하거나 AccountAdmin이 대신 파일을 업로드하도록 하십시오. 사용자 및 사용자 역할 목록은 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
