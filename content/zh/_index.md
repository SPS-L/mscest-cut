---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: 欢迎！
      image:
        filename: welcome.jpg
      text: |
        <br>
        
        这是塞浦路斯 [塞浦路斯理工大学](https://cut.ac.cy) 与中国 [杭州电子科技大学](https://www.hdu.edu.cn) 电子科学与技术联合硕士项目的官方网站。
  
  - block: collection
    content:
      title: 最新消息
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

  - block: collection
    content:
      title: 最新出版物
      subtitle: "[查看完整列表](publication/)"
      content_type: publication
      filters:
        publication_types:
          - '1'  # 期刊论文
          - '2'  # 会议论文
          - '3'  # 预印本
          - '4'  # 报告
          - '5'  # 书籍
          - '6'  # 书籍章节
          - '7'  # 学位论文
          - '8'  # 专利
      count: 5
      page_size: 10
      sort_by: 'Date'
      sort_ascending: false
    design:
      view: citation
      columns: '2'
  
  # - block: features
  #   content:
  #     title: 我的兴趣
  #     subtitle: 章节副标题
  #     text: 章节文本
  #     items:
  #       - name: R
  #         description: 90%
  #         icon: r-project
  #         icon_pack: fab
  #       - name: 统计学
  #         description: 100%
  #         icon: chart-line
  #         icon_pack: fas
  #       - name: 摄影
  #         description: 10%
  #         icon: camera-retro
  #         icon_pack: fas
  # - block: contact
  #   content:
  #     title: 联系方式
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
