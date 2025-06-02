---
title: "Projects"
permalink: /projects/
layout: single
---

<!-- FILTER BUTTONS -->
<div id="filter-bar">
  <button class="filter-btn" data-type="All">All</button>
  <button class="filter-btn" data-type="Academic">Academic</button>
  <!-- button class="filter-btn" data-type="Professional">Professional</button>
  <!-- Add more types as needed -->
</div>

<!-- PROJECT GRID -->
<div class="project-grid">
  {% assign sorted_projects = site.projects | sort: "submission" | reverse %}
  {% for project in sorted_projects %}
  <div class="project-card" data-type="{{ project.type }}">
    <div class="project-tags">
      {% for tag in project.tags %}
        <span class="tag">{{ tag }}</span>
      {% endfor %}
      <span class="type-pill">{{ project.type }}</span>
    </div>
    <div class="project-title">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </div>
  </div>
  {% endfor %}
</div>

<!-- JS FILTERING -->
<script>
  const buttons = document.querySelectorAll('.filter-btn');
  const cards = document.querySelectorAll('.project-card');

  buttons.forEach(btn => {
    btn.addEventListener('click', () => {
      const type = btn.dataset.type;
      cards.forEach(card => {
        card.style.display = (type === "All" || card.dataset.type === type) ? 'flex' : 'none';
      });
    });
  });
</script>

<!-- STYLING -->
<style>
  :root {
    --red: #ff0040; /* Your neon red */
    --black: #0d0d0d; /* Match your dark background */
    --text: #ffffff;
  }

  body {
    color: var(--text);
  }

  #filter-bar {
    margin-bottom: 1.5rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .filter-btn {
    background-color: transparent;
    border: 2px solid var(--red);
    color: var(--text);
    border-radius: 999px;
    padding: 0.25rem 0.75rem;
    font-size: 0.85rem;
    cursor: pointer;
    transition: background 0.2s, color 0.2s;
  }

  .filter-btn:hover {
    background-color: var(--red);
    color: var(--black);
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1.25rem;
  }

  .project-card {
    background-color: transparent;
    border: 2px solid var(--red);
    border-radius: 1rem;
    padding: 1.5rem 1rem 1rem 1rem; /* top padding increased */
    color: var(--text);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    position: relative;
    min-height: 180px;
  }

  .project-tags {
    position: absolute;
    top: 0.5rem;
    left: 0.5rem;
    right: 0.5rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.3rem;
    padding-right: 0.25rem;  /* optional breathing room */
  }

  .tag {
    background-color: var(--red);
    color: var(--black);
    font-size: 0.65rem;
    padding: 0.2rem 0.5rem;
    border-radius: 999px;
    font-weight: bold;
  }

  .type-pill {
    background-color: transparent;
    border: 2px solid var(--red);
    color: var(--text);
    font-size: 0.65rem;
    padding: 0.2rem 0.5rem;
    border-radius: 999px;
    font-weight: bold;
  }

  .project-title {
    margin-top: auto;
    font-size: 1rem;
    padding-top: 1.5rem;
  }

  .project-title a {
    color: var(--red);
    text-decoration: none;
    font-weight: bold;
  }

  .project-title a:hover {
    text-decoration: underline;
  }
</style>
