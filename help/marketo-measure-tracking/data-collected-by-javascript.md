---
description: Marketo Measure 사용자를 위해 JavaScript 지침에서 수집한 데이터
title: JavaScript에서 수집한 데이터
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 13%

---

# JavaScript에서 수집한 데이터 {#data-collected-by-javascript}

배포 시 Marketo Measure JavaScript에서 수집한 데이터에 대해 알아봅니다.

**샘플 요청:**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure은 모든 유형의 요청에 대해 다음과 같은 일반 데이터를 수집합니다.

| 원본 | 이름 | 데이터 유형 | 용도 |
| --- | --- | --- | --- |
| 요청 헤더 | IP 주소 | 문자열 | 사용자의 위치는 GeoIP 조회를 통해 추론됩니다. 이 데이터는 임시적이며 영구적으로 저장되지 않습니다. |
| 요청 헤더 | 사용자 에이전트 문자열 | 문자열 | 사용자가 사용 중인 장치를 결정합니다. |
| 쿼리 매개변수 | `_biz_u` | 문자열 | Bizible 쿠키 ID. |
| 쿼리 매개변수 | `_biz_l` | 문자열 | 현재 페이지 URL. |
| 쿼리 매개변수 | `_biz_t` | 롱 | 활동 타임스탬프. |
| 쿼리 매개변수 | `_biz_i` | 문자열 | 현재 페이지 제목입니다. |

위의 일반적인 데이터 외에도 bizible.js는 아래에 지정된 요청 유형에 따라 추가 데이터를 추가합니다.

| 요청 유형 | 요청 경로 | 추가 쿼리 매개 변수 | 데이터 유형 | 용도 |
| --- | --- | --- | --- | --- |
| 페이지 보기 | `/ipv` | `_biz_r` | 문자열 | 레퍼러 페이지 URL. |
|  |  | `_biz_h` | 문자열 | 해시된 클라이언트의 화면 해상도. |
|  |  | `_biz_c` | 문자열 | 선택적 매개 변수. 이 매개 변수가 있으면 테넌트가 추적하기 전에 사용자의 동의를 기다리도록 `bizible.js`을(를) 구성하고 `bizible.js`이(가) 추적할 사용자의 동의를 받았음을 나타냅니다. |
| 양식 제출 | `/frm` | `eMail` | 문자열 | 일반 텍스트 이메일 주소입니다. |
| 사용자 ID 매핑 | `/u` | `mapType` | enum | `bizible.js`에서 검색된 사용자 ID 매핑 종류(Marketo Munchkin ID 및 Adobe ECID) |
|  |  | `mapValue` | 문자열 | 위의 통합에 대한 실제 타사 쿠키 id 값입니다. |

>[!NOTE]
>
>Bizible은 Marketo Measure의 이전 이름입니다.
