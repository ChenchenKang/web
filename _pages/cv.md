---
layout: single
title: "CV"
permalink: /cv/
author_profile: true
---

<!-- Keep the filename stable so your site link never changes -->
{% assign cv_url = '/assets/files/ChenchenKang_CV.pdf' | relative_url %}

<div style="margin: 1rem 0;">
  <a class="btn btn--primary" href="{{ cv_url }}" target="_blank" rel="noopener">
    🔽 Download CV (PDF)
  </a>
</div>

<!-- Responsive embedded PDF -->
<div style="border:1px solid #e5e7eb; border-radius:0.5rem; overflow:hidden;">
  <object data="{{ cv_url }}" type="application/pdf" width="100%" height="900px">
    <iframe src="{{ cv_url }}" width="100%" height="900px"></iframe>
  </object>
</div>

<p style="margin-top:0.75rem; font-size:0.9rem; color:#64748b;">
  If the PDF doesn’t display in your browser (mobile Safari, etc.), 
  <a href="{{ cv_url }}" target="_blank" rel="noopener">open it in a new tab</a>.
</p>
