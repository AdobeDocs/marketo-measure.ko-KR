---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] 쿠키 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 쿠키"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 69304dddf3569cd92c95a50e9a2e346acdad0f43
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 6%

---

# Marketo Measure 쿠키 {#marketo-measure-cookies}

다양한 항목에 대해 알아보기 [!DNL Marketo Measure] 를 적용할 때 사이트에 로드되는 쿠키 [!DNL Marketo Measure] 랜딩 페이지에 JavaScript를 추가합니다. 이 정보는 구현 중에 웹 개발 팀에 유용할 수 있습니다.

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
    <td>네</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>타사, 도메인=.<a href="http://bizible.com/">bizible.com</a></td>
    <td>여러 도메인에서 사용자를 식별하는 범용 사용자 ID입니다.</td>
    <td>1년</td>
    <td>네</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>타사, 도메인=.<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>임차인의 도메인에 있는 Marketo Measure 쿠키 ID와 해당 Doubleclick 노출 쿠키 ID 간의 매핑.</td>
    <td>1년</td>
    <td>네</td>
    <td>아니요</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

JavaScript 설정 중에 WAF(Web Application Firewall) 경고가 트리거되면 사용자는 아래 예와 같이 해당 WAF 규칙을 비활성화하거나 쿠키를 허용 목록에 추가할 수 있습니다.

![](assets/marketo-measure-cookies-1.png)
