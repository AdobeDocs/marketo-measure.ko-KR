---
unique-page-id: 18874660
description: FAQ - [!DNL Marketo Measure] - 제품 설명서
title: FAQ
exl-id: f1896bf8-2216-427e-ac3e-98d87efede76
feature: Reporting
source-git-commit: e24e01a03218252c06c9a776e0519afbddbe2b8c
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 0%

---

# FAQ {#faq}

[!DNL Marketo Measure Discover]: 자주 묻는 질문

**보고서에 필터를 어떻게 저장합니까?**

오늘처럼 쿼리 결과는 URL에 저장되고 복사된 URL과 저장하거나 공유할 수 있습니다.

**작년 또는 현재 분기처럼 사전 설정된 날짜 범위를 사용하려면 어떻게 합니까?**

이제 사전 설정된 날짜 범위를 사용하는 대신 날짜 유연성이 추가되었습니다. 작년을 계속 설정할 수 있지만 오늘부터 최근 365일인 최근 1년 또는 1/1부터 31/12까지 최근 1년 완료일을 선택할 수 있습니다. 새 날짜 선택기를 사용하는 다른 좋은 방법은 상대 날짜 범위를 설정하는 것입니다. 이 경우 이동 날짜에 대한 롤링 기간 이 제공되는 경향이 있습니다.

**CPL 또는 CPC 데이터를 가져오려면 어떻게 해야 합니까?**

이러한 지표는 유료 미디어 보드에서만 찾을 수 있습니다.

**성장 보드에 페이지 보기 수를 표시하는 것은 어떻습니까?**

Growth Board의 기능 중 하나는 트렌드 차트를 채널 또는 캠페인과 같은 차원으로 그룹화할 수 없다는 것입니다. 페이지 보기는 웹 방문 중에 발생하므로 항상 채널 또는 캠페인과 같은 소스가 있는 것은 아니므로 페이지 보기 수준에서 이러한 데이터를 사용할 수 없습니다. 유료 미디어 또는 웹 트래픽을 사용하여 페이지 보기 데이터를 봅니다.

**그룹화를 변경하면 합계가 항상 같은 금액은 아닙니다. 이유는 무엇입니까?**

계층 구조가 항상 명확한 흐름 구조가 아니기 때문에 데이터의 모든 단일 계층에 값이 있는 것은 아닙니다. 예를 들어 비용이 자체 보고되는지 또는 광고 공급자로부터 가져오기되는지 여부에 관계없이 채널 1의 총 비용은 $10,000일 수 있지만 개별 캠페인별로 총 $5,500만 실제로 보고되었으므로 채널과 캠페인 간의 그룹화가 변경되면 합계가 달라집니다.

**필터 연산자에서 &quot;사용자 속성과 일치함&quot;은 무엇입니까?**

사용자 속성은 비즈니스 ID, 이름 또는 성과 같은 사용자에게 적용되지만, 사용자는 사용자(고객)이지 고객이 아니므로 사용자 속성은에서 실제로 사용할 수 없습니다. [!DNL Marketo Measure Discover] 경험. 이 옵션은 무시해도 됩니다. 고객에게 적용되지 않는 필터를 제거하는 더 나은 사용자 지정 필터 경험을 개발하고 있습니다.

**일부 기본 날짜 범위가 다음 달 1일을 거치는 이유는 무엇입니까?**

날짜 범위가 항상 직관적이지는 않지만 기본 필터 UI에는 종료 날짜에 해당하는 유용한 &quot;이전&quot; 텍스트가 있으므로 사용 중인 종료 날짜가 원하는 범위를 벗어난 1일이어야 함을 알리는 데 도움이 됩니다.

**리드 및 연락처에 어떤 속성 모델을 사용합니까?**

리드 및 연락처에 매핑된 구매자 접점은 리드 생성 터치까지 측정되므로 첫 번째 터치, 리드 생성 및 U자형 모델을 권장합니다. 기여도 분석 모델을 W자형 또는 전체 경로로 변경하면 리드 및 연락처에 대해 U자형 모델이 자동으로 적용됩니다.

**성장 보드에서 방문 수, 고유 방문 수 및 Forms 타일이 비어 있는 이유는 무엇입니까?**

보기에서 이러한 타일이 0이거나 비어 있는 경우, 이는 타일이 계정에 대해 프로비저닝되지 않음을 의미합니다. 이와 관련하여 질문이 있는 경우 성공 관리자에게 문의하십시오.

**시간 경과에 따른 리드 및 시간 경과에 따른 연락처의 경우, 카운트는 무엇을 참조합니까?**

