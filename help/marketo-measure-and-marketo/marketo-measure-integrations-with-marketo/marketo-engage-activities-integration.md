---
unique-page-id: 42762749
description: "[!DNL Marketo Engage] 활동 통합 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Engage] 활동 통합"
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 0%

---

# [!DNL Marketo Engage] 활동 통합 {#marketo-engage-activities-integration}

전체 항목의 일부 [!DNL Marketo Measure] 및 [!DNL Marketo Engage] 통합에서 Marketo 활동을 가져오는 이러한 노력은 큰 역할을 합니다. Marketo 활동을 통해 시스템은 이메일 클릭, 점수 변경 또는 진행 상태 변경과 같은 이벤트를 추적합니다. 이러한 활동 유형은 접점에 적합한 하위 집합을 선택하도록 압축하고 정의할 수 있습니다. 이러한 활동에 대한 터치포인트가 생성되면 참여 여정에서 추적되고 유료 검색 또는 파트너 마케팅과 같은 다른 마케팅 채널과 함께 측정됩니다.

## 요구 사항 {#requirements}

* 프로덕션 Marketo 인스턴스
* 프로덕션 [!DNL Salesforce] 또는 [!DNL Microsoft Dynamics] 인스턴스
* 유료 항목 [!DNL Marketo Measure] 구독
* Marketo 사용자 동기화 활성화됨([!DNL Marketo Measure] 설정)
* Marketo 프로그램 활성화됨([!DNL Marketo Measure] 설정)
* Marketo 활동 활성화됨([!DNL Marketo Measure] 설정)

## 설정 {#setup}

1. Marketo 활동 설정을 시작하려면 다음으로 이동합니다. **내 계정** > **설정** > **활동**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   먼저 규칙을 작성할 활동 유형 목록을 선택해야 합니다. 필요한 활동 유형의 하드 수는 없지만, 터치포인트에 과부하를 주지 않고 중요한 이정표의 중요성을 희석하지 않는 것이 좋습니다. 이를 통해 관련 참여를 추적하는 데 5개 이상의 활동 유형이 필요하지 않을 수 있습니다.

1. 아래의 드롭다운 메뉴를 클릭합니다. [!UICONTROL Select Activities Types] 을 클릭하여 다양한 유형을 선택합니다.

   ![](assets/three-1.png)

1. 필요한 모든 활동을 선택하면 에도 해당 활동이 채워집니다. [!UICONTROL Selected Activities List] 아래에 있을 뿐만 아니라 [!UICONTROL Define Rules].

   ![](assets/four-1.png)

1. 각 활동 유형에 대해 터치포인트에 적합한 레코드를 결정하는 규칙을 하나 이상 정의해야 합니다. 예를 들어 Marketo 사용자가 90 이상의 점수에 도달하면 시스템에서 터치포인트를 만들도록 &quot;점수 변경&quot; 활동 유형에 대한 규칙을 추가합니다.

1. 먼저 활동 유형에 따라 을 설정해야 할 수 있습니다. [!DNL Marketo Measure] 나중에 채널 매핑에 사용할 수 있는 캠페인 이름. [!DNL Marketo Measure] 캠페인 이름은 여러 규칙에서 다시 사용할 수 있습니다. 이렇게 하면 단일 채널 규칙에서 사용할 수 있는 더 광범위한 이름을 가질 수 있습니다. 일부 활동 유형에는 Marketo 프로그램이 포함되어 있지 않으므로 이 첫 번째 단계로 이름을 지정해야 합니다.

   다음은 이러한 추가 단계가 어떤 모습인지에 대한 예입니다.

   ![](assets/five-1.png)

1. &quot;점수 변경&quot; 예제에서는 Marketo 프로그램에서 해당 정보를 가져올 수 있으므로 캠페인 이름을 입력할 필요가 없습니다. 이제 규칙 표현식을 만들 수 있습니다. 이 예제를 따라 &quot; 필드를 선택하겠습니다.[!UICONTROL New Value]&quot;&quot;를 &quot; 연산자로 사용[!UICONTROL is greater than]값이 90인 &quot;

   규칙을 확장하고 &quot;and&quot; 또는 &quot;or&quot; 문을 추가하여 필터 또는 기준을 추가하여 결과 범위를 좁힐 수 있습니다.

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. 마지막으로 터치포인트 날짜로 사용할 항목을 선택합니다. Marketo에서 사용 가능한 모든 날짜 또는 날짜/시간 필드가 여기에 표시됩니다. 사용자 지정 날짜 필드가 없으면 &quot;&quot;이 표시됩니다.[!UICONTROL Activity Date].&quot;

   ![](assets/eight-1.png)

1. 다음을 클릭하십시오. **[!UICONTROL Save As Draft]** 그 동안 변경 사항을 잃지 않도록 하십시오.

   ![](assets/nine-1.png)

1. 다음 위치로 이동 **[!UICONTROL Attribute Mapping]** 탭.

   ![](assets/ten-1.png)

