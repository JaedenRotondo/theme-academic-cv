---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
    design:
      css_class: dark
      background:
        color: black
        image:
          # Add your image background to `assets/media/`.
          filename: stacked-peaks.svg
          filters:
            brightness: 1.0
          size: cover
          position: center
          parallax: false
  - block: collection
    id: projects
    content:
      title: Featured Projects
      filters:
        folders:
          - project
        featured_only: false
    design:
      view: showcase
      columns: 2
  - block: markdown
    content:
      title: '🛠️ Technical Skills'
      subtitle: ''
      text: |-
        ### Frontend Development
        TypeScript, JavaScript, React, Ant Design, MUI, Svelte/SvelteKit, HTML/CSS, Tailwind CSS

        ### Backend Development
        Node.js, Python, Java/Spring Boot, PostgreSQL, Prisma ORM, REST APIs, Microservices

        ### DevOps & Tools
        Docker, Linux/Bash, Network Protocols (TCP/IP), CI/CD, Auth 2.0, Jenkins, Git

        ### Specialized Skills
        Linear Programming, Operations Research, Technical Writing, UI/UX Design, AI/ML, LLM Integration, OWASP Security
    design:
      columns: '2'
  - block: collection
    id: posts
    content:
      title: Blog Posts
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: post
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: date-title-summary
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
  - block: cta-card
    content:
      title: Let's Connect!
      text: |-
        I'm always interested in discussing new opportunities, collaborating on innovative projects, or just having a chat about technology.
        
        Feel free to reach out via email or connect with me on LinkedIn!
      button:
        text: Contact Me
        url: 'mailto:jaeden@rotondo.dev'
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700"
        css_style: ""
---
