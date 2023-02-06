---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---

# [!DNL Facebook] API {#facebook-api}

## 소개 {#introduction}

AdWords &amp; 와 유사합니다 [!DNL Bing Ads] 통합, [!DNL Facebook] 통합은 두 가지 기본 작업을 수행합니다.

* 모두 자동 태그 지정 [!DNL Facebook] 광고 및 [!DNL Marketo Measure] 매개 변수 (_bf)
* 모든 활성 Facebook 광고에서 광고 비용 정보를 다운로드합니다

## 구성 방법 [!DNL Facebook] 통합 {#how-to-configure-the-facebook-integration}

설정에 대해서는 7단계를 [!DNL Marketo Measure] 앱.

1. 다음으로 이동 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 로그인하고
1. 내 계정 아래에서 을 선택합니다. **[!UICONTROL Settings]**.
1. 통합에서 을 선택합니다 **[!UICONTROL Connections]**.
1. 선택 **[!UICONTROL Set Up New Ads Connection]** 그러면 팝업이 나타납니다. 선택 **[!UICONTROL Facebook]** facebook 자격 증명을 사용하여 로그인합니다.

   >[!NOTE]
   >
   >을(를) 연결하는 사람 [!DNL Facebook Ads] 계정은 [!DNL Facebook Ads] 계정이 필요합니다.

1. 한 번 [!DNL Marketo Measure] 가 Facebook 계정에 연결되어 있으면 계정 옆에 있는 연필 아이콘을 클릭합니다.
1. 이 보기 내에서 &#39;자동 태그 지정?&#39;을 이동합니다. &#39;예&#39;로 전환합니다. 그런 다음 [!UICONTROL Learn More] 약관 동의 섹션 다음을 확인합니다. [!UICONTROL Auto-tagging] 토글이 여전히 &#39;(으)로 설정되어 있습니다.[!UICONTROL Yes]&#39;

## 계정 연결 {#connecting-the-account}

![](assets/1.gif)

## 자동 태깅 활성화 {#enabling-autotagging}

>[!NOTE]
>
>자동 태그 지정을 활성화하면 우리가 지정하는 모든 광고에 대한 전환 내역 및 소셜 증명을 재설정합니다. 추천합니다 [이 데이터를 CSV로 내보내기](https://www.facebook.com/business/help/205067636197240) 자동 태그 지정을 활성화하기 전에 .

![](assets/2-2.png)

통합을 활성화하면 [!DNL Marketo Measure] 에 광고 수준 비용 다운로드를 시작합니다. [!DNL Marketo Measure Marketing ROI] 대시보드.

통합이 제대로 작동하려면 [!DNL Facebook] 계정이 필요합니다. 이렇게 하면 시스템에서 모든 광고 링크에 _bf 매개 변수를 추가할 수 있습니다. 이 프로세스는 이미 다음에 추가한 다른 추적 매개 변수 맨 위에 새 매개 변수를 추가합니다 [!DNL Facebook] 광고.

![](assets/3.gif)

## 필드 매핑 {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>터치 포인트 필드</strong></p></th> 
   <th><p><strong>값</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 Id</p></td> 
   <td><p>[[!DNL Facebook] 캠페인 Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 캠페인 이름 </p></td> 
   <td><p>[[!DNL Facebook] 캠페인 이름] 또는 [utm_campaign](제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 Id</p></td> 
   <td><p>[[!DNL Facebook] 광고 세트 Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 그룹 이름</p></td> 
   <td><p>[[!DNL Facebook] 광고 세트 이름]</p></td> 
  </tr> 
  <tr> 
   <td><p>터치 포인트 소스</p></td> 
   <td><p>"[!DNL Facebook]또는 [utm_source](제공된 경우)</p></td> 
  </tr> 
  <tr> 
   <td><p>미디엄</p></td> 
   <td><p>"Social" 또는 제공된 경우 [utm_medium]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 Id 또는 Creative_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[utm_content에서 생성된 사용자 지정 ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>광고 컨텐츠 또는 Creative_Name(Data Warehouse)</p></td> 
   <td><p>제공된 경우</p></td> 
  </tr> 
  <tr> 
   <td><p>키워드 텍스트 또는 Keyword_Name(Data Warehouse)</p></td> 
   <td><p>제공된 경우</p></td> 
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
   <td><p>[[!DNL Facebook] 계정 #]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 계정 이름]</p></td> 
  </tr> 
 </tbody> 
</table>

## FAQ {#faq}

**Q: What [!DNL Facebook] 광고는 [!DNL Marketo Measure]?**

A: 회전판, 단일 이미지. 현재 비디오, 슬라이드 쇼 또는 컬렉션이 아닙니다.

**Q: 사회적 증거가 무엇인가?**

A: 소셜 증명 는 좋아요, 클릭, 댓글 및 공유와 같은 참여 시 볼 수 있습니다.

**Q: 다음의 경우에 발생하는 작업 [!DNL Marketo Measure] 태깅 합니다.**

A: [!DNL Facebook] 광고를 편집할 수 없으므로 [!DNL Marketo Measure] 대상 URL이 포함된 크리에이티브를 삭제한 다음 새 매개 변수로 광고를 다시 만들어야 합니다.

**Q: 이유가 무엇입니까? [!DNL Marketo Measure] 모두 업데이트 [!DNL Facebook] 광고?**

A: 다음 [!DNL Marketo Measure] 프로세스는 모든 광고가 다시 활성화될 경우 태그에 태그를 지정하는 것입니다.

**Q: 연결된 사용자에게 필요한 권한은 무엇입니까?**

A: ads_management, 이메일

**Q: 지출 데이터를 가져오는 데 얼마나 걸립니까?**

A: 1시간

**Q: 광고 데이터를 가져오는 데 얼마나 걸립니까?**

A: 4시간