1. 선택한 각 활동 유형에는에서 해당 값을 보고 보고할 수 있도록 추가 Marketo 속성을 터치포인트 필드에 매핑하는 옵션이 있습니다. [!DNL Marketo Measure Discover] 또는 CRM에서 사용할 수 있습니다.

   대부분의 필드가 자동으로 매핑되었으며 다른 통합과 일치하도록 변경할 수 없습니다. 아래 필드 매핑 섹션을 참조하여 해당 값을 찾으십시오. 일부 활동 유형의 경우 Marketo에는 선택적으로 접점 필드에 매핑할 수 있는 랜딩 페이지, 레퍼러 페이지 또는 브라우저에 대한 속성이 포함됩니다. 아래 예에서는 제거할 수 있는 몇 가지 추가 제안을 했습니다.

1. 매핑할 왼쪽 열에서 구매자 터치포인트 필드를 선택합니다. 그런 다음 구매자 접점 필드에 채울 Marketo 속성을 선택합니다. 이러한 매핑은 옵션이며 매핑할 매핑 위에 추가 매핑이 있습니다. [!DNL Marketo Measure] 이(가) 이미 을(를) 설정했습니다.

   매핑 가능한 필드:

   * 도시
   * 국가
   * 지역
   * 랜딩 페이지
   * 레퍼러 페이지
   * 양식 페이지
   * 양식 날짜
   * 플랫폼
   * 브라우저

   >[!NOTE]
   >
   >광고 콘텐츠 또는 키워드와 같은 광고 필드는 광고 플랫폼 통합용으로 예약되었으므로 이 목록에서 사용할 수 없습니다.

## 활동 유형 {#activity-types}

일부 활동 유형은 프로그램 ID와 프로그램 이름을 제공하므로 구매자 터치포인트의 캠페인 ID와 캠페인 이름에 쉽게 매핑할 수 있습니다. 다른 프로그램의 경우 프로그램 연결이 없으므로 규칙 정의의 일부에서는 [!DNL Marketo Measure] 캠페인 이름. 다음은 각 카테고리의 목록입니다.

**프로그램 ID가 있는 활동 유형**

이메일 보내기(6)\
이메일 전달됨(7)\
반송된 이메일(8)\
이메일 구독 취소(9)\
이메일 열기(10)\
이메일 클릭(11)\
데이터 값 변경(13)\
점수 변경(22)\
목록에 추가(24)\
진행 상태 변경(104)\
양육에 추가(113)\
변경 육성 케이던스(115)

>[!NOTE]
>
>프로그램 ID가 예상되는 활동 유형 중 프로그램 없이 활동이 감지되면 [!DNL Marketo Measure] null Campaign 값을 가질 수 없으므로 이 값을 적격 터치포인트로 받아들이지 않습니다.

**프로그램 ID가 없는 활동 유형**

링크 클릭(3)\
새 잠재 고객 (12)\
SFDC에 리드 동기화(19)\
잠재 고객 전환(21)\
소유자 변경(23)\
목록에서 제거 (25)\
SFDC 활동(26)\
가볍게 반송된 이메일(27)\
SFDC에서 잠재 고객 삭제 (29)\
리드 병합(32)\
영업 기회에 추가 (34)\
영업 기회에서 제거 (35)\
영업 기회 업데이트 (36)\
리드 삭제(37)\
경고 보내기(38)\
판매 이메일 보내기(39)\
영업 이메일 열기 (40)\
Sales Email(41) 을 클릭합니다.\
SFDC 캠페인에 추가(42)\
SFDC 캠페인에서 제거 (43)\
SFDC 캠페인의 상태 변경(44)\
판매 이메일 수신(45)\
캠페인 요청(47)\
반송된 판매 이메일(48)\
수익 단계 변경(101)\
수익 단계 수동 변경(102)\
세그먼트 변경(108)\
Webhook (110) 호출\
친구에게 보내기 이메일(111)\
친구에게 이메일 보내기(112)\
육성 트랙 변경(114)\
Marketo으로 리드 푸시(145)\
Microsoft에 리드 동기화(300)\
콘텐츠 공유(400) 대화 상자 참여(158) 문서 상호 작용(159) 대화 상자 약속 예약(160) 대화 상자 목표 도달(161) 사용자 지정 활동(xxx)

## 채널 매핑 {#channel-mapping}

