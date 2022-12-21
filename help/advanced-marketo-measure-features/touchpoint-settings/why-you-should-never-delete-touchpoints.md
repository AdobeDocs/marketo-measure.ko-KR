---
unique-page-id: 18874560
description: 터치포인트를 삭제하지 않아야 하는 이유 - [!DNL Marketo Measure] - 제품 설명서
title: 터치포인트를 삭제하지 않아야 하는 이유
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# 터치포인트를 삭제하지 않아야 하는 이유 {#why-you-should-never-delete-touchpoints}

Opportunity에 속성 크레딧이 잘못 할당된 터치포인트가 있는 경우 계정 관리자에게 연락하여 다음 단계를 결정합니다. 이러한 경우 SFDC 및 ROI 대시보드에서 터치포인트를 제거하려면 구매자의 터치포인트 억제 기능을 사용하는 것이 좋습니다. 계정 관리자가 이러한 규칙을 만드는 데 도움이 될 수 있습니다. 이러한 터치포인트를 직접 수동으로 삭제하지 마십시오.

다음 [!DNL Marketo Measure] 처리 시스템은 SFDC에서 터치 포인트가 수동으로 삭제되었음을 등록하지 않습니다. 현재, 데이터를 조정하기 위해 시스템에 신호를 보내는 트리거가 없습니다. [!DNL Marketo Measure] 다른 터치 포인트를 자동으로 푸시하여 삭제된 터치 포인트를 대체하지 않으며 터치 포인트 위치나 속성을 후속 터치 포인트에 다시 할당하지 않습니다.

터치 포인트가 삭제되면 속성 데이터에 구멍이 만들어집니다. 일반적으로 이것은 Opportunity 의 속성 터치포인트에서 나타납니다. 아래 이미지에서 Opportunity Creation 터치를 받을 터치 포인트가 삭제되었습니다. 따라서 이 영업 기회는 OC 터치포인트를 누락하며 이 Opp에 대한 속성 비율은 최대 100%까지 추가되지 않습니다.

![](assets/1.png)

SFDC에서 터치포인트가 삭제된 경우 연락처에 문의하십시오 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;} 을 입력하여 데이터 재가져오기를 요청합니다.
