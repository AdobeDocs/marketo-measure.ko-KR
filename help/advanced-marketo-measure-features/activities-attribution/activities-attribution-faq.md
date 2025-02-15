---
unique-page-id: 18874704
description: 활동 속성 FAQ - [!DNL Marketo Measure]
title: 활동 속성 FAQ
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 활동 속성 FAQ {#activities-attribution-faq}

[!DNL Marketo Measure] 활동이 모든 활동 레코드를 가져오고 터치포인트를 생성하므로 이러한 활동이 속성 크레딧을 받을 수 있습니다. 가장 일반적인 사용 사례는 잠재 고객에게 전송된 전화 통화 또는 이메일 기록을 생성하는 영업 팀의 활동을 추적하는 것입니다. 추적할 수 있는 다른 고유한 사항은 에셋 다운로드나 비디오 보기와 같은 콘텐츠 상호 작용입니다.

>[!AVAILABILITY]
>
>이 기능은 계층 2 고객만 사용할 수 있습니다. 더 높은 계정 계층을 요청하려면 Adobe 계정 팀(계정 관리자)에 문의하십시오.

**오프라인 캠페인과 어떻게 다릅니까?**

가장 큰 차이점은 Campaigns 에서는 각 리드 또는 연락처에 대해 캠페인 멤버 하나만 허용하므로 Campaigns에서는 하나의 접점만 제공할 수 있다는 것입니다. 즉, 각 그룹화에 대해 개별 캠페인을 만들지 않는 한 아웃바운드 호출, 데모 또는 웨비나 참석자와 같은 반복 이벤트를 추적할 수 없습니다. 활동을 통해 모든 이벤트를 측정할 수 있습니다.

**작업, 이벤트 및 활동에 차이가 있습니까?**

Activities 개체는 Task 및 Event 개체에 대해 상위 또는 umbrella 역할을 합니다. 활동은 기본적으로 작업과 이벤트를 모두 포함합니다. 작업은 일반적으로 전화 통화 또는 이메일과 같은 빠른 일회성 항목을 기록하는 데 사용됩니다. 이벤트는 일반적으로 회의 또는 전화 회의와 같이 시작 또는 종료 날짜가 있는 항목에 사용됩니다.

**같은 되풀이하는 작업에 대한 잠재 고객 또는 연락처가 있는 경우, 구매자 터치포인트가 모두 표시됩니까?**

예. 동기화된 활동과 만들어진 터치포인트 사이에 1:1 관계가 있습니다.

**터치포인트가 만들어지는 레코드를 어떻게 알 수 있습니까?**

CRM의 Activity 개체를 사용하여 먼저 필터를 설정하는 것이 좋습니다. 필터 규칙을 기반으로 해당 기준에 해당하는 레코드 수에 대해 잘 알고 있다면 필요에 따라 정교화할 수 있습니다. 필수는 아니지만, 활동 규칙이 설정된 후 터치포인트를 만드는 활동 수를 사용자가 이해하는 데 유용한 방법입니다.

**캠페인 이름 [!DNL Marketo Measure]은(는) 무엇입니까?**

이러한 활동으로 인해 터치포인트가 생성되므로 [!DNL Marketo Measure]은(는) 자신이 속한 채널과 하위 채널을 알고 있어야 합니다. 각 규칙에 대해 [!DNL Marketo Measure] 캠페인 이름을 제공해야 합니다. 만든 후 온라인 채널 CSV를 사용하여 해당 [!DNL Marketo Measure] 캠페인 이름을 해당 채널에 매핑합니다. [!DNL Marketo Measure] 캠페인 이름은 [!UICONTROL Ad Campaign Name] 필드 내의 터치포인트 자체에도 표시됩니다.

**채워지는 터치포인트 필드는 무엇입니까?**

| **접점 필드** | **값** |
|---|---|
| 리드/연락처 | 모든 활동은 잠재 고객 또는 연락처와 관련되어 있습니다. |
| Campaign | Channel.Subchannel [[!DNL Marketo Measure]] |
| 터치포인트 Source | CRM 활동 |
| 보통 | Activity.Type |
| 접점 유형 | Activity.Type |
| 광고 캠페인 이름 | [!DNL Marketo Measure] 캠페인 이름 |
| 광고 콘텐츠 | 활동 제목 |
| 광고 Id | 활동 외부 Id |
| 접점 날짜 | [사용자 지정 - 앱에서 설정] |

**각 영업 사원에 대해 다른 규칙을 만들어야 할 경우 어떻게 해야 합니까? 각각에 대해 서로 다른 [!DNL Marketo Measure] 캠페인을 만들어야 합니까?**

아뇨, 안 돼요. &quot;동적 캠페인 이름&quot;을 사용하면 Activity 개체의 필드를 참조하는 &quot;대체 매개 변수&quot;를 사용하여 [!DNL Marketo Measure] 캠페인 이름의 일부(또는 전체)를 채울 수 있습니다. 예를 들어, &quot;아웃바운드 호출&quot;이라는 이름의 캠페인 이름이 [!DNL Marketo Measure]이지만 영업 담당자가 끝에 오도록 하려면 CRM 필드 이름을 사용하여 캠페인 이름 [!DNL Marketo Measure]을(를) &quot;아웃바운드 호출 {AssignedTo}&quot; 또는 &quot;아웃바운드 호출 {CreatedBy}&quot;으로 호출합니다.

**[!DNL Marketo Measure] 앱에서 활동을 설정하려면 어떻게 해야 합니까?**

[!UICONTROL Marketo] 측정 앱 내에서 활동을 구성하는 방법에 대한 지침은 [!DNL Marketo Measure] 활동 지원 문서에서 확인할 수 있습니다.

**다른 연산자의 의미는 무엇입니까?**

* 다음과 같음: 값과 정확히 일치(예: social)
* 포함: 텍스트가 중간에 있습니다(예: &#42;social&#42;).
* 다음으로 시작: 값이 텍스트로 시작합니다(예: social&#42;).
* 다음으로 끝남: 값이 텍스트로 끝남(예: &#42;social)
* 임의 항목과 일치: 쉼표로 구분된 여러 값을 추가할 수 있습니다. [!UICONTROL starts with], [!UICONTROL ends with] 또는 contains 연산자를 적용해야 하는 경우 와일드카드(&#42;)를 사용하십시오
* 보다 큼: 숫자 필드 또는 날짜/시간 필드에 사용됨
* 보다 작음: 숫자 필드 또는 날짜/시간 필드에 사용됨

**이 활동을 수행할 채널은 무엇입니까?**

활동 규칙과 해당 [!DNL Marketo Measure] 캠페인 이름이 만들어지면 온라인 채널 정의를 사용하여 해당 캠페인을 올바른 마케팅 채널 아래에 배치합니다. [!DNL Marketo Measure]은(는) 중간 및 소스뿐만 아니라 캠페인을 사용하여 채널을 정의할 수 있습니다.

위의 예에서 &quot;아웃바운드 호출 {Assigned To}&quot; 캠페인을 BDR 채널에 할당하려면 캠페인 정의가 &quot;아웃바운드 호출&#42;&quot;인 BDR 채널의 온라인 채널 CSV에 행을 삽입합니다. 별표는 와일드카드 값을 나타내므로 &quot;아웃바운드 호출&quot;로 시작하는 모든 캠페인은 각 캠페인 이름에 대해 별도의 행을 만들지 않고 BDR 채널에 속합니다.
