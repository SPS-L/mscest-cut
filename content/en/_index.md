---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: Welcome!
      image:
        filename: welcome.jpg
      text: |
        <br>
        
        This is the official website of the joint MSc in Electronics Science and Technology between the [Cyprus University of Technology](https://cut.ac.cy) in Cyprus and the [Hangzhou Dianzi University](https://www.hdu.edu.cn) in China.
  
  - block: collection
    content:
      title: Latest News
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: post
    design:
      view: compact
      columns: '2'

  - block: pages
    content:
      title: Publications
      subtitle: ''
      filters:
        folders:
          - publications
        publication_types:
          - '1'  # Journal articles
          - '2'  # Conference papers
          - '3'  # Book chapters
          - '4'  # Books
          - '5'  # Reports
          - '6'  # Theses
        exclude_featured: false
        exclude:
          - publication_type: '2'
          - author: 'admin'
      count: 5
      page_size: 10
      sort_by: 'Date'
      sort_ascending: false
    design:
      view: 3
      columns: '2'
  
  # - block: features
  #   content:
  #     title: My Interests
  #     subtitle: Section subtitle
  #     text: Section text
  #     items:
  #       - name: R
  #         description: 90%
  #         icon: r-project
  #         icon_pack: fab
  #       - name: Statistics
  #         description: 100%
  #         icon: chart-line
  #         icon_pack: fas
  #       - name: Photography
  #         description: 10%
  #         icon: camera-retro
  #         icon_pack: fas
  # - block: contact
  #   content:
  #     title: Contact
  #     text: 
  #     email: test@example.org
  #     phone: 888 888 88 88
      # address:
      #   street: 450 Serra Mall
      #   city: Stanford
      #   region: CA
      #   postcode: '94305'
      #   country: United States
      #   country_code: US
      # coordinates:
      #   latitude: '37.4275'
      #   longitude: '-122.1697'
      # directions: Enter Building 1 and take the stairs to Office 200 on Floor 2
      # office_hours:
      #   - 'Monday 10:00 to 13:00'
      #   - 'Wednesday 09:00 to 10:00'
      # appointment_url: 'https://calendly.com'
      # contact_links:
      #  - icon: comments
      #    icon_pack: fas
      #    name: Discuss on Forum
      #    link: 'https://discourse.gohugo.io'
    
      # Automatically link email and phone or display as text?
      autolink: true
    
      # Email form provider
      # form:
      #   provider: netlify
      #   formspree:
      #     id:
      #   netlify:
      #     # Enable CAPTCHA challenge to reduce spam?
      #     captcha: false
    design:
      columns: '2'
---