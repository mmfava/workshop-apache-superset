---
theme: slides-left
header: 🐍 84ª Python Floripla
_header: ""
_footer: ""
_paginate: false
footer: Marília Melo Favalesso
paginate: true
center: teste
date: ""
link: 
created: 2025-01-03T11:37
updated: 2025-03-26T21:08
---
<!-- _class: first-slide -->

<small>🐍 84º Python Floripa</small>

# ==Apache Superset==

**Marília Melo Favalesso**

---
## <!-- fit --> Marília Melo Favalesso  

![bg right:33% width:500px](figs/me.png)

🧠 Desenvolvedora de IA | MSc | PhD

🐍 Python & Comunidades  

🐈 Gatos, pizza e bicicleta nas horas vagas
<br>
<small>📧 marilia.melo.favalesso@gmail.com</small>

<small>🔗 LinkedIn: [/mariliafavalesso](https://www.linkedin.com/in/mariliafavalesso/)</small>

<small>🔗 github: [/mmfava](https://github.com/mmfava)</small>

<small>🔗 site: [www.mariliafavalesso.com](https://github.com/mmfava)</small>

---
<!-- _class: first-slide -->
![bg](theme/slides-design/12.png)

# "*Superseter by heart*"
<div class="linha"></div><br>

Entusiasta de ferramentas Open-Source 💙

---

## Agenda

<div style="display:grid;grid-template-columns:1fr 1fr">
<div>
<p>

1. Overview  
2. Arquitetura   
3. Back-end  
4. Interface e Front-end  
5. SQL Lab 

</p>
</div>

<div>
<p>

6. Datasets
7. Charts 
8. Dashboards e Filtros  
9. Outras funcionalidades 
10. Mão na Massa  

</p>
</div>
</div>


---
<!-- _class: first-slide -->
![bg](theme/slides-design/12.png)

# Overview 
<div class="linha"></div><br>

O <b>Apache Superset</b> é uma <b>Ferramenta para Business Intelligence (BI)<br>open-source</b> que permite a exploração e visualização de dados de forma iterativa e escalável. 

---
## <!--- fit ---> Business Intelligence (BI)
<b><small>Inteligência de Negócios</small></b><br>

![bg right:30%](figs/bi-intro.png)


- Conjunto de processos, tecnologias e ferramentas que **coletam, organizam, analisam e visualizam dados**.
- Transforma dados dispersos em **informações úteis** e insights claros.
- Facilita decisões estratégicas, operacionais e táticas, permitindo ações rápidas e informadas.
- Ajuda gestores a entenderem rapidamente **o que está acontecendo e o porquê**.

<br>
<small>✨ O objetivo é o de apoiar decisões inteligentes e baseadas em fatos <br>✨~<b><u>Data-Driven</u></b>(DWx 2025)!</small>


---

## Apache Superset

![center width:2000px](figs/sistema-do-bi-2.png)

<small><center><a href="https://www.techtarget.com/searchbusinessanalytics/definition/business-intelligence-architecture">Adaptado de Yasar & Pratt 2024 (techtaget)
</a></center></small>

---

![center width:1200px drop-shadow:0,5px,10px,rgba(0,0,0,.4)](figs/apache-superset-plataform.png)


---

<center>No <b>Apache Superset</b>, a análise e visualização de dados ocorrem a partir de <b>conjuntos de dados estruturados</b> – tabelas organizadas em <b>linhas e colunas</b> – extraídas de bancos de dados compatíveis com <b>SQL</b>.</center>

<br>

![center width:1000px](figs/dados-estruturados.png)

---

<center>Os dados são manipulados e sumarizados para compor <b>visualizações interativas e personalizadas</b>.<br>O <b>Apache Superset</b> oferece <b>mais de 40 tipos de gráficos e visualizações</b>.</center>

![center width:1100px](figs/tabelas-para-graficos.png)

---

<center><b>Quando os datasets são atualizados na fonte original, o Apache Superset reflete essas mudanças de forma automática</b>, garantindo que as visualizações de dados estejam sempre atualizadas.</center><br>

![center width:1100px](figs/update-data.png)

---


<center>As visualizações geradas podem ser organizadas em <b>dashboards interativos</b>,<br>fornecendo uma visão abrangente dos dados com filtros, indicadores e relatórios dinâmicos.</center> <br> 


![center width:1200px](figs/dashboard-from-database.png)

---

<center>Os <b>dashboards</b> podem incluir tabelas e gráficos personalizados,<br>ser exportados como <b>PDFs, imagens ou relatórios automatizados</b> e<br>compartilhados com equipes para acompanhamento de métricas.</center><br>

![center width:1000px](figs/document.png)

---

![left width:1000px](figs/Pasted%20image%2020250325212046.png)<br>
*Self-serve analytics* para **todos os níveis de usuários**!<br>Oferece um construtor de visualizações e customizações **sem código**.

---

![center width:1000px](figs/interacao-outros-usuarios.png)

<center>O <b>Apache Superset</b> oferece um sistema de permissões flexível, permitindo a definição de <b>diferentes perfis de usuários</b>, cada um com níveis de acesso e funcionalidades personalizáveis, garantindo controle granular sobre a plataforma.</center><br>

---

<center>A ferramenta é um projeto de <b>código aberto (<i>open-source</i>)</b> e se beneficia de uma grande<br>comunidade de desenvolvedores e usuários que contribuem para a sua melhoria contínua.</center><br>

![center width:1000px](figs/users.png)



---
### Workflow

![center width:2000px](figs/estrutura.png)

---

### Fonte de dados

![bg right:36% width:700px](figs/database.png)  

A ferramenta se conecta a diversas fontes de dados compatíveis com **SQL**, incluindo **Presto, Trino, Athena e muitos outros**.  
<small>
✅ Suporte a **bancos relacionais e data warehouses**  
✅ Compatibilidade depende de **driver Python DB-API**  
✅ Utiliza **SQLAlchemy** para abstração e integração
</small>


---

# História

![bg right:33%](figs/max-beauchemin2.png)

 - Projeto de hackathon no Airbnb (2015) cujo objetivo era a criação de uma ferramenta para a visualização de dados em código aberto.
 - Cresceu rapidamente e superou o Tableau como principal solução de visualização de dados do Airbnb.
 - Em 2016, Superset tornou-se um projeto de código aberto completo, incubado pela Apache Software Foundation.
 - Empresas como Airbnb, Lyft e Twitter (X) são usuários corporativos do Superset.

<br> <div style="border: 1px solid #ccc; padding: 15px; padding-left:60px; font-size: 0.7em; background-color: #f8f8f8;"> Maxime criou o **Apache Superset** para superar as limitações do **Tableau** no Airbnb, que não suportava **Presto** e **Druid**, além de ser caro e pouco escalável. O objetivo era desenvolver uma solução **open-source**, flexível e acessível para análise e visualização de dados. [🔗](https://maximebeauchemin.medium.com/the-future-of-business-intelligence-is-open-source-9b654595773a)</div>


---

<!-- _class: first-slide -->
![bg](theme/slides-design/12.png)

# Arquitetura
<div class="linha"></div><br>

"*The Future of Business Intelligence is Open Source*"
<small>Maxime Beauchemin (2021)[🔗](https://maximebeauchemin.medium.com/the-future-of-business-intelligence-is-open-source-9b654595773a)</small>

---

![](figs/componentes-1.png)



---

### Funcionalidades opcionais

Os componentes opcionais - camada de cache - são necessários para ativar as seguintes funcionalidades:

- **Alertas e Relatórios**
- **Cache**
- **Consultas Assíncronas**
- **Miniaturas de Dashboards (Thumbnails)**

<br> <div style="border: 1px solid #ccc; padding: 15px; padding-left:60px; font-size: 0.7em; background-color: #f8f8f8;"> Se você fizer a instalação utilizando Docker Compose ou Kubernets, todos esses componentes serão criados automaticamente.</div>


---

<!-- _class: first-slide -->
![bg](theme/slides-design/12.png)

# A ferramenta
<div class="linha"></div><br>

"*The Future of Business Intelligence is Open Source*"
<small>Maxime Beauchemin (2021)[🔗](https://maximebeauchemin.medium.com/the-future-of-business-intelligence-is-open-source-9b654595773a)</small>

---

![center width:1000px](figs/diagram-chatgpt.png)

<center>Made by ChatGPT</center>

---

![bg:20%](figs/menu-explicação.png)



---
<!-- Texto Principal -->
<div class="texto-principal">Obrigada!</div>

<!-- Linha Divisória -->
<div class="linha"></div>
<div class="contato">
  <b>Marília Melo Favalesso - PhD, Cientista de Dados<b>
</div>

<!-- Redes Sociais -->
<div class="redes-sociais">
  <a href="https://www.linkedin.com/in/seuusuario" target="_blank">🔗 LinkedIn: /mariliafavalesso</a>
  <a href="mailto:seuemail@example.com">✉️ Email: marilia.melo.favalesso@gmail.com</a>
</div>
