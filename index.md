---
layout: homepage
title: 
---
<p align="center">
  <img src="{{ '/assets/id_pic.png' | relative_url }}" alt="Profile picture" class="profile-pic" />
</p>

<div class="social-links">
  <a href="mailto:coakeben@gmail.com" title="Email" target="_blank" rel="noopener">
    <i class="fa-solid fa-envelope"></i>
  </a>
  <a href="https://github.com/bjcke" title="GitHub" target="_blank" rel="noopener">
    <i class="fa-brands fa-github"></i>
  </a>
  <a href="https://uk.linkedin.com/in/bencoake" title="LinkedIn" target="_blank" rel="noopener">
    <i class="fa-brands fa-linkedin"></i>
  </a>
</div>

<style>
.profile-pic {
  width: 150px;         /* adjust size */
  height: 150px;        /* same as width to keep circle */
  object-fit: cover;    /* crop and fill */
  border-radius: 50%;   /* makes it a circle */
  display: block;
  margin: 0 auto;       /* centers block element */
  border: 3px solid #ccc; /* optional: add a border */
}

.social-links {
  text-align: center;
  margin-top: 1rem;
}

.social-links a {
  margin: 0 10px;
  color:rgb(186, 186, 186);
  font-size: 1.5rem;
  text-decoration: none;
  transition: color 0.2s ease;
}

.social-links a:hover {
  color: #d80909; /* Customize hover color */
}
</style>
