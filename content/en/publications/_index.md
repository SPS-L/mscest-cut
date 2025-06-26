---
# An instance of the Pages widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: pages

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 90

title: Publications
subtitle: ''

content:
  # Filter on criteria
  filters:
    # The folders to display content from
    folders:
      - publication
    # Only show content with these publication types (leave empty for all types)
    publication_types:
      - '1'  # Journal articles
      - '2'  # Conference papers
      - '3'  # Book chapters
      - '4'  # Books
      - '5'  # Reports
      - '6'  # Theses
    # Exclude publications that would normally be shown
    exclude_featured: false
    # Exclude publications that match these criteria
    exclude:
      - publication_type: '2'
      - author: 'admin'
  # Choose how many pages you would like to display (0 = all pages)
  count: 5
  # Choose a page size to display
  page_size: 10
  # Choose how pages should be sorted
  sort_by: 'Date'
  sort_ascending: false

design:
  # Choose a view for the listings:
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   4 = Citation (publication only)
  view: 4
  columns: '2'
--- 