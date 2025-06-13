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
  - block: markdown
    content:
      title: '💻 About Me'
      subtitle: ''
      text: |-
        I'm a Software Developer specializing in full-stack development with a passion for creating efficient, scalable applications. My expertise spans modern web technologies, AI/ML applications, and collaborative software solutions.

        With experience in both startup and enterprise environments, I've delivered critical security solutions, performance optimizations, and innovative features that directly impact business outcomes.
        
        I'm always excited to work on challenging projects and collaborate with teams that push the boundaries of technology. Let's connect! 🚀
    design:
      columns: '1'
  - block: collection
    id: projects
    content:
      title: Featured Projects
      filters:
        folders:
          - project
        featured_only: false
    design:
      view: article-grid
      columns: 2
  - block: markdown
    content:
      title: '🛠️ Technical Skills'
      subtitle: ''
      text: |-
        ### Frontend Development
        TypeScript, JavaScript, React, Svelte/SvelteKit, HTML/CSS, Tailwind CSS, MUI
        
        ### Backend Development
        Python, Java, Spring Boot, SQL, REST APIs, Database Management
        
        ### DevOps & Tools
        Docker, Linux/Bash, Network Protocols (TCP/IP), CI/CD, Auth 2.0, Jenkins
        
        ### Specialized Skills
        Technical Writing, UI/UX Design, Neural Networks, Prompt Engineering, LLM Integration
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
