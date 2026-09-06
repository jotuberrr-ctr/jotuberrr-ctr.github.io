---
layout: default
title: 실험
---
<section class="hero">
<div class="eyebrow">jotuber · 자동화 실험실</div>
<h1 class="big">회사를 다니면서,<br>일은 <em>AI가 하고</em> 나는 승인만 합니다</h1>
<p class="lede">글·강의·카드뉴스가 만들어지는 과정을 실제로 자동화하고, 걸린 시간과 실패까지 숫자로 남깁니다. 남의 팁을 요약하지 않습니다. 직접 만들고 돌린 것만 씁니다.</p>
<div class="pillars">
  <div class="pillar"><b>만든다</b><span>주제 한 줄 → AI 초안 → 승인 → 발행. 사람의 일은 주 30분.</span></div>
  <div class="pillar"><b>숫자로 본다</b><span>걸린 시간, 자동 생성된 검증 항목 수, AI가 스스로 표시한 '확인 필요' 개수.</span></div>
  <div class="pillar"><b>선을 지킨다</b><span>회사 자료 0, 미검증 값 확정 어투 금지, AI 사용 공개.</span></div>
</div>
</section>

<h2>실험 기록</h2>
{% if site.posts.size == 0 %}
<p class="lede">첫 기록 준비 중 — 실험 #01 「글은 AI가 새벽에 써 놓고, 나는 승인 버튼만 누릅니다」가 먼저 올라옵니다. 인스타그램 <a href="{{ site.instagram_url }}" target="_blank" rel="noopener">@jotuberrr</a>에 요약본이 먼저 게시됩니다.</p>
{% endif %}
<ul class="post-list">
{% for post in site.posts %}
  <li><span class="no">#{{ post.part | default: forloop.rindex }}</span><div><a class="t" href="{{ post.url | relative_url }}">{{ post.title }}</a><div class="m">{{ post.date | date: "%Y-%m-%d" }}{% if post.verified %} · 실행·검증 완료{% else %} · 검증 전 초안{% endif %}</div></div></li>
{% endfor %}
</ul>

{% include subscribe.html %}
