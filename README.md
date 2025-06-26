# MSc in Electronics and Technology

[![Website](https://img.shields.io/badge/Website-mscet.cut.ac.cy-blue)](https://mscet.cut.ac.cy/)
[![Hugo](https://img.shields.io/badge/Built%20with-Hugo-orange)](https://gohugo.io/)
[![Theme](https://img.shields.io/badge/Theme-Wowchemy%20Research%20Group-green)](https://wowchemy.com/hugo-themes/)

Official website for the joint **MSc in Electronics Science and Technology** program between the [Cyprus University of Technology](https://cut.ac.cy) (CUT) in Cyprus and [Hangzhou Dianzi University](https://www.hdu.edu.cn) (HDU) in China.

## About the Program

This is a collaborative master's program that combines the expertise of two leading institutions in electronics and technology education. The program offers:

- **International Collaboration**: Joint degree from CUT (Cyprus) and HDU (China)
- **Comprehensive Curriculum**: 6-semester program covering electronics, technology, and research
- **Research Focus**: Emphasis on practical research and thesis work
- **Multilingual Support**: Website available in English and Chinese

## Website Features

- **Program Information**: Detailed course structure across 6 semesters
- **Faculty Profiles**: Meet the academic staff and coordinators
- **Publications**: Latest research publications from students and faculty
- **News & Updates**: Program announcements and latest developments
- **Contact Information**: Easy access to program coordinators
- **Multilingual**: Full support for English and Chinese languages

## Technology Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Theme**: [Wowchemy Research Group Theme](https://wowchemy.com/hugo-themes/)
- **Deployment**: Netlify
- **Content Management**: Markdown-based with Hugo shortcodes

## Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (version 0.80.0 or higher)
- [Go](https://golang.org/dl/) (for Hugo modules)

### Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd mscet
   ```

2. Install Hugo modules:
   ```bash
   hugo mod get
   ```

3. Start the development server:
   ```bash
   hugo server
   ```

4. Open [http://localhost:1313](http://localhost:1313) in your browser

### Content Structure

- `content/en/` - English content
- `content/zh/` - Chinese content
- `content/en/program/` - Program information and courses
- `content/en/authors/` - Faculty profiles
- `content/en/publication/` - Research publications
- `content/en/post/` - News and announcements

## Deployment

The website is automatically deployed to Netlify when changes are pushed to the main branch. The live site is available at [https://mscet.cut.ac.cy/](https://mscet.cut.ac.cy/).

## Contributing

To update content:

1. Edit the appropriate Markdown files in the `content/` directory
2. Test locally with `hugo server`
3. Commit and push changes
4. Netlify will automatically rebuild and deploy

## Contact

For questions about the program or website:
- **Program Coordinators**: See the [People](https://mscet.cut.ac.cy/people) page
- **Technical Issues**: Contact the web development team

## License

This website is built using the [Wowchemy Research Group Theme](https://github.com/wowchemy/starter-hugo-research-group) which is licensed under the MIT License.
