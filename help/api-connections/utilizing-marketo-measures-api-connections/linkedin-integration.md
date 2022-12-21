---
unique-page-id: 35586080
description: linkedIn 통합 - [!DNL Marketo Measure] - 제품 설명서
title: linkedIn 통합
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '2594'
ht-degree: 0%

---

# linkedIn 통합 {#linkedin-integration}

## 개요 {#overview}

다음 [!DNL Marketo Measure] LinkedIn과의 통합은 다음 두 가지 부분으로 제공됩니다.

스폰서 콘텐츠: 스폰서가 있는 컨텐츠 통합은 [!DNL Marketo Measure] 대상 URL에 태그를 지정하려면 다음을 수행하십시오 [!DNL LinkedIn] 궁극적으로 [!DNL Marketo Measure] 사용자의 전체 터치포인트 여정을 통해 사용자를 따르고 활동을 다시 특정 [!DNL LinkedIn] Campaign과 Creative. 이를 통해 고객에게 ROI에 대한 통찰력을 얻을 수 있습니다 [!DNL LinkedIn] 활동.

리드 젠 Forms: Marketo은 LinkedIn의 Lead Gen Forms과의 통합을 통해 LinkedIn 플랫폼을 통해 제출된 양식에 대한 통찰력을 제공합니다. 이러한 양식 채우기는 CRM의 리드와 일치하거나 [!DNL Marketo Engage] 예를 들어 속성이 기여하도록 허용합니다. 양식을 생성하는 데 도움이 되는 캠페인, 크리에이티브 및 양식에 대한 통찰력을 통해 팀은 이제 LinkedIn 마케팅 및 광고 비용을 더욱 최적화할 수 있습니다.

## 사용 가능 {#availability}

모든 고객이 사용할 수 있습니다.

## 요구 사항 {#requirements}

**Campaign Manager 역할**

대상 [!DNL Marketo Measure] 광고 데이터 및 광고 비용 데이터를 다운로드하려면 캠페인 관리자에서 다음 역할 중 하나를 수행해야 합니다.

* 청구 관리자
* 계정 관리자
* 캠페인 관리자

