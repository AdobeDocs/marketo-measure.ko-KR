---
description: Passport 대시보드 - [!DNL Marketo Measure] - 제품
title: Passport 대시보드
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 3%

---

# Passport 대시보드 {#passport-dashboard}

Passport 대시보드는 마케터에게 지정된 기간 내에 다양한 단계를 통해 전환되는 잠재 고객, 연락처 및 기회에 대한 동적 보기를 제공합니다. 특정 날짜에 대해 필터링하면 해당 날짜의 레코드 스냅샷을 가져올 수도 있습니다.

질문과 대답은 다음과 같습니다.

* 선택한 날에 각 비종료 단계에 얼마나 많은 리드, 연락처 또는 기회가 존재했습니까?
* 지정된 기간 동안 각 임시 단계를 통해 진행된 개별 리드 또는 연락처의 수는 몇 개입니까?
   * _예_: 잠재 고객 A가 2023년 1월 1일에 단계 1에 있다가 2023년 3월 31일까지 단계 5로 발전하면 2023년 1분기 여권 분석은 1~5단계에서 잠재 고객 A를 계산합니다.
* 주어진 기간 동안 각 임시 단계를 통해 전달된 고유한 Opportunity 는 몇 개입니까?

<table style="table-layout:auto"> 
<tbody>
<tr> 
   <th>구성 요소</th> 
   <th>설명</th>
   <th>날짜 유형</th>
   <th>드릴스루 필드</th>
   <th>필터</th>
  </tr>
  <tr>
    <td>기회</td>
    <td><li>각 단계는 주어진 시간대에 해당 단계를 통과한 BAT가 있는 Opportunity 수를 보여줍니다.</li>
<ul style="padding-left: 30px;"><li>Opportunity 가 해당 범위 내에서 여러 단계를 거치는 경우, 해당 단계를 거치는 모든 단계에서 계산됩니다.</li></ul>
<li>"Closed Won", "Closed Lost" 등의 터미널 단계는 제외된다.</li>
<li>시작 날짜와 종료 날짜는 모두 포괄적입니다.</li>
<br/><img src="assets/passport-dashboard-1.png" width="600"></td>
    <td rowspan="2">전환 날짜</td>
    <td></td>
    <td rowspan="2"><li>날짜</li>
<li>채널</li>
<li>부채널</li>
<li>캠페인</li>
<li>세그먼트</li></td>
  </tr>
  <tr>
    <td>잠재 고객/연락처</td>
    <td><li>각 단계에는 주어진 기간 내에 BT 를 통과한 잠재 고객 또는 연락처 수가 표시됩니다.</li>
<ul style="padding-left: 30px;"><li>"잠재 고객" 또는 "연락처"를 표시할지 여부는 설정 &gt; 속성 설정 &gt; 기본 대시보드 개체에 설정된 기본 설정에 따라 결정됩니다.</li></ul>
<li>"Closed Won", "Closed Lost" 등의 터미널 단계는 제외된다.</li>
<li>시작 날짜와 종료 날짜는 모두 포괄적입니다.</li>
<br/><img src="assets/passport-dashboard-2.png" width="600"></td>
    <td><li>잠재 고객/연락처 Id</li>
<li>잠재 고객/연락처 이메일</li>
<li>제작일</li>
<li>현재 단계</li>
<li>전환 입력 날짜</li>
<li>전환 종료 날짜</li></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[대시보드 기본 사항 살펴보기](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
