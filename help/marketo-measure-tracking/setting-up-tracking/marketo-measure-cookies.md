---
unique-page-id: 18874590
description: '[!DNL Marketo Measure] 쿠키 - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] 쿠키'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 0ba036e7ebba77d870931704a59b19011e84271e
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 10%

---

# Marketo Measure 쿠키 {#marketo-measure-cookies}

랜딩 페이지에 [!DNL Marketo Measure] JavaScript을 적용할 때 사이트에 로드되는 다양한 [!DNL Marketo Measure] 쿠키에 대해 알아봅니다. 이 정보는 구현 중에 웹 개발 팀에 유용할 수 있습니다.

>[!IMPORTANT]
>
>개인 정보 보호 문제로 인해 서드파티 쿠키가 출시되고 있습니다. Google Chrome이 발표한 2024년 3분기 타사 쿠키의 사용 중단을 통해 이러한 형식의 추적이 종료되었음을 효과적으로 알 수 있습니다. 그 결과 Adobe은 타사 쿠키에 의존하는 Marketo Measure 기능을 더 이상 사용하지 않습니다. 특히, Google/DoubleClick 노출 쿠키를 사용하는 도메인 간 추적 및 뷰스루 속성. Marketo Measure의 다른 기능은 영향을 받지 않습니다. 자사 쿠키 사용도 영향을 받지 않습니다. Google의 일정에 비추어 볼 때 위의 두 기능에 대한 예상 사용 중단 날짜는 2024년 6월 1일입니다. 이 날짜 이전에 수집된 관련 데이터는 Adobe 고객이 계속 사용할 수 있습니다.

<table>
<thead>
  <tr>
    <th>쿠키 이름</th>
    <th>쿠키 유형</th>
    <th>목적</th>
    <th>만료</th>
    <th>보안 플래그가 설정되었습니까?<br></th>
    <th>HTTP 전용 플래그가 설정되어 있습니까?</th>
    <th>쿠키 설정자</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>자사</td>
    <td>현재 도메인에서 사용자를 고유하게 식별합니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>자사</td>
    <td>내부 진단 목적으로 모든 요청에 대해 Marketo Measure이 포함하는 시퀀스 번호입니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>자사</td>
    <td>양식 제출, 도메인 간 마이그레이션, 뷰스루 픽셀, 옵트아웃 상태 추적 등과 같은 다양한 사용자 정보를 저장하는 쿠키입니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>자사</td>
    <td>Marketo Measure 서버로 성공적으로 전송될 때까지 분석 데이터를 임시로 저장합니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>자사</td>
    <td>최적화 및 Visual Web Optimizer의 체크섬 목록이미 보고된 데이터를 저장하여 bizible.js가 수집된 데이터를 다시 보내지 못합니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>자사</td>
    <td>Bizible.js가 수집된 데이터를 다시 보내지 못하도록 Bizible 이벤트에서 보고한 체크섬 목록입니다.</td>
    <td>1년</td>
    <td>아니요</td>
    <td>아니요</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>자사</td>
    <td>여러 도메인에서 사용자를 식별하는 범용 사용자 ID로, ITP 제한을 무시하는 통합을 사용하는 테넌트에만 적용됩니다.</td>
    <td>1년</td>
    <td>예</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>타사, 도메인=.<a href="https://business.adobe.com/products/marketo/bizible.html">bizible.com</a></td>
    <td>여러 도메인에서 사용자를 식별하는 범용 사용자 ID입니다.</td>
    <td>1년</td>
    <td>예</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>타사, 도메인=.<a href="https://bizibly.com/">bizibilly.com</a></td>
    <td>임차인의 도메인에 있는 Marketo Measure 쿠키 ID와 해당 Doubleclick 노출 쿠키 ID 간의 매핑.</td>
    <td>1년</td>
    <td>예</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

JavaScript 설정 중에 웹 애플리케이션 방화벽(WAF) 경고가 트리거되면 사용자는 아래 예와 같이 해당 WAF 규칙을 비활성화하거나 쿠키를 허용 목록 할 수 있습니다.

![](assets/marketo-measure-cookies-1.png)
