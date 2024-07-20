---
description: JavaScript에서 수집한 데이터 - [!DNL Marketo Measure]
title: JavaScript에서 수집한 데이터
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
source-git-commit: c5a799c20d15c9e14bbdc69f422cd1b90a121e37
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 6%

---

# JavaScript에서 수집한 데이터 {#data-collected-by-javascript}

배포 시 Marketo Measure JavaScript에서 수집한 데이터에 대해 알아봅니다.

**샘플 요청:**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure은 모든 유형의 요청에 대해 다음과 같은 일반 데이터를 수집합니다.

<table>
<thead>
  <tr>
    <th>원본</th>
    <th>이름</th>
    <th>데이터 유형</th>
    <th>목적</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>요청 헤더</td>
    <td>IP 주소</td>
    <td>문자열</td>
    <td>사용자의 위치는 GeoIP 조회를 통해 추론됩니다. 이 데이터는 임시적이며 영구적으로 저장되지 않습니다.</td>
  </tr>
  <tr>
    <td>요청 헤더</td>
    <td>사용자 에이전트 문자열</td>
    <td>문자열</td>
    <td>사용자가 사용 중인 장치를 결정합니다.</td>
  </tr>
  <tr>
    <td>쿼리 매개 변수</td>
    <td>_biz_u</td>
    <td>문자열</td>
    <td>Bizible 쿠키 ID.</td>
  </tr>
  <tr>
    <td>쿼리 매개 변수</td>
    <td>_biz_l</td>
    <td>문자열</td>
    <td>현재 페이지 URL.</td>
  </tr>
  <tr>
    <td>쿼리 매개 변수</td>
    <td>_biz_t</td>
    <td>길게</td>
    <td>활동 타임스탬프.</td>
  </tr>
  <tr>
    <td>쿼리 매개 변수</td>
    <td>_biz_i</td>
    <td>문자열</td>
    <td>현재 페이지 제목입니다.</td>
  </tr>
</tbody>
</table>

위의 일반적인 데이터 외에도 bizible.js는 아래에 지정된 요청 유형에 따라 추가 데이터를 추가합니다.

<table>
<thead>
  <tr>
    <th>요청 유형</th>
    <th>요청 경로</th>
    <th>추가 쿼리 매개 변수</th>
    <th>데이터 유형</th>
    <th>목적</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>페이지 보기</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>문자열</td>
    <td>레퍼러 페이지 URL.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>문자열</td>
    <td>해시된 클라이언트의 화면 해상도.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>문자열</td>
    <td>선택적 매개 변수. 이 매개 변수가 있으면 테넌트가 추적하기 전에 사용자의 동의를 기다리도록 bizible.js를 구성하고 bizible.js가 추적할 사용자의 동의를 받았음을 나타냅니다.</td>
  </tr>
  <tr>
    <td>양식 제출</td>
    <td>/frm</td>
    <td>이메일</td>
    <td>문자열</td>
    <td>일반 텍스트 이메일 주소입니다.</td>
  </tr>
  <tr>
    <td>사용자 ID 매핑</td>
    <td>/u</td>
    <td>mapType</td>
    <td>enum</td>
    <td>bizible.js 매핑 종류를 감지했습니다(Marketo Munchkin id 및 Adobe ECID).</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>mapValue</td>
    <td>문자열</td>
    <td>위의 통합에 대한 실제 타사 쿠키 id 값입니다.</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible은 Marketo Measure의 이전 이름입니다.
