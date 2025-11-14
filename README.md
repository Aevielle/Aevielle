<h1 align="center">Hi, I'm Kim Aeriel 👋</h1>

---

<p align="center">
  <em>💻 Computer Science Student | 🤔 Exploring New Tech | 📖 Learning by Building</em>
</p>

<p align="center">
  <a href="mailto:your.email@example.com" title="Email">
    <img alt="email" src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  <a href="https://www.linkedin.com/in/your-linkedin" title="LinkedIn">
    <img alt="linkedin" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://github.com/your-github" title="GitHub">
    <img alt="github" src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</p>

---

### 🎓 Education

- **Bachelor of Science in Computer Science**
  - [New Era University] (2024 – Present)

---

### 📜 Certificates

| Certificate | Issued By | Year |
|---|---:|---:|
| [Introduction to Cybersecurity](https://drive.google.com/file/d/1pYepQ4Q4aguL3iDqsbrg-kimREEIAFQX/view?usp=sharing) | Cisco Net Acad | 2025 |
| [SQL Database 101](https://drive.google.com/file/d/1TqRAgKz5aN1TlBJ-QkI9A-omdJ8-9Esk/view?usp=sharing) | Cognitive Class AI | 2025 |

### 🛠 Skills

- **Programming Languages:** Java, SQL, Python, HTML, CSS, TypeScript, JavaScript, Shell  
- **Databases & Services:** IBM DB2 Cloud, Supabase, MongoDB  
- **Frameworks & Tools:** React, Node.js, Lucidchart, Figma, Canva Education, Notion  
- **Dev Tools:** Visual Studio Code, Google Workspace, Git, Microsoft Office, Vercel, Heroku

<p align="center">
  <img alt="js" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" />
  <img alt="ts" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" />
  <img alt="react" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" />
  <img alt="node" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" />
  <img alt="mongodb" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original.svg" />
  <img alt="python" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" />
  <img alt="java" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" />
  <img alt="vscode" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" />
</p>

---

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
