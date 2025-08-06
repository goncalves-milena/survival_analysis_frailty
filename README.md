# Estudo da Adesão de Políticas Públicas da Área da Saúde por Municípios Brasileiros via Modelo de Fragilidade Compartilhada

**Autora:** Milena Souza Gonçalves  
**Orientadora:** Profª Drª Juliana Betini Fachini Gomes  
**Coorientador:** Mateus Felipe Santos Araújo  
**Instituição:** Universidade de Brasília (UnB) – Departamento de Estatística  
**Ano:** 2025

---

## 📌 Objetivo

Este repositório reúne informações (e em breve os scripts e dados) do estudo que teve como objetivo identificar os fatores que influenciam a adesão de políticas públicas da área da saúde por municípios brasileiros. O modelo adotado foi o **Modelo de Fragilidade Compartilhada**, que considera eventos múltiplos e dependência entre os tempos de adoção em um mesmo município.

---

## 📖 Introdução

A pesquisa em difusão de políticas públicas visa compreender:

- O que causa a adoção de novos programas por governos?
- Quais fatores influenciam essa adesão?
- Qual a velocidade de disseminação de uma política?

A análise de sobrevivência (Event History Analysis – EHA) é amplamente utilizada nesse campo, especialmente em contextos descentralizados como o Brasil, onde a difusão pode ocorrer de forma horizontal (entre municípios/estados) ou vertical (entre níveis de governo).

---

## 🔍 Metodologia

### 📂 Fonte de Dados

- **Políticas públicas**: Banco de dados do IPEA.
- **Adesões**: Raspagem de dados (web scraping) de diários oficiais municipais – parceria LAPCIPP/IPOL/UnB e ENAP.
- **Variáveis explicativas**: Adaptadas da tese de doutorado de Celina Pereira (2025).

### ✂️ Critérios de Recorte

- Políticas criadas entre 2000 e 2022.
- Políticas passíveis de adesão por qualquer município.
- Municípios com população ≥ 100 mil habitantes (n = 318).
- Políticas com ≥ 5% de taxa de adesão e com maior dispersão temporal.
- Políticas exclusivamente da área da saúde.

📊 **Amostra Final**:  
- 9 políticas públicas  
- 318 municípios  
- 2.862 registros (1.170 falhas, ou 40,88%)

### 📐 Variáveis

As covariáveis foram organizadas em 4 dimensões principais, além de variáveis de controle:

1. **Governabilidade Nacional**
2. **Capacidades Institucionais dos Ministérios**
3. **Inovação Ministerial**
4. **Desenho da Política**
5. **Controle Geográfico e Político**  
   (ex: PIB, porte populacional, ideologia, ano eleitoral etc.)

ℹ️ Algumas variáveis foram transformadas com logaritmo natural para linearização.

### 🛠 Ferramentas

- Todo o processamento, modelagem e análise foram realizados em **R**.

### 📈 Modelo

- Análise de Sobrevivência com eventos múltiplos.
- Modelo de **Fragilidade Compartilhada**, ideal para captar dependência entre tempos de adoção em um mesmo município.
- Avaliação do ajuste via resíduos de Cox-Snell.

---

## 🔬 Resultados

### 📊 Análise Descritiva

- 40,88% das observações resultaram em adesão (falha).
- Políticas com mais adesões:  
  - Programa Mais Médicos (PMM)  
  - Programa Saúde na Escola (PSE)  
  - Política Nacional de Atenção Básica (PNAB)  
- Políticas com menos adesões:  
  - Política Nacional de Regulação do SUS (PNRSUS)  
  - Política Nacional de Saúde da Pessoa com Deficiência (PNSPD)  
- 59,43% dos municípios aderiram a 3 ou 4 políticas.
- Capitais como BH, Goiânia, Rio e Salvador aderiram a 8 das 9 políticas.

### 📉 Resultados do Modelo Final

- **Fragilidade Compartilhada**: significativa (p = 0,0133)
- **Covariáveis significativas (exemplos)**:
  - Governabilidade Nacional:  
    - Taxa de vetos ↓ risco  
    - Taxa de sucesso ↑ risco
  - Capacidades Institucionais:  
    - Orçamento total autorizado ↓ risco (contrário ao esperado)  
    - Orçamento em TI ↑ risco
  - Inovação Ministerial:  
    - Índice de inovação ↓ risco (contrário ao esperado)
  - Desenho da Política:  
    - Número de dispositivos, multissetorialidade e taxa de controle ↑ risco
  - Variáveis de controle:
    - PIB e prefeito reeleito ↓ risco  
    - Porte populacional e ideologia do governador ↑ risco  
    - Ano eleitoral ↓ risco

### 📊 Fragilidade dos Municípios

- **Maior fragilidade**: Natal (RN) e Pelotas (RS)  
- **Menor fragilidade**: Belo Horizonte (MG)

---

## ✅ Ajuste do Modelo

- A curva empírica dos resíduos de Cox-Snell se mostrou próxima da curva teórica, indicando **bom ajuste do modelo**.

---

## 📬 Contato

Para perguntas, colaborações ou sugestões:

**Milena Souza Gonçalves**  
📧 sgoncalves.milena@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/milenagoncalves/)