추가 정보: [Campaign Manager의 사용자 역할 및 기능](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**유료 미디어 관리자 역할**

대상 [!DNL Marketo Measure] 스폰서가 있는 크리에이티브를 생성/업데이트하려면 다음 유료 미디어 관리자 역할 중 하나가 있어야 합니다.

* 스폰서가 있는 컨텐츠 포스터
* Lead Gen Forms Manager

추가 정보: [linkedIn 페이지 관리자 역할](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

다른 것도 있습니다 [!DNL LinkedIn] 우리가 하는 역할 **not** 통합을 위해 가 필요합니다. 이러한 역할은 필요한 역할로 종종 오인되므로 차이점이 있습니다!

**페이지 관리자 역할**

대상 [!DNL Marketo Measure] 리드 생성 양식에서 리드를 다운로드/통합하려면 다음 페이지 관리자 역할이 있어야 합니다.

* 슈퍼 관리자

추가 정보: [linkedIn 페이지 관리자 역할](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## linkedIn 광고 유형 {#linkedin-ad-types}

[!DNL Marketo Measure] 지원 대상:

**스폰서 콘텐츠:** 스폰서가 있는 콘텐츠를 [!DNL LinkedIn] 귀사를 따르는 사용자를 넘어 구성원의 피드입니다. 스폰서가 있는 콘텐츠는 특정 대상을 타겟팅할 수 있으며, 광고주가 특정 대상에 도달하도록 도울 수 있습니다 [!DNL LinkedIn] 멤버들이 언제 어디서나 [!DNL LinkedIn] 데스크탑, 모바일, 태블릿에서 플랫폼 구축 Lead Gen Forms 가 있는 스폰서가 있는 컨텐츠가 지원됩니다.

지원되는 스폰서 콘텐츠 및 형식 유형 [!DNL Marketo Measure] 단일 이미지 광고 및 비디오 광고입니다(Lead Gen Forms을 통해). 스키마의 복잡성으로 인해 Adobe는 회전 메뉴 광고를 지원하지 않습니다.

[!DNL Marketo Measure] 은 스폰서가 있는 메시지, 텍스트 광고 또는 동적 광고를 지원하지 않습니다.

![](assets/one.png)

>[!TIP]
>
>스폰서가 없는 컨텐츠 소스(예: &quot;텍스트 광고&quot; 또는 &quot;스폰서가 있는 InMail&quot;의 캠페인 유형)에서 발생한 캠페인/지출 [!DNL Marketo Measure] does _not_ 기본적으로 이러한 캠페인 유형의 추적을 지원합니다. &quot;스폰서가 있는 컨텐츠&quot; 지출과 함께 이와 같은 캠페인의 비용을 추적하려면 마케팅 비용 CSV를 사용하여 해당 비용을 수동으로 기록해야 합니다.

## 작동 방법: 스폰서 콘텐츠 {#how-it-works-sponsored-content}

>[!NOTE]
>
>먼저 다음 위치로 이동하여 이 기능 설정을 활성화해야 합니다 [!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms].

**[!DNL LinkedIn's]고유한 자동 태깅 요구 사항**

[!DNL Marketo Measure] 을 추적하는 데 도움이 될 수 있음 [!DNL LinkedIn] 랜딩 페이지를 자동으로 태깅하여 캠페인 성과.

[!DNL Marketo Measure] 고유한 LinkedIn Share가 있는 크리에이티브를 검색하고 `?_bl={creativeId}` 매개 변수를 끝에 추가합니다.

**공유 복사**

사용 [!DNL Marketo Measure/LinkedIn] 통합은 고객이 기존 크리에이티브를 복사/복제/복제하지 않도록 요구합니다. 공유를 찾았다가 하나의 크리에이티브에서만 사용하도록 감지된 경우, [!DNL Marketo Measure] 는 크리에이티브 또는 공유 를 다시 작성하지 않고도 공유에 태그를 지정할 수 있으며 모든 광고 기록(노출 횟수, 클릭 수, 공유)은 그대로 유지됩니다.

여러 크리에이티브 간에 공유되는 공유가 발견되는 즉시, [!DNL Marketo Measure] 고유한 세트를 만들려면 일시 정지, 복사 및 다시 태깅 프로세스를 실행해야 합니다. [!DNL Marketo Measure] 은 라이브 크리에이티브를 일시 중지하고 보관하므로, 모든 것에 제대로 자동 태그를 지정하려면 노출 횟수, 클릭 수 및 소셜 공유를 포함한 광고 내역을 지웁니다.

앞으로, [!DNL Marketo Measure] 는 중복 제거를 수행하지 않도록 권장합니다. [!DNL LinkedIn] 광고 내역을 삭제하지 않고 간편하게 추적을 추가할 수 있도록 모든 크리에이티브 및 공유를 가능한 한 고유하게 공유하고 유지합니다.

**단축된 URL**

추가 단계가 필요한 이유는 LinkedIn에서 대상 URL을 [!DNL Marketo Measure] 에서 길고 확인된 URL이 표시되지 않으며 [!DNL Marketo Measure] 를 사용하려면 추적 매개 변수를 해결된 URL에 추가해야 합니다. 그 문제를 해결하기 위해서 [!DNL Marketo Measure] 광고를 다시 만들기 전에 단축된 URL을 찾고, URL을 확장한 다음, 해결된 URL과 모든 해당 매개 변수로 새 광고를 만들며, [!DNL Marketo Measure] 를 클릭하여 태그를 추가합니다. 새 광고를 만들면 광고 기록(노출 횟수, 클릭 수, 공유)이 삭제되므로 단축된 URL에 태그를 지정할 수 있는 권한이 필요합니다.

단축 URL을 많이 사용하는 경우 크리에이티브에 심각한 영향을 줄 수 있습니다. 따라서 단축된 URL을 더 이상 사용하지 않는 것이 좋습니다 [!DNL Marketo Measure] 새 광고를 만들고 광고 내역을 지우지 않아도 랜딩 페이지에 태그를 지정할 수 있습니다.

**프로세스**

몇 가지 예를 들어보겠습니다. 우리가...

크리에이티브 A : 공유 123\
크리에이티브 B : 공유 234\
Creative C : 공유 234\
광고 D : 공유 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] 는 먼저 &quot;활성&quot; 상태의 모든 캠페인, 크리에이티브 및 공유를 살펴봅니다. [!DNL Marketo Measure] 일시 중지, 보관 또는 취소된 광고에 태그를 지정하지 않습니다. 광고가 일시 중지된 경우 로 설정합니다. [!UICONTROL active], 다시 활성화되면 태깅합니다. 고유한 공유를 찾을 수 있는 경우, 이는 여러 크리에이티브 또는 캠페인(예: Creative A : 공유 123), [!DNL Marketo Measure] 사용자 지정 매개 변수를 추가합니다. `>> ?_bl={creativeId}` 공유 URL로 액세스 가능한 상태로 전환합니다.

`2)` 이제 공유가 공유되고 그 고유성이 손실된 경우(예: Creative B : 공유 234 및 Creative C : 234와 Creative D 공유 : 공유 234), [!DNL Marketo Measure] 는 유사한 모든 광고( Creative B, Creative C 및 Creative D)를 일시 중지하고 보관합니다.

`3)` [!DNL Marketo Measure] 는 보관된 크리에이티브 B의 컨텐츠를 복사하는 3개의 새로운 크리에이티브 E, Creative F 및 Creative G를 만듭니다.

`4)` [!DNL Marketo Measure] 또한 Share234의 컨텐츠를 복제하고, Share345, Share 456 및 Share 567의 신규 주식 3개를 생성하며, 이는 Share234의 고유한 주식을 보유한다는 것을 제외하고, `?_bl` 태깅합니다.

`5)` [!DNL Marketo Measure] 공유는 공유되지 않는지 정기적으로 확인해야 하며, 공유되는 경우 위의 2단계에서 프로세스를 다시 시작합니다.

>[!NOTE]
>
>이를 구현하면 고객이 Creative B 의 광고 내역을 잃게 됩니다. 공유 234, Creative C : 234와 Creative D 공유 : 이제 Creative E를 사용하여 다시 만들어지기 때문에 234를 공유하십시오. 공유 345, 공유 F : 공유 456 및 Creative G : 각각 567을 공유합니다.

![](assets/three.png)

## 작동 방법: 리드 젠 Forms {#how-it-works-lead-gen-forms}

**프로세스**

사용 [!DNL LinkedIn's] Ad Form API 및 Ad Form 응답 API를 사용하여 광고 계정에 대한 양식 제출 데이터를 수집하고 이메일 주소를 CRM 또는 Marketo의 리드에 연결할 수 있습니다.

linkedIn 양식에는 여러 이메일 주소가 포함될 수 있습니다. 양식 응답을 다운로드할 때 다음과 같은 우선 순위가 있는 이메일 주소를 찾습니다. 유효한 이메일 값이 있는 회사 이메일, 이메일 주소(기본 양식 필드) 또는 사용자 지정 필드.

Campaign 또는 Creative 상태에 관계없이 모든 양식 응답이 터치 포인트를 초래합니다. [!DNL Marketo Measure] 90일 전환 확인 제한이 있으므로 [!DNL Marketo Measure] 90일 이상 경과한 양식 응답에 액세스할 수 없지만 [!DNL Marketo Measure] 및 [!DNL LinkedIn] 통합이 활성화되면 리드 젠 양식 터치포인트가 더 많이 [!DNL Marketo Measure].

>[!NOTE]
>
>linkedIn 비용은 여전히 스폰서가 있는 컨텐츠 캠페인의 일부로 다운로드됩니다.

**CRM 또는 Marketo에서 리드 세대 Forms 추적**

이전 [!DNL Marketo Measure] 및 LinkedIn Lead Gen Forms Integration은 일반적으로 고객이 양식 제출을 Marketo 프로그램 및/또는 CRM Campaign에 푸시하여 양식을 추적하고 해당 활동에 대한 속성을 수신하는 경우에 유용합니다. 리드 세대 Forms 설정이 활성화되면 이러한 양식 제출이 두 번 카운트되지 않도록 하려고 합니다. 다음을 확인하십시오.

* CRM 개체의 &quot;구매자 터치포인트 활성화&quot; 필드가 &quot;없음&quot; 또는 &quot;모든 캠페인 구성원 제외&quot;로 설정됩니다.
* 관련 Marketo 프로그램 또는 Marketo 활동 규칙 업데이트
* 관련 CRM 캠페인 규칙 업데이트

>[!NOTE]
>
>LinkedIn API에는 90일 전환 확인 제한이 있으므로 Marketo 또는 CRM 규칙을 사용하는 경우에는 통합 기능을 활성화한 날짜보다 90일 전에 규칙의 종료 날짜를 설정하는 것이 좋습니다 [!DNL Marketo Measure].

## 터치 포인트 세부 사항 {#touchpoint-details}

한 번 [!DNL Marketo Measure] 의 LinkedIn 크리에이티브 고객 랜딩 페이지에 태그를 성공적으로 지정했으므로 터치포인트에서 해결된 광고 데이터를 볼 수 있습니다. 다음은 표시되어야 하는 데이터 값의 매핑입니다.

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>터치 포인트 필드</th> 
   <th>샘플 값</th> 
  </tr> 
  <tr> 
   <td><p>광고 Id </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>광고 컨텐츠 </p></td> 
   <td><p>#B2B 마케터의 copy-1-image-2-man 95%가 수요 생성 전략이 성공적이라고 생각합니다. 추가 정보: [!DNL https]://lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 Id </p></td> 
   <td><p>(공백) </p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 이름 </p></td> 
   <td><p>(공백) </p></td> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 Id </p></td> 
   <td><p>138949954 </p></td> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 이름 </p></td> 
   <td><p>SU - COM 계정 - 수요 기술 </p></td> 
  </tr> 
  <tr> 
   <td><p>광고 대상 URL </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>양식 URL </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>양식 URL - 원시 </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>키워드 Id </p></td> 
   <td><p>(공백) </p></td> 
  </tr> 
  <tr> 
   <td><p>키워드 일치 유형 </p></td> 
   <td><p>(공백) </p></td> 
  </tr> 
  <tr> 
   <td><p>랜딩 페이지 </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders </p></td> 
  </tr> 
  <tr> 
   <td><p>랜딩 페이지 - 원시 </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>마케팅 채널 </p></td> 
   <td><p>유료 소셜 </p></td> 
  </tr> 
  <tr> 
   <td><p>마케팅 채널 - 경로 </p></td> 
   <td><p>유료 Social.LinkedIn </p></td> 
  </tr> 
  <tr> 
   <td><p>미디엄 </p></td> 
   <td><p>"cpc" 또는 "리드 세대 양식"</p></td> 
  </tr> 
  <tr> 
   <td><p>레퍼러 페이지 </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>레퍼러 페이지 - 원시 </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>검색 구 </p></td> 
   <td><p>(공백) </p></td> 
  </tr> 
  <tr> 
   <td><p>터치 포인트 유형 </p></td> 
   <td><p>웹 양식 </p></td> 
  </tr> 
  <tr> 
   <td><p>터치 포인트 소스 </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## 비용 {#costs}

왜냐면 [!DNL Marketo Measure] 는 와 직접 통합됩니다. [!DNL LinkedIn]과 같은 방식으로 각각의 Campaign과 Creative에 대해 기록된 비용을 매일 다운로드합니다. 고객이 보고할 필요가 없습니다 [!DNL LinkedIn] 내에서 지출 [!DNL Marketo Measure] 더 이상 애플리케이션을 지원하지 않습니다.

다른 광고 통합에서와 마찬가지로, [!DNL Marketo Measure] 모두 배치하도록 마케팅 채널 규칙을 정의했습니다. [!DNL LinkedIn] 캠페인, 크리에이티브 및 비용 이 규칙을 사용하려면 고객이 유료 항목의 새 행을 삽입하려고 합니다 [!DNL LinkedIn] 노력. 새 채널이거나 기존 채널일 수 있습니다. 레퍼러 열에서 정의 &quot;[[!DNL LinkedIn] &quot;]&quot; [!DNL Marketo Measure] 가 [!DNL Marketo Measure] 태그에 가깝게 포함했습니다.

![](assets/four.png)

## [!DNL Marketo Measure] 검색 {#marketo-measure-discover}

에 몇 가지 기능이 개선되었습니다 [!DNL Marketo Measure] Lead Gen Forms 보고를 지원하기 위한 Discover 를 참조하십시오.

**유료 미디어 보드**

리드 젠 Forms 타일: LinkedIn 양식 채우기 수를 포함하는 새 타일입니다. 이 개수의 드릴스루 에는 활동 ID, 양식 날짜, 양식 이름 및 이메일 주소가 표시됩니다.

**참여 경로 보드**

이벤트 여정: 통합을 통해 제공되는 양식에 대한 &quot;활동&quot; 이벤트 유형과 미디어 &quot;리드 생성 양식&quot;을 포함합니다. 드릴스루 보기에는 Campaign, Creative 및 Form 세부 사항이 포함됩니다.

## 스폰서 콘텐츠 FAQ {#sponsored-content-faq}

**어두운 공유란 무엇입니까?**

어두운 공유는 회사 페이지에 게시되지 않고 즉시 작성하여 Creative로 직접 추가되는 게시물입니다. 그래서 [!DNL Marketo Measure]&quot;작성된 크리에이티브는 회사 페이지 맨 위에 나타나지 않고 다시 홍보됩니다. 어두운 공유들이 사용되어 백그라운드에서 나올 수 있습니다.

**상태 작업 [!DNL Marketo Measure] 실제로 태그입니다.**

에는 네 가지 다른 상태가 있습니다 [!DNL LinkedIn] Campaign 및 Creative: 활성, 일시 중지, 보관 및 취소됨. 활성화된 캠페인 및 크리에이티브에만 태그를 지정합니다. 다른 상태에 태깅하여 다시 활성으로 설정합니다. [!DNL Marketo Measure] 일시 중지, 보관 또는 취소된 캠페인 또는 크리에이티브에 태그를 지정하지 않지만 상태가 활성으로 변경되면 태깅을 다시 시작합니다.

**다음 값이 무엇입니까? [!DNL Marketo Measure] 태그를 사용합니까?**

대상 URL의 끝, [!DNL Marketo Measure] 매개 변수를 추가하고 있습니다. `&_bl={creativeId}`, 여기서 `{creativeId}` 는 LinkedIn의 광고 ID입니다. 광고 ID로, [!DNL Marketo Measure] 캠페인 ID를 결정할 수도 있습니다. [!DNL LinkedIn] 은 각 크리에이티브가 하나의 캠페인에만 속할 수 있으므로 매우 기본적인 광고 구조를 갖습니다.

**옛날 창작물에 어떤 일이 생겼나요 [!DNL Marketo Measure] 새 버전을 만드시겠습니까?**

When [!DNL Marketo Measure] 공유를 다시 만들고 새 크리에이티브에 배치하면 이전 크리에이티브가 보관됩니다. 이것이 또한 이유이다 [!DNL Marketo Measure] 보관된 캠페인 또는 크리에이티브에 태그를 지정하지 않습니다. 그렇지 않으면 [!DNL Marketo Measure] 무한정 태깅하려고 합니다.

**생성된 광고의 대상 URL이 원래 광고와 일치하지 않는 이유는 무엇입니까?**

[!DNL Marketo Measure] 추적 매개 변수를 해결된 URL에 추가해야 하지만 API에 표시되는 URL은 모든 매개 변수가 없는 경우에 단축된 URL일 수 있습니다. 그 문제를 해결하기 위해서 [!DNL Marketo Measure] 추가를 다시 만들기 전에 단축된 URL을 찾아서 확인한 다음 해결된 URL과 모든 해당 매개 변수로 새 광고를 만들어 [!DNL Marketo Measure] 를 클릭하여 태그를 추가합니다.

**내 광고에 태깅하고 있니? 모든 랜딩 페이지에 레이블 매개 변수가 표시되지 않습니까?**

일부 마케터가 대상 URL에 이미지 링크를 입력하는 것을 확인했습니다 [!DNL Marketo Measure] 태깅할 수 없으므로 광고 콘텐츠 내에서 URL을 검색합니다. If [!DNL Marketo Measure] 에는 단축 URL에 태그를 지정할 수 있는 권한이 있습니다. URL과 태그를 확장하지만 LinkedIn의 복사 구조 때문에 텍스트 내에서 자동으로 단축됩니다. 태그는 LinkedIn 단축된 URL 내에 있게 되며, 이것은 랜딩 페이지 - 원시 필드가 아닌 터치포인트의 광고 콘텐츠 필드에 표시됩니다.

**이런, 제 팀의 누군가가 실수로 주식을 복제했어요. 잠시 정지해도 될까요?**

걱정 마 [!DNL Marketo Measure] 는 더 이상 고유하지 않은 공유를 프로그래밍 방식으로 확인하므로 다른 Creative에 복사한 후 의미합니다. 일단 그 복사본이 발견되면 [!DNL Marketo Measure] 일반적인 흐름을 따라 태그를 지정하고 새 광고를 만듭니다.

**내 광고는 이전에 검토를 보류 중이었습니다. 왜 그 후에 다시 검토를 보류하고 있습니까 [!DNL Marketo Measure] 태그해?**

linkedIn을 사용하려면 만들거나 수정한 모든 광고가 게시되기 전에 일반 보안 프로세스를 통과해야 합니다. [!DNL Marketo Measure] 는 6시간마다 새로운 광고를 스캔하므로 가능한 한 빨리 광고를 차단하려고 하지만 [!DNL LinkedIn's] 추가 단계로, 몇 시간 정도 지연될 수 있습니다.

**내 광고에는 2개의 URL이 있습니다. 어떤 게 태그되나요?**

둘 다 다음 [!DNL Marketo Measure] 통합을 통해 광고의 클릭스루 이미지에서 대상 URL에 태그를 지정할 수 있지만, 광고 설명에서 단축된 URL도 자동으로 업데이트됩니다.

![](assets/five.png)

**나는 이미 나의 [!DNL LinkedIn ads] 계정이 필요합니다. 왜 그렇지? [!DNL Marketo Measure] 내 링크에 태그 지정**

연결된 [!DNL LinkedIn] 사용자는 적절한 편집 액세스 권한이 있어야 합니다. 즉, 사용자가 계정 관리자, 캠페인 관리자 또는 Creative Manager여야 합니다.

**내 크리에이티브가 복사되는지 어떻게 알 수 있습니까? 크리에이티브가 동일한 공유를 사용하고 있는지 알 수 있습니까?**

공유 ID가 [!DNL LinkedIn] 보고서 세트에서는 창의적이고 명확한 공유 간 매핑을 확인할 수 없습니다. 크리에이티브가 복사본이라고 의심되는 경우 내에서 광고를 열어 수동으로 확인할 수 있습니다. [!DNL LinkedIn] 캠페인 관리자 - 새 탭에서 광고가 열리고 URL에 공유 ID가 표시됩니다.

![](assets/six.png)

## 리드 젠 Forms FAQ {#lead-gen-forms-faq}

**이 개선 사항의 비용은 얼마입니까?**

이 오퍼는 유료 서비스에 포함되어 있습니다 [!DNL Marketo Measure] 구독.

**통합이 소급 적용됩니까?**

예, 90일 전환 확인 기간으로 제한되어 있지만 LinkedIn에서 내역 광고 양식 응답을 다운로드할 수 있습니다. 길수록 [!DNL Marketo Measure] 및 LinkedIn 통합이 활성화되면 Lead Gen Form 터치포인트가 더 많이 [!DNL Marketo Measure].

다운로드할 특정 날짜를 설정할 수 있는 선택 사항이 없지만, 억제해야 하는 터치 포인트가 있으면 터치 포인트 삭제 규칙을 선택적으로 설정할 수 있습니다.

**이미 을(를) 사용 중인 경우 이 기능이 자동으로 활성화됩니까? [!DNL Marketo Measure] linkedIn 광고 통합?**

아니요. 모든 고객을 위해 자동으로 다운로드하지 않지만 설정에서 이 기능을 사용할 수 있는 매우 간단한 스위치입니다.

**양식 데이터를 사용할 수 있습니까?**

양식 데이터는 [!DNL Marketo Measure] 양식 ID 및 양식 이름을 포함하여 검색합니다. CRM의 터치 포인트 개체에서 양식 세부 사항을 아직 사용할 수 없습니다.

**어떤 경우에도 [!DNL LinkedIn] 이전에 Marketo 프로그램 또는 CRM 캠페인에 동기화된 리드는 무엇입니까?**

모든 항목을 조정하는 것이 좋습니다 [!DNL Marketo Measure] 중복을 방지하기 위해 특정 프로그램 또는 캠페인에서 터치포인트를 생성하는 규칙입니다. LinkedIn API에는 90일 전환 확인 제한이 있으므로 Marketo 또는 CRM 규칙을 사용하는 경우에는 통합 기능을 활성화한 날짜보다 90일 전에 규칙의 종료 날짜를 설정하는 것이 좋습니다 [!DNL Marketo Measure]. 이 시점부터 [!DNL Marketo Measure] 보다 통찰력과 세부 사항을 통해 이러한 리드를 다운로드할 수 있습니다.

**자동 태그 지정 또는 추적이 있습니까?**

아니요 다른 것과 다릅니다 [!DNL Marketo Measure] 통합. 랜딩 페이지를 수정하는 대신(랜딩 페이지를 클릭스루가 없음) LinkedIn에서 관련 정보를 다운로드하고 내에서 활동으로 처리합니다 [!DNL Marketo Measure].
