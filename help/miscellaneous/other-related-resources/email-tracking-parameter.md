---
unique-page-id: 37356030
description: 이메일 추적 매개 변수 - [!DNL Marketo Measure] - 제품 설명서
title: 이메일 추적 매개 변수
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 1%

---

# 이메일 추적 매개 변수 {#email-tracking-parameter}

다음 [!DNL Marketo Measure] 이메일 추적 매개 변수를 사용하면 마케터가 이메일 클릭을 양식 제출로 취급하여 해당 작업에 대한 터치포인트를 생성할 수 있습니다. 이메일 추적 매개 변수를 사용하지 않으면 사용자가 양식 제출 또는 웹 채팅을 통해 사이트에 실제로 관여할 때까지 이메일의 클릭스루는 &quot;웹 방문&quot;으로만 처리됩니다.

## 사용 사례  {#use-cases}

**웨비나 등록**: 마케팅 팀이 웨비나 등록을 위해 단일 버튼이 있는 이메일 초대를 보냅니다. 이메일에 이미 해당 사용자의 정보가 포함되어 있으므로 한 번의 클릭으로 해당 정보가 자동 등록됩니다. 랜딩 페이지에는 이메일 추적 매개 변수가 포함되어 있으므로, 해당 사용자가 을(를) 클릭스루하여 확인 페이지에 도달하면 [!DNL Marketo Measure] 은 이메일 주소를 캡처하고 클릭스루를 양식 채우기로 처리하여 터치포인트를 생성할 수 있습니다.

**콘텐츠 다운로드**: 콘텐츠 마케팅 팀이 이메일의 직접 다운로드 링크와 함께 최근 게시한 eBook을 홍보하려고 합니다. 이메일 템플릿이 빌드되면 다운로드 확인 페이지에는 이메일 추적 매개 변수가 포함되어 클릭스루할 때 [!DNL Marketo Measure] 은 이메일 주소를 캡처할 수 있습니다. 사이트에서 양식을 작성할 필요 없이, [!DNL Marketo Measure] 은 이메일 추적 매개 변수와 함께 확인 페이지에 콘텐츠를 랜딩했으므로 이메일을 통해 발생한 콘텐츠 다운로드에 대한 터치포인트를 생성할 수 있습니다.

## 작동 방법 {#how-it-works}

방문자가 사이트에 도달하면, [!DNL Marketo Measure] 은(는) 이메일 주소 또는 이(가) 포함된 랜딩 페이지를 찾을 수 있습니다. [!DNL Salesforce] ID를 입력하여 해당 방문을 &quot;양식 제출&quot;과 연결하고 해당 활동에 대한 터치포인트를 생성할 수 있습니다.

고객은 평소와 같이 이메일 템플릿을 작성합니다. 추적할 작업의 랜딩 페이지에 추가할 시기가 되면 Marketing Automation 플랫폼에서 허용하는 토큰, 변수 태그 또는 매크로를 확인하여 각 개인에 대한 값을 동적으로 표시해야 합니다.

Marketo Measure은 이메일 주소, Salesforce 리드 ID 또는 Salesforce 연락처 ID 값을 허용합니다.

## 태그 예 {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>마케팅 자동화</p></th> 
   <th><p>토큰/태그/매크로 </p></th> 
   <th><p>예</p></th> 
   <th><p>지원 자료</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.Email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://docs.marketo.com/display/public/DOCS/Tokens+Overview#TokensOverview-PersonTokens</p></td> 
  </tr> 
  <tr> 
   <td><p>파르도</p></td> 
   <td><p>%%이메일%% </p><p>또는</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/articleView?id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>(편집기를 통해 삽입됨)</p></td> 
   <td><p>해당 사항 없음</p></td> 
   <td><p>https://knowledge.hubspot.com/cos-general/how-to-use-personalization-with-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>실제</p></td> 
   <td><p>(메시지 작성기를 통해 삽입됨)</p></td> 
   <td><p>해당 사항 없음</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

그리고 마지막으로 [!DNL Marketo Measure], 추적 매개 변수를 지정하여 [!DNL Marketo Measure] 은 이메일 또는 ID 값을 찾을 수 있습니다. 기본값은 위의 예와 아래 스크린샷에 표시된 대로 &quot;mailId&quot;입니다. 의 설정에 값을 입력합니다. [!DNL Marketo Measure]을 클릭한 다음 을 클릭합니다 **[!UICONTROL Save]**.

![](assets/one.png)
