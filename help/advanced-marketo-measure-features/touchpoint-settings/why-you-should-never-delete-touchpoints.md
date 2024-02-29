---
unique-page-id: 18874560
description: 터치포인트를 삭제하지 말아야 하는 이유 - [!DNL Marketo Measure] - 제품 설명서
title: 터치포인트를 삭제하지 말아야 하는 이유
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# 터치포인트를 삭제하지 말아야 하는 이유 {#why-you-should-never-delete-touchpoints}

속성 크레딧이 잘못 할당되는 영업 기회에 접점이 있는 경우 계정 관리자에게 연락하여 다음 단계를 결정하십시오. 이러한 상황에서는 구매자의 접점 억제 기능을 사용하여 SFDC 및 ROI 대시보드에서 터치포인트를 제거하는 것이 좋습니다. 계정 관리자가 이러한 규칙을 만드는 데 도움을 줄 수 있습니다. 이러한 터치포인트를 직접 수동으로 삭제하지 마십시오.

다음 [!DNL Marketo Measure] 처리 시스템은 SFDC에서 터치포인트가 수동으로 삭제되었음을 등록하지 않습니다. 오늘날에는 데이터를 조정하기 위해 시스템에 신호를 보내는 트리거가 없습니다. [!DNL Marketo Measure] 다른 터치포인트를 자동으로 푸시하여 삭제된 터치포인트를 바꾸지 않으며 터치포인트 위치 또는 속성을 후속 터치포인트에 재할당하지 않습니다.

터치포인트가 삭제되면 속성 데이터에 구멍이 생성됩니다. 일반적으로 이는 Opportunity 의 속성 터치포인트에서 나타납니다. 아래 이미지에서 영업 기회 생성 터치를 받았을 터치포인트가 삭제되었습니다. 결과적으로 이 영업 기회는 OC 접점을 놓치고 이 Opp에 대한 속성 비율이 최대 100%까지 추가되지 않습니다.

![](assets/1.png)

SFDC에서 터치포인트가 삭제된 경우 다음으로 문의하십시오. [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 데이터 다시 가져오기를 요청합니다.
