---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] 쿠키 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 쿠키"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo Measure 쿠키 {#marketo-measure-cookies}

다양한 항목에 대해 알아보기 [!DNL Marketo Measure] 를 적용할 때 사이트에 로드되는 쿠키 [!DNL Marketo Measure] 랜딩 페이지에 JavaScript를 추가합니다. 이 정보는 구현 중에 웹 개발 팀에 유용할 수 있습니다.

| **쿠키 이름** | **쿠키 유형** | **목적** |
|---|---|---|
| _BUID | 타사, .bizible.com 도메인에 저장됨 | 여러 클라이언트의 도메인에서 동일한 사용자를 식별하기 위한 범용 사용자 ID입니다. |
| _biz_uid | 자사 | 현재 도메인의 사용자 ID. |
| _biz_sid | 자사 | 사용자의 세션 ID입니다. |
| _biz_flagsA | 자사 | 사용자가 양식을 제출했는지, 교차 도메인 마이그레이션을 수행했는지, 뷰스루 픽셀을 전송했는지, 추적을 옵트아웃했는지 등의 여러 정보를 저장하는 단일 쿠키. |
| _biz_nA | 자사 | 시퀀스 번호 [!DNL Marketo Measure] 모든 요청에 대해, 내부 진단 용도로 포함 |
| _biz_dfsA | 자사 | 이전에 발생한 양식 제출 데이터를 임시로 저장 [!DNL bizible.js] 는 HTTPS에서 양식 추적을 사용할지 여부를 결정하는 구성 JS를 수신합니다. |
| _biz_pendingA | 자사 | 에 성공적으로 전송되지 않은 분석 데이터를 일시적으로 저장 [!DNL Marketo Measure] 아직 서버를 생성하지 않았습니다. |

JavaScript 설정 중에 WAF(Web Application Firewall) 경고가 트리거되면 사용자는 아래 예와 같이 해당 WAF 규칙을 비활성화하거나 쿠키를 허용 목록에 추가할 수 있습니다.

![](assets/marketo-measure-cookies-1.png)
