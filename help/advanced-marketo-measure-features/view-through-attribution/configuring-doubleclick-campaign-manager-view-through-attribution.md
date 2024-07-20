---
unique-page-id: 18874781
description: 속성을 통해 Doubleclick Campaign Manager 보기 구성 - [!DNL Marketo Measure]
title: 속성을 통해 Doubleclick Campaign Manager 보기 구성
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# 속성을 통해 Doubleclick Campaign Manager 보기 구성 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 속성을 통해 보기 측정 {#measuring-view-through-attribution}

>[!IMPORTANT]
>
>개인 정보 보호 문제로 인해 서드파티 쿠키가 출시되고 있습니다. Google Chrome이 발표한 2024년 3분기 타사 쿠키의 사용 중단을 통해 이러한 형식의 추적이 종료되었음을 효과적으로 알 수 있습니다. 그 결과 Adobe은 타사 쿠키에 의존하는 Marketo Measure 기능을 더 이상 사용하지 않습니다. 특히, Google/DoubleClick 노출 쿠키를 사용하는 도메인 간 추적 및 뷰스루 속성. Marketo Measure의 다른 기능은 영향을 받지 않습니다. 자사 쿠키 사용도 영향을 받지 않습니다. Google의 일정에 비추어 볼 때 위의 두 기능에 대한 예상 사용 중단 날짜는 2024년 6월 1일입니다. 이 날짜 이전에 수집된 관련 데이터는 Adobe 고객이 계속 사용할 수 있습니다.

>[!NOTE]
>
>[!DNL Marketo Measure] 및 [!DNL DoubleClick Campaign Manager] 통합을 사용하는 경우 [API 연결](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms)이 필요하므로 광고 해결을 위해 캠페인 및 광고 크리에이티브의 세부 정보를 다운로드할 수 있습니다.

[!DNL Doubleclick Campaign Manager]을(를) 사용한 추적을 통해 보기에서 보다 세부적인 통찰력을 얻으려면 추적 픽셀을 구성해야 합니다.

[!DNL Marketo Measure] 속성을 통한 보기 기능에 대한 자세한 내용은 [속성을 통한 Marketo Measure 보기 FAQ](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md)를 참조하십시오.

[!DNL Marketo Measure]은(는) DCM 광고 태그를 통한 서드파티 호출이므로 피기백 태그로 간주됩니다. 피기백 태그는 이미지 태그에서는 작동하지 않으며 iframe 또는 javascript 태그만 작동합니다. DCM 지원에 따르면, 이 기능은 최근에 변경되지 않았으며 항상 유지되어 왔습니다. 표준 태그는 2017년 10월 2일부터 사용되지 않지만 [!DNL Marketo Measure]의 노출 추적 기능에는 영향을 주지 않습니다.

DCM에서 상위 및 하위 계층을 사용하는 경우 노출 추적을 위해 모든 수준에 태그가 적용되어야 합니다.

## 이미지 태그를 추가하는 방법 {#how-to-add-the-image-tag}

Advertiser 설정 아래의 Doubleclick에 태그를 추가하고 노출 이벤트 태그를 만듭니다.

1. 다음 코드를 1x1 이미지 픽셀로 추가합니다.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 추가되면 다음과 같이 구분 기호가 매핑되는지 확인합니다. 태그가 적용되면 자동으로 설정되어야 합니다.

   v = %eadv! [!DNL Expand] 광고주 Id\
   a = %eaid! 광고 Id 확장\
   c = %ecid! 크리에이티브 ID 확장\
   s = %esid! 사이트 Id 확장\
   p = %epid! 배치 Id 확장\
   m = %m 일치 코드 매크로\
   n = %n 난수 매크로

   ![](assets/1.png)

## FAQ {#faq}

**Q: 이미지 태그가 안전합니까?**

A: 예. JavaScript 태그가 아니라 이미지 태그입니다.

**Q: 연결된 사용자에게 필요한 권한은 무엇입니까?**

A: dfatrafficking, dfareporting, userinfo.email

**Q: 지출 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 최대 6시간

**Q: 광고 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 최대 6시간
