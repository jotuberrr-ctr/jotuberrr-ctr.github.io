---
layout: post
title: "글은 AI가 새벽에 써 놓고, 나는 승인 버튼만 누릅니다"
series: "실험"
part: 1
date: 2026-09-06 09:00:00 +0900
verified: true
tags: [자동화, 승인, 예약작업]
---

## 1. 문제

회사를 다니면서 블로그를 운영하려면 글 한 편에 3–5시간이 듭니다. 주제 정하기, 자료 찾기, 쓰기, 다듬기, 올리기. 이 중에서 제가 꼭 해야 하는 일은 사실 "이 글을 내보내도 되는가"를 판단하는 것 하나뿐이었습니다. 나머지는 넘길 수 있는지 확인해 보기로 했습니다.

## 2. 구조

<figure>
<svg viewBox="0 0 760 200" xmlns="http://www.w3.org/2000/svg" font-family="IBM Plex Sans KR, sans-serif" font-size="13">
  <defs><marker id="a" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="#6E727C"/></marker></defs>
  <rect x="16" y="50" width="150" height="80" rx="4" fill="#E6E9EE" stroke="#6E727C"/>
  <text x="91" y="82" text-anchor="middle" font-weight="600" fill="#121317">주제 큐</text><text x="91" y="104" text-anchor="middle" fill="#6E727C">제목 한 줄 · 사람</text>
  <rect x="206" y="50" width="150" height="80" rx="4" fill="#DCE1FB" stroke="#2742E6"/>
  <text x="281" y="82" text-anchor="middle" font-weight="600" fill="#121317">예약 작업</text><text x="281" y="104" text-anchor="middle" fill="#6E727C">화·금 06:00 · AI</text>
  <rect x="396" y="50" width="150" height="80" rx="4" fill="#E6E9EE" stroke="#121317" stroke-width="1.5"/>
  <text x="471" y="82" text-anchor="middle" font-weight="600" fill="#121317">승인</text><text x="471" y="104" text-anchor="middle" fill="#6E727C">읽고 누른다 · 사람</text>
  <rect x="586" y="50" width="150" height="80" rx="4" fill="#DCE1FB" stroke="#2742E6"/>
  <text x="661" y="82" text-anchor="middle" font-weight="600" fill="#121317">발행</text><text x="661" y="104" text-anchor="middle" fill="#6E727C">승인분만 · 자동</text>
  <line x1="166" y1="90" x2="204" y2="90" stroke="#6E727C" stroke-width="1.4" marker-end="url(#a)"/>
  <line x1="356" y1="90" x2="394" y2="90" stroke="#6E727C" stroke-width="1.4" marker-end="url(#a)"/>
  <line x1="546" y1="90" x2="584" y2="90" stroke="#6E727C" stroke-width="1.4" marker-end="url(#a)"/>
  <path d="M471 130 V 165 H 281 V 132" fill="none" stroke="#6E727C" stroke-width="1.2" stroke-dasharray="4 3" marker-end="url(#a)"/>
  <text x="376" y="182" text-anchor="middle" fill="#6E727C">반려 사유 → 다음 생성에 반영</text>
</svg>
<figcaption>파란 칸이 AI, 회색 칸이 사람. 사람이 있는 칸은 두 개뿐이고 둘 다 "쓰기"가 아닙니다.</figcaption>
</figure>

주제 큐에는 제목 한 줄과 메모(다룰 것·피할 것)만 적습니다. 예약 작업이 화·금 새벽에 큐 맨 위 주제를 꺼내 지침 파일대로 초안·도식·검증표를 만들어 대시보드의 "대기"에 넣습니다. 저는 대기함을 열어 읽고 승인·수정 요청·반려 중 하나를 누릅니다. 발행 작업은 **승인된 것만** 사이트에 올립니다. 승인하지 않은 글이 나가는 경로는 없습니다.

## 3. 결과

| 항목 | 값 | 확인 |
|---|---|---|
| 주제 → 초안 완성 | 11분 | 작업 로그 (2026-09-05) |
| 자동 생성된 검증 항목 | 12개 | 초안 검증표 |
| AI가 스스로 `[값 검증 필요]`로 표시한 곳 | 17곳 | 초안 본문 |
| 지어낸 수치 | 0 | 저자 확인 |
| 사람이 쓴 시간 | 승인 검토 약 30분 | 저자 기록 |

가장 중요한 숫자는 17입니다. 지침 파일에 "출처나 실행 결과가 아니면 값을 쓰지 말고 `[값 검증 필요]`로 남겨라"라는 한 줄을 넣었더니, 첫 초안에서 AI가 확신 없는 값 17곳을 스스로 표시했습니다. 속도보다 이게 먼저입니다.

실패도 있었습니다. 발행 작업이 새벽에 브라우저 권한 창 앞에서 30분 멈춘 것입니다. 완전 자동을 고집하는 대신 "본문 복사 + 커밋 화면 열기" 버튼 하나로 물러났고, 지금은 30초면 어디서든 발행됩니다. 자동화율 90%가 100%보다 오래 갑니다.

## 4. 다시 할 수 있게

필요한 것은 세 가지입니다. 지침 파일([전문 공개](/rules/)), 주제 큐와 승인 버튼이 있는 대시보드, 그리고 정해진 시각에 도는 예약 작업. 도구는 무엇이든 됩니다. 핵심은 **생성과 발행 사이에 사람의 버튼을 하나 두는 것**입니다.

## 발행 전 검증표

| # | 항목 | 유형 | 확인 방법 | 상태 |
|---|---|---|---|---|
| 1 | 초안 생성 11분 | 실행 결과 | 작업 로그 | [x] |
| 2 | 검증 항목 12개 · 표시 17곳 | 실행 결과 | 초안 원문 | [x] |
| 3 | 발행 작업 30분 대기 사건 | 실행 결과 | 작업 상태 기록 | [x] |
| 4 | 회사·고객사 식별 정보 없음 | 저자 확인 | 본문 재독 | [x] |

*이 글의 초안과 도식은 Claude의 보조를 받아 작성했습니다. 수치는 실제로 실행해 나온 값만 쓰고, 확인되지 않은 값은 [값 검증 필요]로 남깁니다. 오류 제보는 48시간 내 확인하고 정정 기록을 공개합니다.*
