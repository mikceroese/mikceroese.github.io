---
layout: default
---

<div class="content">
  <div class="tabs">
    <button class="tab" id="research_tab" onclick="showTab('research')">Research</button>
    <button class="tab" id="resumee_tab" onclick="showTab('resumee')">Resumee</button>
    <button class="tab" id="personal_tab" onclick="showTab('personal')">Personal</button>
  </div>

  <div id="research" class="tab-content">
    {% assign posts = site.posts | where: 'category', 'research' %}
    {% for post in posts %}
      <h2>{{ post.title }}</h2>
      <p>{{ post.date | date: "%B %d, %Y" }}</p>
      <div>{{ post.content }}</div>
      <hr/>
    {% endfor %}
  </div>

  <div id="resumee" class="tab-content" style="display:none;">
    {% assign posts = site.posts | where: 'category', 'resumee' %}
    {% for post in posts %}
      <h2>{{ post.title }}</h2>
      <div>{{ post.content }}</div>
      <hr/>
    {% endfor %}
  </div>

  <div id="personal" class="tab-content" style="display:none;">
    {% assign posts = site.posts | where: 'category', 'personal' %}
    {% for post in posts %}
      <h2>{{ post.title }}</h2>
      <div>{{ post.content }}</div>
      <hr/>
    {% endfor %}
  </div>
</div>

<script>
function showTab(tabId) {
  document.querySelectorAll('.tab-content').forEach(t => t.style.display = 'none');
  document.getElementById(tabId).style.display = 'block';
  document.querySelectorAll('.tab').forEach(t => t.style.backgroundColor = '#ffc0cb');
  let buttonId = tabId+"_tab"
  document.getElementById(buttonId).style.backgroundColor = '#f8e7c7';
}
</script>
