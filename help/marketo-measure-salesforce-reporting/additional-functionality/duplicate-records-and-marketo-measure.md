---
unique-page-id: 18874572
description: 중복 레코드 및 [!DNL Marketo Measure] - [!DNL Marketo Measure] - 제품 설명서
title: 중복 레코드 및 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# 중복 레코드 및 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

[!DNL Marketo Measure] 은 CRM의 관련 리드 또는 연락처에 데이터를 일치시킬 때 이메일 주소를 고유한 식별자로 활용합니다. When [!DNL Marketo Measure] 동일한 이메일 주소를 사용하는 여러 리드 또는 연락처를 찾으면 모든 레코드에 동일한 데이터를 표시하게 됩니다. 이 경우, [!DNL Marketo Measure] 구매자 터치포인트를 가진 고유한 사람의 양을 잘못 부풀릴 수 있습니다.

이것은 어떻게 생겼습니까 [!DNL Marketo Measure] 보고?

_예제 보고서: [!DNL Marketo Measure] 구매자 터치포인트를 가진 사람._

![](assets/1-1.png)

에 대해 를 볼 수 있습니다. [!DNL Marketo Measure] 해당 이메일 주소와 함께 존재하는 리드와 연락처가 있는 kelsey@adobe.com의 개인 ID입니다. 이 보고서에서는 보고된 첫 번째 터치 2개, 리드 생성 터치 2개 및 PostLC 상호 작용이 2개 있음을 알 수 있습니다. 이러한 중복 레코드는 동일한 터치 포인트 날짜 및 터치 포인트 정보를 공유하며 동일한 사람이 있음에도 불구하고 두 사람이 다른 사람들이라는 결론을 내릴 수 있습니다.

**권장 사항**

* 보고서의 반환 횟수를 최대화하려면 CRM 내에서 중복 제거 도구를 활용하여 고유한 순 레코드만 만드는 것이 좋습니다. 이 작업은 마케팅 자동화 도구 또는 CRM 내에 설치된 별도의 소프트웨어를 사용하여 수행할 수 있습니다. [!DNL Marketo Measure] 는 자동으로 레코드를 중복 제거하지 않으며 소프트웨어를 통해 이 서비스를 제공하지 않습니다.
* 중복 항목을 식별할 때 레코드를 수동으로 병합하는 것이 다른 옵션입니다. 이 프로세스는 시간이 많이 걸리고 지루할 수 있지만 정확한 보고 결과를 보고하는 것은 많은 시간을 투자할 가치가 있습니다.
