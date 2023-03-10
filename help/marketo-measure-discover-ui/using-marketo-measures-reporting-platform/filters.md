---
unique-page-id: 18874656
description: 필터 - [!DNL Marketo Measure] - 제품 설명서
title: 필터
exl-id: 249266c8-9ff5-4895-979c-4f377423d031
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 1%

---

# 필터 {#filters}

Discover에서 사용할 수 있는 다양한 필터 및 사용 방법에 대해 자세히 알아보십시오.

>[!NOTE]
>
>Discover 필터 내의 &quot;사용자 속성과 일치&quot; 및 &quot;일치(고급)&quot; 연산자는 순전히 관리적이며 안전하게 무시될 수 있습니다.

**계정 Id**

_에 사용됨: 계정 기반 마케팅_

CRM에서 일련의 계정 ID를 선택하거나 붙여 넣어 결과를 필터링합니다. 이름이 같을 수 있으므로 계정 ID는 계정 이름보다 더 고유성을 제공합니다.

**계정 이름**

_에 사용됨: 계정 기반 마케팅_

CRM에서 일련의 계정 이름 을 선택하거나 붙여 넣어 결과를 필터링합니다. 문자열에는 중복이 있을 수 있으므로 여러 &quot;가 있을 수 있습니다.[!DNL Marketo Measure]예를 들어 &quot; 계정이 있는 경우가 있습니다. 이 경우 단일 계정이 필요한 경우 대신 계정 ID 필터를 사용하십시오.

**속성 모델**

_에 사용됨: 개요, 마케팅 비용, 광고 ROI, 계정 기반 마케팅, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, Passport_

보드에 적용할 단일 속성 모델을 선택합니다. 첫 번째 터치, 리드 만들기 터치, U자형, W자형, 전체 경로 또는 사용자 정의 모델. 전체 경로 및 사용자 지정 모델은 모든 계층에서 사용할 수 없습니다.

**캠페인**

_에 사용됨: 개요, 성장, 광고 ROI, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, Passport_

단일 또는 여러 캠페인 이름으로 보드를 필터링합니다. 연산자는 &quot;포함&quot; 또는 &quot;다음으로 시작&quot; 연산자를 사용하는 등의 추가적인 유연성을 필터에 제공합니다. 채널 또는 하위 채널 필터가 적용된 경우 표시되는 캠페인 목록은 적용된 필터의 하위 세트가 됩니다.

**카테고리 1-10**

_에 사용됨: 개요, 성장, 광고 ROI, CMO, 유료 미디어, 컨텐츠 마케팅, 속도, 스냅샷, 집단 단계, Passport_

보드에서 만든 카테고리 및 세그먼트를 사용하여 세그먼트 필터를 보드에 적용합니다 [!DNL Marketo Measure] 설정. 만든 카테고리 목록이 필터 메뉴에 나타나므로 카테고리를 설정하지 않은 경우 메뉴에 카테고리 필터가 없습니다. 세그먼트 카테고리는 모든 계층에서 사용할 수 없으며, 사용 가능한 카테고리 수는 계층마다 다릅니다.

**채널**

_에 사용됨: 개요, 성장, 마케팅 지출, 광고 ROI, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, 속도, 여권_

하나 또는 여러 채널로 보드를 필터링합니다. 연산자는 &quot;포함&quot; 또는 &quot;다음으로 시작&quot; 연산자를 사용하는 등의 추가적인 유연성을 필터에 제공합니다. 채널을 입력하면 하위 채널 및 캠페인 필터에 표시된 값은 적용된 하위 채널 필터에서 가져옵니다.

**집단 단계**

_에 사용됨: 집단 단계_

집단을 볼 스테이지를 선택합니다. 선택한 스테이지는 맨 위에서 아래로 모든 전환이 흐르는 단계 맨 위에 나타납니다.

**날짜**

_에 사용됨: 개요, 성장, 마케팅 비용, 광고 ROI, 계정 기반 마케팅, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, 속도, 스냅샷, 집단 단계, Passport_

예를 들어 &quot;is in the range&quot;, &quot;is in the year&quot; 또는 &quot;is before&quot;와 같은 유연한 날짜 연산자를 사용하여 보드에서 데이터를 필터링할 날짜 범위를 선택합니다. 단, 스냅샷은 데이터 스냅샷을 볼 수 있는 단일 날짜를 선택합니다.

**날짜 유형**

_에 사용됨: 개요, 성장, 마케팅 지출, 광고 ROI, 계정 기반 마케팅, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, Passport_

날짜 필터에 연결된 사용할 날짜 유형을 선택합니다. 기본 날짜 유형은 보드에 따라 다릅니다. Touchpoint Date는 마케팅 활동이 발생한 날짜이고 Created Date는 CRM에서 Lead 또는 Contact 또는 Opportunity가 생성된 날짜이며 Close Date는 Opportunity가 종료된 날짜입니다.

**치수**

_에 사용됨: 유료 미디어_

Dimension은 유료 미디어 보드에서 약간 다른 방식으로 사용된다는 점을 제외하면 그룹 기준 기능과 유사합니다. Dimension은 차트를 스택하지 않고 개요 차트와 테이블의 선행 객체에서 라인을 변경합니다.

![](assets/1.png)