프로그램 ID가 있는 활동 유형의 규칙에 대해 프로그램에서 Marketo 프로그램 채널이 결정됩니다. 프로그램 채널을 사용하여 사용자 지정 오프라인 채널에 매핑하므로 채널이 올바르게 구성되었는지 확인해야 합니다 [여기에 지시된대로](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

프로그램 ID가 없는 활동 유형의 규칙에 대해 첫 번째 단계는 캠페인 이름을 만드는 것이었습니다. 이 캠페인 이름을 사용하여 사용자 정의 온라인 채널을 설정합니다. [여기 펼쳐진](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Marketo 활동에 대한 채널이 제대로 구성되지 않은 경우 새 터치포인트가 &quot;기타&quot; 채널에 해당할 수 있습니다.

## 프로그램 비용 {#program-costs}

Marketo 프로그램의 데이터 가져오기를 통해 비용은 기간 원가에서 자동으로 다운로드되고 Marketo의 보고된 비용은 할당된 달 내내 배포됩니다. 예를 들어 $1000가 2021년 1월에 보고되면 $1000는 31일에 걸쳐 분할됩니다. 비용은 다음 위치에서 찾을 수 있습니다. [!DNL Marketo Measure Discover].

## 쿠키 매핑 {#cookie-mapping}

의 결과로 [!DNL Marketo Measure] Marketo과 통합, [!DNL Marketo Measure] 쿠키 ID도 이제 매핑되고 와 동기화됩니다. [!DNL Marketo Munchkin Id]. 이렇게 하면 FT 및 LC 터치를 모두 Marketo 활동에 귀속시키지 않고 간격을 닫아 익명의 첫 번째 터치를 웹 세션에 귀속시킵니다. 이 시나리오를 상상해 보십시오.

마크는 Facebook 광고를 클릭하고 wayneenterprises.com에 와서 쿠키를 가져옵니다. [!DNL Marketo Measure] Id 123 및 [!DNL Marketo Munchkin Id] 456. 양식 채우기가 수행되지 않습니다.

Wayne Enterprises 마케팅 팀은 특정 타겟팅된 리드에 이메일 폭탄을 발송하며, 그 중 하나가 `mark@email.com`.

`mark@email.com` 이메일을 수신하고 을 클릭하여 (으)로 전환합니다. `wayneenterprises.com`. 다음과 같이 됩니다. `mark@email.com's` 두 번째 방문 `wayneenterprise.com` 쿠키 ID가 동일하지만 양식 채우기가 없으므로 [!DNL Marketo Measure], 여전히 익명 방문자입니다.

Wayne Enterprises 마케팅 팀은 &quot;이메일 클릭&quot; 활동 유형에 대한 터치포인트를 생성하는 Marketo 활동 규칙을 만듭니다.

오늘의 구현은 을 위한 단일 FT 및 LC 접점을 만듭니다. `mark@email.com` 이메일 클릭 활동 유형의 Marketo 활동에서

이 쿠키 매핑 개선 사항을 통해 FT는 다시 Facebook 광고로 전환되고 LC는 이메일에 대한 크레딧을 받습니다.

>[!NOTE]
>
>쿠키 매핑 비헤이비어를 사용하면 웹 방문에서 발생하는 일부 LC 터치포인트를 찾을 수 있습니다. 연결된 활동 없이 Marketo에 잠재 고객이 나타났을 수 있습니다. [!DNL Marketo Measure] 해당 리드를 다운로드하고 관련 쿠키와 일치시킨 다음, 리드를 생성한 양식 활동이 없어도 가장 최근 웹 세션으로 추적했습니다.

## FAQ {#faq}

**Marketo 프로그램 규칙을 만들지 Marketo 활동 규칙을 만들지 어떻게 알 수 있습니까?**

다음 [!DNL Marketo Engage] 프로그램 통합은 개인이 프로그램의 프로그램 구성원인지 여부에 따라 터치포인트를 생성하는 간단한 방법입니다. 개인이 특정 프로그램 상태를 변경하는 시간을 기준으로 규칙을 정의하려면 [!DNL Marketo Engage] 활동 통합은 원하는 설정이며, 특히 &quot;진행 중 상태 변경&quot; 활동 유형을 통해 터치포인트 날짜를 시스템에서 생성한 활동 날짜에 매핑할 수 있습니다.

**터치포인트 유형의 이름이 잘리는 이유는 무엇입니까?**

터치포인트 유형 필드는 [!DNL Marketo Measure] 16자로 된 패키지. 안타깝게도 필드의 문자 제한을 변경하려면 기존 필드를 더 이상 사용하지 않고 새 필드를 만들어야 합니다. 접점 유형 의 값은 활동 유형이며, 매체 필드에도 설정됩니다.

**내 사용자 지정 활동 유형이 사용 가능한 활동 목록에 표시되지 않는 이유는 무엇입니까?**

&quot;승인됨&quot; 사용자 정의 활동 유형만 표시되며 초안이나 초안으로 승인됨은 표시되지 않습니다.

**터치포인트를 생성할 활동 유형을 어떻게 결정합니까?**

만들 수 있는 활동 유형의 수에는 제한이 없지만 일반적으로 5개 이하의 활동 유형을 사용하는 것이 좋습니다. 접점 여정의 일부가 될 수 있을 만큼 적절한 마케팅 활동을 결정하려면 시간이 걸립니다. 예를 들어 &quot;이메일 구독 취소&quot;는 추적하기에 중요한 터치포인트가 아닐 수 있지만 추가 필터가 있는 &quot;이메일 클릭&quot;이 유용할 수 있습니다. 이는 각 조직 및 팀에 따라 다르므로, 팀과 협력하여 여기에서 가장 적합한 접근 방식을 브레인스토밍하는 것이 좋습니다.

**내 브라우저 이름이 잘리는 이유는 무엇입니까?**

다음 [!DNL Marketo Measure] Marketo에서 가져온 사용자 에이전트 값은 긴 문자열이지만 브라우저 이름은 20자로 제한됩니다.

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
