---
unique-page-id: 18874781
description: 속성을 통해 Doubleclick Campaign Manager 보기 구성 - [!DNL Marketo Measure] - 제품 설명서
title: 속성을 통해 Doubleclick Campaign Manager 보기 구성
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# 속성을 통해 Doubleclick Campaign Manager 보기 구성 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 속성을 통해 보기 측정 {#measuring-view-through-attribution}

>[!NOTE]
>
>를 사용 중이라면 [!DNL Marketo Measure] 및 DoubleClick Campaign Manager 통합을 위해서는 [API 연결](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 따라서 광고를 해결하기 위해 캠페인 및 크리에이티브의 세부 사항을 다운로드할 수 있습니다.

Doubleclick Campaign Manager를 사용한 추적을 통해 보기에서 더 세부적인 통찰력을 얻으려면 추적 픽셀을 구성해야 합니다.

제발 [여기를 클릭하십시오.](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) 추가 정보 [!DNL Marketo Measure] 기여도 분석 기능을 통해 봅니다.

[!DNL Marketo Measure] 는 DCM 광고 태그를 통한 타사 호출이므로 paggyback 태그로 간주됩니다. 피기백 태그는 이미지 태그, iframe 또는 javascript 태그에서만 작동하지 않습니다. DCM 지원 팀에 따르면 이는 최근에 변경되지 않았으며 항상 그러했습니다. 표준 태그는 2017년 10월 2일부터 사용되지 않지만, [!DNL Marketo Measure] 노출 횟수를 추적하려면 다음을 수행하십시오.

DCM에서 상위 및 하위 계층을 활용하는 경우, 노출 추적을 위해 모든 수준에 태그를 적용해야 합니다.

## 이미지 태그를 추가하는 방법 {#how-to-add-the-image-tag}

광고주 설정 아래에 태그를 Doubleclick에 추가하고 노출 이벤트 태그를 만듭니다.

1. 다음 코드를 1x1 이미지 픽셀로 추가합니다.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 일단 추가되면 구분 기호가 다음과 같이 매핑되는지 확인합니다. 태그가 적용된 후 이 작업은 자동으로 수행됩니다.

   v = %eadv! 광고주 Id 확장\
   a = %eaid! 광고 Id 확장\
   c = %ecid! 광고 Id 확장\
   s = %esid! 사이트 Id 확장\
   p = %epid! 배치 Id 확장\
   m = %m 일치 코드 매크로\
   n = %n 난수 매크로

   ![](assets/1.png)

## FAQ {#faq}

**Q: 이미지 태그는 안전합니까?**

A: 예. JavaScript 태그가 아니며, 이미지 태그입니다.

**Q: 연결된 사용자에게 필요한 권한은 무엇입니까?**

A: fatinking, delapporting, userinfo.email

**Q: 지출 데이터를 가져오는 데 얼마나 걸립니까?**

A: 최대 6시간

**Q: 광고 데이터를 가져오는 데 얼마나 걸립니까?**

A: 최대 6시간