선택한 속성 모델에 의해 배포된 접점 수를 사용합니다. 시간이 지남에 따라 분배된 총 Lead 및 Count 가 됩니다. 이는 고유 카운트가 아닙니다.

**콘텐츠 마케팅의 채널별 양식 URL 차트에 웹 방문 횟수나 양식 채우기가 표시됩니까?**

이러한 항목은 추적된 양식 채우기만 됩니다.

**Discover over Measure의 이점은 무엇입니까?**

[!DNL Marketo Measure Discover] 에서는 드릴스루와 같이 더 나은 기능과 하위 채널 및 채널과 같은 더 나은 필터링을 제공합니다. 우리는 또한 2019 년에 잠시 Measure를 일광욕을 하고 있습니다.

**측정에서 광고 계정으로 필터링될 때 광고 그룹 및 계정별로 필터링할 수 있었습니다. 이렇게 하려면 검색에서 어떻게 해야 합니까?**

이 기능은 유료 미디어 보드에서만 사용할 수 있습니다.

**집단 단계는 Passport 단계와 어떻게 다릅니까?**

집단 단계를 사용하면 판매 단계 전환율을 보고 단계 간 영향을 측정할 수 있습니다. 필터를 사용하여 측정할 단계를 선택할 수 있습니다. 이 필터를 사용하면 해당 단계에서 모든 후속 단계로의 전환율을 볼 수 있습니다. Passport 보드는 주어진 기간 내에 각 파이프라인 단계를 거친 모든 Lead/Contact 및 Opportunity 를 표시합니다.

**유료 미디어 보드의 콘텐츠는 어떻게 결정됩니까?**

통합하면 해당 소스에서 광고 데이터를 가져올 수 있으므로 각 보드 타일에 Facebook, Google, Bing, LinkedIn 또는 Doubleclick의 알려진 광고 공급자가 있는 데이터만 포함하는 필터를 추가했습니다. 또한 디스플레이, 유료 검색, 유료 소셜, PPC, SEM, 유료 모바일, 유료 Twitter, Adroll, Terminus, Madison Logic, Madisonlogic 및 Demandbase에 대한 채널 및 하위 채널에 일치하는 퍼지 이름을 추가했습니다.

**방문 횟수와 고유 방문 횟수 간의 차이점은 무엇입니까?**

고유 방문 횟수 는 방문의 하위 집합입니다. 방문 횟수는 모든 사이트 방문의 횟수이지만 고유 방문 횟수는 해당 사이트 방문의 고유 쿠키입니다. 개인이 다른 쿠키 식별자를 사용하여 재방문하는 경우 여러 개의 고유한 방문을 고려할 수 있습니다.

**접점 카운트는 구매자 접점 또는 구매자 속성 접점 카운트입니까?**

Lead/Contact 또는 Opportunity에 터치포인트를 생성하지 않는 터치포인트와 두 터치포인트의 합계인 &quot;원시&quot; 터치포인트 또는 &quot;사용자 터치포인트&quot;로 간주되는 터치포인트의 수입니다.

**URL로 필터링할 때 타일당 비용이 $0.00로 표시되는 이유는 무엇입니까?**

이는 URL로 세그먼트화된 비용이 없기 때문에 해당 시나리오에서는 적용할 수 없기 때문에 예상되는 동작입니다.

**내 범주 필터에 대해 모든 세그먼트 옵션이 표시되지 않는 이유는 무엇입니까?**

유효한 레코드가 매핑된 세그먼트만 세그먼트 필터에 표시됩니다. 예를 들어 &quot;기타&quot; 세그먼트가 있는 레코드가 없는 경우 &quot;기타&quot;가 옵션으로 표시되지 않습니다.

**다음과 같음 [!DNL Marketo Measure Discover] gb18030 문자 세트를 지원합니까?**

Discover는 타사 도구를 사용하며 현재 설정된 GB18030 문자를 지원하지 않습니다.

**Discover를 로드할 때 &quot;이 페이지를 볼 수 있도록 인증되지 않았습니다&quot;라는 401 오류가 표시되는 이유는 무엇입니까?**

[!DNL Marketo Measure Discover] 제대로 표시하려면 타사 쿠키가 필요합니다. Discover를 사용하려면 브라우저에서 서드파티 쿠키를 활성화하고 페이지를 새로 고치십시오.

>[!NOTE]
>
>시크릿(Incognito)의 Chrome을 포함한 일부 브라우저는 기본적으로 서드파티 쿠키를 비활성화합니다.

![](assets/faq-1.png)