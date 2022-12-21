---
unique-page-id: 18874676
description: "[!DNL Marketo Measure] 인사이트 설명 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 통찰력 설명"
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# [!DNL Marketo Measure] 인사이트 설명 {#marketo-measure-insights-explained}

에 대해 알아보기 [!DNL Marketo Measure] 의 통찰력 보기 [!DNL Salesforce]에는 다른 아이콘이 나타내는 것과 기능을 사용하는 방법을 포함합니다. 이 기능은 리드, 연락처 또는 계정의 처음 20개 세션을 보는 데 가장 유용합니다.

다음에 의해 누군가가 추적되면 [!DNL Marketo Measure] javascript를 사용하여 웹 사이트에 양식을 작성하면 사용자는 시스템의 리드가 되고 Salesforce(SFDC) 조직에 디지털 마케팅 데이터를 푸시합니다. 이 경우 내에 채워진 터치 포인트 데이터를 볼 수 있습니다 [!DNL Marketo Measure] Lead/Contact/Opportunity/Account 객체의 Lead Insights 섹션(Canvas App)

먼저 인사이트의 중간에서 사용자가 웹 사이트에서 보유한 세션 수를 확인할 수 있습니다. 이 세션을 스크롤하여 원하는 위치로 이동할 수 있습니다.

![](assets/1.png)

인사이트의 중간 상단에 있는 &quot;모두&quot;를 클릭하면 모든 세션의 롤업을 볼 수 있습니다. 여기에서 개별 세션의 날짜, 이러한 세션을 유도하는 채널 또는 소스 및 추가 정보를 지정하는 아이콘 세트를 이해할 수 있습니다.

가장 먼저 FT 또는 LC 아이콘이 표시됩니다. 나열된 세션의 터치 포인트 위치를 나타냅니다. 특히, FT는 리드 생성을 위한 첫 번째 터치 및 LC 대역을 나타냅니다. 여러 세션을 가질 수 있지만 하나의 터치포인트는 FT 또는 LC일 수 있습니다. 한 사람에 연결된 FT 또는 LC를 여러 개 찾을 수 없습니다.

종이와 같은 아이콘은 세션 내에서 페이지 보기가 발생했음을 나타냅니다. 모든 세션에 이 아이콘이 포함될 수 있습니다.

![](assets/2.png)

비커 모양의 아이콘은 A/B 테스트 실험이 발생했음을 나타냅니다. Adobe는 이 시점에서 Optimizely 및 VWO와 통합합니다. 이 통합을 통해 사용자가 특정 세션에서 본 실험 및 변형을 푸시할 수 있습니다.

![](assets/3.png)

특정 세션을 클릭하면(세션의 실제 날짜 또는 그룹화된 세션의 중간 부분을 클릭하여 수행할 수 있음) 세션 세부 정보를 볼 수 있습니다. 각 세션에서는 사용자가 날짜 및 시간별로 정렬한 모든 특정 페이지를 볼 수 있습니다.

![](assets/4.png)

각 세션의 오른쪽에서는 당사가 추진하는 보다 세부적인 마케팅 데이터를 볼 수 있습니다 [!DNL Marketo Measure] sfdc의 필드. 이 예에서는 광고 그룹, 광고 컨텐츠, 캠페인, 키워드, 매체를 볼 수 있습니다. 아래로 스크롤하여 더 많은 [!DNL Marketo Measure] 우리가 제공하는 데이터.

마지막으로, 누군가 많은 세션을 가지고 있으면 내에서 일부 필터를 사용할 수 있습니다 [!UICONTROL Insights] 방문자가 사이트에서 특정 참여 부분을 찾습니다. 다음을 기준으로 필터링할 수 있습니다 [!UICONTROL Touchpoint Position] 예.

페이지 보기 수, AB 테스트 또는 Forms별로 검색할 수도 있습니다.