기본적으로 Dimension은 하위 채널로 설정되며 다음 항목으로 변경할 수 있습니다.

* 없음: 분류되지 않고 합계로 모든 것을 표시합니다
* 채널: 마케팅 채널별 데이터 목록
* 하위 채널: 마케팅 하위 채널별 데이터 목록
* 캠페인: 캠페인별 데이터 목록
* 계정: 계정별로 데이터를 나열합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 광고 그룹: 광고 그룹별로 데이터를 나열합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 광고: 광고별로 데이터를 나열합니다. Doubleclick 광고에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다
* 광고주: 광고주별로 데이터를 나열합니다. Doubleclick 광고주에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다
* 크리에이티브: 크리에이티브별로 데이터를 나열합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 키워드: 키워드별로 데이터를 나열합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 배치: 위치별로 데이터를 나열합니다. Doubleclick 배치에 적용되므로 Doubleclick를 사용하지 않으면 결과가 표시되지 않습니다
* 사이트: 사이트별 데이터를 나열합니다. Doubleclick 사이트에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다

**그룹화 기준**

_에 사용됨: 개요, 성장, 마케팅 비용, 계정 기반 마케팅, 웹 트래픽, CMO_

차트를 조정하여 함께 누적 및 그룹화되는 차원을 변경합니다. 기본적으로 그룹 기준 은 채널로 설정되며 다음과 같이 변경할 수 있습니다.

* 없음: 분류되지 않고 합계로 모든 것을 표시합니다
* 채널: 마케팅 채널별로 데이터를 그룹화합니다
* 하위 채널: 마케팅 하위 채널별로 데이터를 그룹화합니다
* 캠페인: 캠페인별로 데이터를 그룹화합니다
* 계정: 계정별로 데이터를 그룹화합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 광고 그룹: 광고 그룹별로 데이터를 그룹화합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 광고: 데이터를 광고 단위로 그룹화합니다. Doubleclick 광고에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다
* 광고주: 광고주별로 데이터를 그룹화합니다. Doubleclick 광고주에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다
* 크리에이티브: 크리에이티브별로 데이터를 그룹화합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 키워드: 데이터를 키워드별로 그룹화합니다. 적용 대상 [!DNL AdWords], [!DNL Bing], 및 [!DNL Facebook].
* 배치: 배치별로 데이터를 그룹화합니다. Doubleclick 배치에 적용되므로 Doubleclick를 사용하지 않으면 결과가 표시되지 않습니다
* 사이트: 사이트별로 데이터를 그룹화합니다. Doubleclick 사이트에 적용되므로 Doubleclick를 사용하지 않으면 결과가 나타나지 않습니다

![](assets/2.png)

**랜딩 페이지**

_에 사용됨: 컨텐츠 마케팅_

단일 랜딩 페이지의 성능이나 &quot;블로그&quot;와 같은 특정 단어가 포함된 랜딩 페이지를 드릴다운합니다.

**지표**

_에 사용됨: 개요, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅_

여러 보드에서 사용되는 두 개의 다른 지표 선택기가 있습니다. 예를 들어 매출액 또는 지출 또는 노출 횟수 보기 간을 전환할 수 있도록 지표 선택기에서 측정값이 차트로 변경됩니다.

개요 및 CMO 보드에는 ROI 지표와 관련된 값이 축소된 목록이 있습니다.

* 매출
* 지출
* 딜
* 파이프라인 매출
* 기회
* 연락처
* 리드

웹 트래픽, 유료 미디어 및 컨텐츠 마케팅 보드에서는 ROI 및 단계 지표 모두와 관련된 더 긴 값 목록이 있습니다.

* 매출
* 지출
* 딜
* 파이프라인 매출
* 기회
* 연락처
* 리드
* 클릭 수
* 노출 횟수
* 방문 횟수
* 고유 방문 횟수
* 페이지 보기 수
* Forms

**단계**

_에 사용됨: 속도_

기본적으로 [속도] 보드는 모든 단계에 대한 시간을 표시하지만 특정 스테이지로 드릴다운하려면 [스테이지] 필터를 사용하여 스테이지를 선택합니다.

**하위 채널**

_에 사용됨: 개요, 성장, 마케팅 지출, 광고 ROI, 웹 트래픽, CMO, 유료 미디어, 컨텐츠 마케팅, Passport_

하나 또는 여러 하위 채널로 보드를 필터링합니다. 연산자는 &quot;포함&quot; 또는 &quot;다음으로 시작&quot; 연산자를 사용하는 등의 추가적인 유연성을 필터에 제공합니다. 채널 필터가 적용된 경우 나타나는 하위 채널 목록은 적용된 필터의 하위 세트가 됩니다. 하위 채널을 입력하면 캠페인 필터에 표시된 값은 적용된 하위 채널 필터에서 가져옵니다.

**URL**

_에 사용됨: 웹 트래픽_

단일 URL의 트래픽 또는 &quot;product&quot;와 같은 특정 단어가 포함된 URL을 드릴다운합니다.

**원**

_에 사용됨: 속도_

기본적으로 Velocity 보드는 닫힌 원 기회만 보고하지만 이 필터를 조정하여 닫힌 원 또는 닫힌 영업 기회의 속도를 확인합니다.
