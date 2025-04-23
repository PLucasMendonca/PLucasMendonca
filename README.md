## Olá! Eu sou o Lucas Mendonça


- 🔭 Atualmente faço estágio na Sempre Técnologia.
- 📕 Cursando o 7º semestre de Ciências da Computação.
- 🏫 Faculdade:Instituto de Educação Superior de Brasília (IESB)
- 💬 Me pergunte sobre qualquer coisa
- ⚡ Curiosidade tenho 23 anos 
-->
<div align="center">
  <a href="https://github.com/plucasmendonca">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=plucasmendonca&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
  <img height="120em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=plucasmendonca&layout=compact&langs_count=7&theme=dark"/>
</div>
<div style="display: inline_block"><br>
<img height="60em" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" />
<img height="60em" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" />
<img height="60em" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" /> 
<img height="60em" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" /> 
</div>
    <div align="right">
<img src="https://user-images.githubusercontent.com/96083134/148793580-649c59b5-c20c-4204-984d-c2b2db6dfc77.png" width="200px" />
</div>
  
  ##
  <div> 
  <a href="https://instagram.com/lucas_s.mendonca" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/lucas-mendonça-031a7222a" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
 <a href="https://discord.gg/qvprpCgR" target="_blank"><img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white" target="_blank"></a> 
      <a href = "mailto:p.lucas.santos.mendonca@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
    <a href="https://www.twitch.tv/luukistar88" target="_blank"><img src="https://img.shields.io/badge/Twitch-9146FF?style=for-the-badge&logo=twitch&logoColor=white" target="_blank"></a>



# Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: PLucasMendonca
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
