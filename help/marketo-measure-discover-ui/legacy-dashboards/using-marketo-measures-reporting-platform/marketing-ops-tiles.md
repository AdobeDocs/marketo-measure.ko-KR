---
unique-page-id: 34406495
description: 마케팅 운영 타일 - [!DNL Marketo Measure] - 제품 설명서
title: 마케팅 운영 타일
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
feature: Reporting
source-git-commit: e24e01a03218252c06c9a776e0519afbddbe2b8c
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 마케팅 운영 타일 {#marketing-ops-tiles}

마케팅 Ops를 통해 유효성 검사 및 진단 가능 [!DNL Marketo Measure] 리드, 연락처, 계정, 캠페인 및 기회에 대한 개별 접점에 대한 완전한 가시성이 있는 데이터.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><br></td> 
   <td><p><strong>계정 ID</strong></p></td> 
   <td><p><strong>계정 이름</strong></p></td> 
   <td><p><strong>Opp ID</strong></p></td> 
   <td><p><strong>Opp 이름</strong></p></td> 
   <td><p><strong>잠재 고객 또는 연락처 ID</strong></p></td> 
   <td><p><strong>잠재 고객 또는 연락처 이메일</strong></p></td> 
   <td><p><strong>캠페인 ID</strong></p></td> 
   <td><p><strong>Opp 원</strong></p></td> 
   <td><p><strong>Opp 생성일</strong></p></td> 
   <td><p><strong>Opp 종료일</strong></p></td> 
   <td><p><strong>접점 날짜</strong></p></td> 
   <td><p><strong>속성 모델</strong></p></td> 
  </tr> 
  <tr> 
   <td><p><strong>계정</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>기회</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>연락처</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>잠재 고객</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>캠페인</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
 </tbody> 
</table>

## 계정 타일 {#account-tile}

![](assets/one-1.png)

지정된 계정과 관련된 다음 데이터를 표시합니다.

**계정에 터치포인트 데이터가 있어야 합니다(ABM이 활성화된 경우에만 해당).**

-Account ID: CRM의 계정 ID

-Account Name: CRM의 계정 이름

-만든 날짜: CRM에서 계정의 만든 날짜

* 드릴다운: 시간, 분, 시간별로 생성된 날짜 참조

-웹 사이트: 계정의 웹 사이트 필드에 있는 값

-참여 등급: 다음으로 채워진 PES(예측 참여 점수) [!DNL Marketo Measure]^1

-Opportunities: 계정에 연결된 Opportunity 수

* 드릴다운: 연관된 Opportunity에 대한 세부 정보를 참조하십시오.

-연락처: 이 계정에 나열된 연락처 수

* 드릴다운: 연관된 담당자에 대한 상세내역을 참조하십시오.

-Leads: 가망 고객 대 계정 매핑^1을(를) 통해 이 계정에 매핑된 가망 고객 수

* 드릴다운: 계정에 매핑된 잠재 고객에 대한 세부 정보를 확인합니다.

-속성 접점: 계정에 대한 구매자 속성 접점 수

* 드릴다운: 구매자 속성 접점 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형, 속성 모델)를 참조하십시오.

-터치포인트: 이 계정의 연락처에 있는 터치포인트의 수^2

* 드릴다운: 계정의 터치포인트 세부 사항(ID, 이메일, 터치포인트 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형)에서 터치포인트를 참조하십시오.

>[!NOTE]
>
>ABM이 있는 경우 Lead에서 Account Mapping으로 매핑된 Lead 관련 터치 포인트가 표시됩니다.

## 영업 기회 타일 {#opportunity-tile}

![](assets/two-1.png)

지정된 영업 기회와 관련된 다음 데이터를 표시합니다.

-Opportunity ID: CRM의 Opportunity ID

-Opportunity Name: CRM에 있는 Opportunity 이름

-Account Name: 영업 기회에 연결된 계정 이름

-Created Date: CRM에 Opportunity 가 Created Date

드릴다운: 시간, 분, 시간별로 생성된 날짜 참조

-Close Date: CRM에 있는 Opportunity 의 Close Date

드릴다운: 시간, 분, 시간별 종료 일자 참조

-Amount: Opportunity 의 총 금액

-Contacts: Opportunity 와 연관된 Contact 수

드릴다운: 연관된 담당자에 대한 상세내역을 참조하십시오.

-속성 접점: 관련 구매자 속성 접점 수

드릴다운: 구매자 속성 접점 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형, 속성 모델)를 참조하십시오.

## 연락처 타일 {#contacts-tile}

![](assets/three-1.png)

지정된 연락처와 관련된 다음 데이터를 표시합니다.

-연락처 ID: CRM의 연락처 ID

-Email: 연락처 레코드 이메일 주소

-만든 날짜: CRM에서 연락처의 만든 날짜

* 드릴다운: 시간, 분, 시간별로 생성된 날짜 참조

-Account Name: 연락처에 연결된 계정 이름

-속성 접점: 연락처에 대한 구매자 속성 접점 수

* 드릴다운: 구매자 속성 접점 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형, 속성 모델)를 참조하십시오.

-터치포인트: 연락처에 대한 구매자 터치포인트 수

* 드릴다운: 거래처의 연락처 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형)를 참조하십시오.

## 리드 타일 {#leads-tile}

![](assets/four-1.png)

지정된 리드와 관련된 다음 데이터를 표시합니다.

-잠재 고객 ID: CRM의 잠재 고객 ID

-Email: 잠재 고객 레코드 이메일 주소

-생성 날짜: CRM에서 잠재 고객을 만든 시간

* 드릴다운: 시간, 분, 시간별로 생성된 날짜 참조

-Company (from Lead): 고객이 채운 CRM의 레코드에 나열되는 회사입니다

-Account Name: 계정 이름 [!DNL Marketo Measure] 리드-계정 매핑을 기반으로 채우기

-터치포인트: 리드와 연결된 터치포인트 수

* 드릴다운: 거래처의 연락처 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형)를 참조하십시오.

## 캠페인 타일 {#campaigns-tile}

![](assets/five-1.png)

지정된 Campaign과 관련된 다음 데이터를 표시합니다.

-Campaign ID: CRM의 Campaign ID

-Campaign Name: CRM의 캠페인 이름

-캠페인 지출: 지출 [!DNL Marketo Measure] 이(가) 캠페인에 연결된 을(를) 기록함

-속성 모델: 선택한 모델을 기반으로 적절한 속성을 표시합니다.

-속성 접점: 캠페인에 연결된 구매자 속성 접점 수입니다.

* 드릴다운: 구매자 속성 접점 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형, 속성 모델)를 참조하십시오.

-터치포인트: 캠페인에 연결된 터치포인트 수

* 드릴다운: 거래처의 연락처 세부 정보(ID, 이메일, 접점 날짜, 계정 이름, 캠페인, 채널, 하위 채널, 마케팅 터치 유형)를 참조하십시오.
