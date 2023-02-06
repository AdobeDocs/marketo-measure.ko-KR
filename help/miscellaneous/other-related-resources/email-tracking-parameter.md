---
unique-page-id: 37356030
description: 전자 메일 추적 매개 변수 - [!DNL Marketo Measure] - 제품 설명서
title: 전자 메일 추적 매개 변수
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 1%

---

# 전자 메일 추적 매개 변수 {#email-tracking-parameter}

다음 [!DNL Marketo Measure] 이메일 추적 매개 변수를 사용하면 마케터가 이메일 클릭 수를 양식 제출물로 처리하여 터치 포인트가 이러한 작업에 대해 생성되도록 할 수 있습니다. 이메일 추적 매개 변수를 사용하지 않으면 사용자가 양식 제출 또는 웹 채팅을 통해 실제로 사이트에 도달할 때까지 이메일의 클릭스루가 &quot;웹 방문 수&quot;로만 처리됩니다.

## 사용 사례  {#use-cases}

**웨비나 등록**: 마케팅 팀은 단일 단추가 있는 이메일 초대를 전송하여 웨비나에 등록합니다. 전자 메일에는 이미 개인 정보가 있으므로 한 번의 클릭으로 해당 정보가 자동으로 등록됩니다. 랜딩 페이지에는 전자 메일 추적 매개 변수가 포함되어 있으므로 클릭스루하고 확인 페이지에 도달하면 [!DNL Marketo Measure] 은 이메일 주소를 캡처하고 클릭스루를 양식 채우기로 처리할 수 있으며 이것은 터치포인트를 생성합니다.

**컨텐츠 다운로드**: 컨텐츠 마케팅 팀은 이메일의 직접 다운로드 링크가 포함된 최근 eBook을 홍보하려고 합니다. 이메일 템플릿이 작성되면 다운로드 확인 페이지에 이메일 추적 매개 변수가 포함되어 고객이 클릭스루할 때 [!DNL Marketo Measure] 이메일 주소를 캡처할 수 있습니다. 사이트에 양식을 작성하지 않고도 [!DNL Marketo Measure] 은 이메일 추적 매개 변수를 사용하여 확인 페이지에 도달했으므로 이메일을 통해 발생한 컨텐츠 다운로드에 대한 터치포인트를 생성할 수 있습니다.

## 작동 방법 {#how-it-works}

방문자가 사이트에 도달하면, [!DNL Marketo Measure] 에는 이메일 주소 또는 [!DNL Salesforce] 해당 방문을 &quot;양식 제출&quot;과 연결하고 해당 활동에 대한 터치포인트를 생성할 수 있는 ID입니다.

고객은 평소대로 이메일 템플릿을 작성합니다. 추적할 작업을 위한 랜딩 페이지에 추가할 때가 되면 Marketing Automation 플랫폼에서 각 개인의 값을 동적으로 표시하기 위해 토큰, 변수 태그 또는 매크로를 결정해야 합니다.

Marketo Measure은 다음 값을 허용합니다. 이메일 주소, Salesforce 리드 Id 또는 Salesforce 연락처 Id.

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
   <th><p>지지재</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.Email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://docs.marketo.com/display/public/DOCS/Tokens+Overview#TokensOverview-PersonTokens</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%이메일%% </p><p>또는</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/articleView?id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>허브스팟</p></td> 
   <td><p>(편집기를 통해 삽입됨)</p></td> 
   <td><p>해당 사항 없음</p></td> 
   <td><p>https://knowledge.hubspot.com/cos-general/how-to-use-personalization-with-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>(메시지 작성기를 통해 삽입됨)</p></td> 
   <td><p>해당 사항 없음</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

그리고 마지막으로, [!DNL Marketo Measure]를 채울 수 있도록 추적 매개 변수를 지정해야 합니다 [!DNL Marketo Measure] 은 이메일 또는 ID 값을 찾을 수 있습니다. 기본값은 위의 예와 아래 스크린샷에 표시된 대로 &quot;mailId&quot;입니다. 의 설정에 값을 입력합니다 [!DNL Marketo Measure]를 클릭한 다음 **[!UICONTROL Save]**.

![](assets/one.png)
