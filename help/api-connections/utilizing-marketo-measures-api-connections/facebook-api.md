---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure]"
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# [!DNL Facebook] API {#facebook-api}

## 소개 {#introduction}

AdWords 및 [!DNL Bing Ads] 통합과 마찬가지로 [!DNL Facebook] 통합은 두 가지 기본적인 작업을 수행합니다.

* [!DNL Marketo Measure] 매개 변수(_bf)를 사용하여 모든 [!DNL Facebook] 광고에 자동 태그 지정
* 모든 활성 Facebook 광고에서 광고 비용 정보 다운로드

## [!DNL Facebook] 통합을 구성하는 방법 {#how-to-configure-the-facebook-integration}

[!DNL Marketo Measure] 앱 내에서 완료해야 하는 7가지 단계가 있습니다.

1. [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}(으)로 이동하여 로그인합니다.
1. 내 계정에서 **[!UICONTROL Settings]**&#x200B;을(를) 선택합니다.
1. 통합에서 **[!UICONTROL Connections]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Set Up New Ads Connection]**&#x200B;을(를) 선택하면 팝업이 나타납니다. **[!UICONTROL Facebook]**&#x200B;을(를) 선택하고 Facebook 자격 증명을 사용하여 로그인합니다.

   >[!NOTE]
   >
   >[!DNL Facebook Ads] 계정을 연결하는 사람은 [!DNL Facebook Ads] 계정 내에서 관리자여야 합니다.

1. [!DNL Marketo Measure]이(가) Facebook 계정에 연결되면 계정 옆에 있는 연필 아이콘을 클릭합니다.
1. 이 보기 내에서 &#39;자동 태그 지정?&#39;을 이동합니다. &#39;예&#39;로 전환합니다. [!UICONTROL Learn More] 섹션에 있는 확인란을 선택하여 약관에 동의합니다. [!UICONTROL Auto-tagging] 토글이 여전히 &#39;[!UICONTROL Yes]&#39;(으)로 설정되어 있는지 확인하십시오.

## 계정 연결 {#connecting-the-account}

![](assets/1.gif)

## 자동 태그 지정 사용 {#enabling-autotagging}

>[!NOTE]
>
>자동 태그 지정을 활성화하면 태그 지정하는 모든 광고의 전환 내역과 소셜 증명이 재설정됩니다. 자동 태그 지정을 활성화하기 전에 [이 데이터를 CSV로 내보내기](https://www.facebook.com/business/help/205067636197240)하는 것이 좋습니다.

![](assets/2-2.png)

통합을 활성화하면 [!DNL Marketo Measure]이(가) 광고 수준 비용을 [!DNL Marketo Measure Marketing ROI] 대시보드로 다운로드하기 시작합니다.

통합이 제대로 작동하려면 [!DNL Facebook] 계정에서 자동 태그 지정을 활성화해야 합니다. 이렇게 하면 시스템에서 모든 광고 링크에 _bf 매개 변수를 추가할 수 있습니다. 이 프로세스에서는 [!DNL Facebook] 광고에 이미 추가한 다른 추적 매개 변수 위에 새 매개 변수를 추가합니다.

![](assets/3.gif)

## 필드 매핑 {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>접점 필드</strong></p></th> 
   <th><p><strong>값</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 Id</p></td> 
   <td><p>[[!DNL Facebook] 캠페인 ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 이름 </p></td> 
   <td><p>[[!DNL Facebook] 캠페인 이름] 또는 [utm_campaign] (제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 ID</p></td> 
   <td><p>[[!DNL Facebook] 광고 집합 Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 이름</p></td> 
   <td><p>[[!DNL Facebook] 광고 집합 이름]</p></td> 
  </tr> 
  <tr> 
   <td><p>터치포인트 Source</p></td> 
   <td><p>"[!DNL Facebook]" 또는 [utm_source] (제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>미디엄</p></td> 
   <td><p>"Social" 또는 [utm_medium] (제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 Id 또는 Creative_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[utm_content에서 생성된 사용자 지정 ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 컨텐츠 또는 Creative_Name(Data Warehouse)</p></td> 
   <td><p>[utm_content] (제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>키워드 텍스트 또는 Keyword_Name(Data Warehouse)</p></td> 
   <td><p>[utm_term] (제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 광고 Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 광고 이름]</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[utm_term에서 생성된 사용자 지정 ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider(Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 계정 번호]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 계정 이름]</p></td> 
  </tr> 
 </tbody> 
</table>

## FAQ {#faq}

**Q: [!DNL Marketo Measure]에서 지원하는 [!DNL Facebook] 광고는 무엇입니까?**

A: 회전 메뉴, 단일 이미지 지금은 비디오, 슬라이드쇼 또는 컬렉션이 아닙니다.

**Q: 소셜 증명이란 무엇입니까?**

A: 소셜 증명에는 좋아요, 클릭 수, 댓글 및 공유와 같은 참여가 표시됩니다.

**Q: [!DNL Marketo Measure]에서 광고에 태그를 지정할 때 어떻게 됩니까?**

A: [!DNL Facebook]은(는) 광고 편집을 허용하지 않으므로 [!DNL Marketo Measure]은(는) 대상 URL이 포함된 크리에이티브를 삭제한 다음 새 매개 변수로 광고를 다시 만들어야 합니다.

**Q: [!DNL Marketo Measure]에서 [!DNL Facebook]개의 광고를 모두 업데이트하는 이유는 무엇입니까?**

A: [!DNL Marketo Measure] 프로세스는 모든 광고가 다시 활성화될 경우 태그를 지정하는 것입니다.

**Q: 연결된 사용자에게 필요한 권한은 무엇입니까?**

A: ads_management, 이메일

**Q: 지출 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 1시간

**Q: 광고 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 4시간
