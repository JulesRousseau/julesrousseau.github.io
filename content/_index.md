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
        color: white
        image:
          # Add your image background to `assets/media/`.
          filename: stacked-peaks.svg
          filters:
            brightness: 1.0
          size: cover
          position: center
          parallax: true
  - block: markdown
    content:
      title: "Job Seeker"
      subtitle: ""
      text: |-
        **Security engineering position**
    
        As a newcomer to the job market in cryptography, I am seeking my first experience to enhance and develop my practical knowledge in this field. I am driven by both the theory of cryptography and the practice of cybersecurity, which is why I aspire to join a company as an evaluator or an integrator. Specifically, my internship allowed me to work on lightweight encryption algorithms, and I see myself continuing in this domain.
    design:
      columns: '1'
  #- block: collection
  #  id: news
  #  content:
   #   title: Recent News
    #  subtitle: ''
     # text: ''
      # Page type to display. E.g. post, talk, publication...
      #page_type: post
      # Choose how many pages you would like to display (0 = all pages)
      #count: 5
      # Filter on criteria
      #filters:
       # author: ""
       # category: ""
       # tag: ""
       # exclude_featured: false
       # exclude_future: false
       # exclude_past: false
       # publication_type: ""
      # Choose how many pages you would like to offset by
      #offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      #order: desc
    design:
      # Choose a layout view
      view: date-title-summary
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700"
        css_style: ""
---
