---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-10-03
type: landing

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: me
      text: ''
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md # Options: xs, sm, md, lg (default), xl
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  - block: markdown
    id: research
    content:
      title: '🔬 Research Interests'
      subtitle: ''
      text: |-
        My interests lie in **deep learning** and **computer vision**, and in making learning and graph algorithms fast enough to run on real-world data.

        Most recently I worked on **DensePCE**, an optimized exact pseudo-clique enumeration framework in C++ that combines FPCE pruning with cache-friendly graph storage and Turán-based clique seeding to speed up enumeration on large graphs.

        I'm always happy to talk about research collaborations and assistantships. Feel free to reach out 😃
    design:
      columns: '1'
  - block: collection
    id: projects
    content:
      title: Featured Projects
      filters:
        folders:
          - projects
        featured_only: true
    design:
      view: article-grid
      columns: 2
      show_date: false
      show_read_time: false
---
