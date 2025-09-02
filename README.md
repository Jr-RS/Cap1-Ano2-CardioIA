# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# CardioIA — Fase 1: Batimentos de Dados

## Nome do grupo

## 👨‍🎓 Integrantes: 
- <a href="https://www.linkedin.com/company/inova-fusca">Ana Beatriz Duarte Domingues</a>
- <a href="https://www.linkedin.com/company/inova-fusca">Carlos Emilio Castillo Estrada</a>
- <a href="https://www.linkedin.com/company/inova-fusca">Junior Rodrigues da Silva</a>

## 📜 Descrição

Este repositório documenta a Fase 1, "Batimentos de Dados", do projeto CardioIA.

O objetivo desta fase é realizar a curadoria, coleta e exploração inicial de três tipos de dados cardiológicos: numéricos (IoT/prontuário), textuais (diretrizes) e visuais (imagens de ECG). Essa base de dados sustentará as próximas fases do projeto, incluindo modelagem, construção de APIs e aplicação para suporte à decisão clínica.

A abordagem prioriza reprodutibilidade e transparência, com Google Colaboratory Notebooks para executar downloads, carregamentos e visualizações. A pasta `docs/` contém um estudo aprofundado (“CardioIA_ Coleta e Preparação de Dados.docx”) que fundamenta as escolhas técnicas e clínicas desta fase.

### Parte 1 – Dados Numéricos (IoT)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/1_dados_numericos.ipynb)
- Fonte: "Cardiovascular Disease dataset" (Kaggle) — https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
- Justificativa: Dados reais com 70.000 registros adequados para análises clínicas e modelagem preditiva. Variáveis-chave: ap_hi (pressão sistólica), ap_lo (pressão diastólica), cholesterol e age. Hipertensão e dislipidemia são fatores críticos para DCV; idade é um fator não modificável central. Essas variáveis são essenciais para estratificação de risco e priorização de intervenções.
- Entregável: Notebook do Colab que realiza download via Kaggle, carrega com pandas e executa EDA básica (head/info/describe).
- Abrir no Colab: https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/1_dados_numericos.ipynb

### Parte 2 – Dados Textuais (NLP)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/2_dados_textuais.ipynb)
- Fonte: "Diretriz Brasileira de Insuficiência Cardíaca Crônica e Aguda" — http://publicacoes.cardiol.br/portal/abc/portugues/2018/v11103/diretriz-brasileira-de-insuficiencia-cardiaca-cronica-e-aguda_pdf.html
- Justificativa: Diretrizes clínicas são ideais para NLP: permitem Reconhecimento de Entidades Nomeadas (medicamentos, sintomas, comorbidades), construção de Grafos de Conhecimento (relações medicamento–doença–conduta) e sumarização automática para apoio à decisão. Esse pipeline textual alimenta o “cérebro” do CardioIA e viabiliza um assistente clínico em fases futuras.
- Entregável: Notebook do Colab que baixa o PDF, extrai o texto com pdfplumber, exibe os primeiros 2000 caracteres e salva o conteúdo completo em `docs/diretriz_brasileira_ic.txt`.
- Abrir no Colab: https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/2_dados_textuais.ipynb

### Parte 3 – Dados Visuais (VC)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/3_dados_visuais.ipynb)
- Fonte: "ECG Arrhythmia Image Dataset" (Kaggle), derivado do MIT-BIH — https://www.kaggle.com/datasets/erhmrai/ecg-image-data
- Justificativa: Imagens de ECG são ideais para CNNs, possibilitando classificação de arritmias (ex.: normal, supraventricular, ventricular) e detecção de anomalias. Essa trilha dá origem ao módulo de diagnóstico automatizado nas próximas fases, aumentando eficiência e precisão.
- Entregável: Notebook do Colab que baixa o dataset do Kaggle e exibe exemplos de cada classe detectada.
- Abrir no Colab: https://colab.research.google.com/github/Jr-RS/Cap1-Ano2-CardioIA/blob/main/notebooks/3_dados_visuais.ipynb




## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>.github</b>: Nesta pasta ficarão os arquivos de configuração específicos do GitHub que ajudam a gerenciar e automatizar processos no repositório.

- <b>assets</b>: aqui estão os arquivos relacionados a elementos não-estruturados deste repositório, como imagens.

- <b>config</b>: Posicione aqui arquivos de configuração que são usados para definir parâmetros e ajustes do projeto.

- <b>document</b>: aqui estão todos os documentos do projeto que as atividades poderão pedir. Na subpasta "other", adicione documentos complementares e menos importantes.

- <b>scripts</b>: Posicione aqui scripts auxiliares para tarefas específicas do seu projeto. Exemplo: deploy, migrações de banco de dados, backups.

- <b>src</b>: Todo o código fonte criado para o desenvolvimento do projeto ao longo das 7 fases.

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).

Estrutura ativa nesta fase:
- `docs/`
  - `diretriz_brasileira_ic.txt` — texto extraído da diretriz de IC.
  - `CardioIA_ Coleta e Preparação de Dados.docx` — pesquisa aprofundada que fundamenta o projeto.
- `notebooks/`
  - `1_dados_numericos.ipynb` — Kaggle + pandas + EDA.
  - `2_dados_textuais.ipynb` — download PDF + extração com pdfplumber.
  - `3_dados_visuais.ipynb` — Kaggle + visualização por classe.

## 🔧 Como executar o código

Você pode optar por executar via Google Colab (recomendado nesta fase) ou localmente.

1) Google Colab
- Clique nos links das Partes 1–3; o Colab abrirá o notebook a partir deste repositório.
- Configure credenciais do Kaggle (usuário e key) no ambiente do Colab antes de executar as células de download, se necessário.

2) Execução local (opcional)
- Requisitos: Python 3.10+ e pip. Abra os notebooks com Jupyter/VS Code.
- Instale dependências: `pip install -r requirements.txt`.
- Configure credenciais do Kaggle: crie `%USERPROFILE%/.kaggle/kaggle.json` com `{ "username": "SEU_USER", "key": "SUA_KEY" }` ou exporte variáveis de ambiente.
- Execute as células conforme instruções de cada notebook.

## 🗃 Histórico de lançamentos

* 1.0.0 - 30/08/2025

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>


