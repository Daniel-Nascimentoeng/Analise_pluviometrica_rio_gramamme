# 📊🌨 Análise Pluviométrica – (2019)  
**Bacia Hidrográfica do Rio Gramame**

Este projeto apresenta a análise dos dados de **precipitação** coletados pela **estação pluviográfica de código 14**, localizada na **bacia do Rio Gramame**, para o ano de **2019**.  

A análise foi realizada em **quatro escalas temporais distintas**:  
- 📏 **5 minutos** (passo original de medição)  
- 🕐 **60 minutos** (acumulado horário)  
- 📅 **Diário**  
- 📆 **Mensal**  

---

## 🧪 Objetivo
Transformar, organizar e visualizar os dados pluviométricos em diferentes escalas de tempo, a fim de:  
✔️ Compreender o comportamento das chuvas na região  
✔️ Identificar padrões e extremos de precipitação  
✔️ Apoiar análises hidrológicas e a **tomada de decisão em gestão hídrica**

---

# 🌧️ Pluviômetro de Báscula

O **pluviômetro de báscula** é um dos tipos mais modernos de pluviômetros.  
Ele funciona de forma **automática** e é amplamente utilizado em **estações meteorológicas automáticas** no Brasil, como as do **INMET, ANA e CPRM**.

---

## 💡 Curiosidade Hidrológica – Pluviômetro de Báscula

### 📌 Como funciona
1. A chuva é captada por um **funil**.  
2. A água cai sobre uma **báscula** (semelhante a uma gangorra com dois compartimentos).  
3. Quando um dos lados enche com um volume fixo (ex.: **0,2 mm de chuva**), a báscula **vira**, despejando a água e acionando um **sensor magnético**.  
4. Cada “basculada” gera um **pulso elétrico**, que é registrado e convertido em **milímetros de precipitação**.  

---

### 🔎 Características principais
- 🌧️ Mede a **chuva acumulada** com alta precisão.  
- ⏱️ Permite calcular chuva em **tempo real** (minutos, horas, dias).  
- 📡 Pode ser integrado a **sistemas automáticos de telemetria**.  

---

### ⚠️ Limitação
Em chuvas de **alta intensidade**, o mecanismo pode não bascular rápido o suficiente, o que resulta em uma **subestimativa dos totais de precipitação**.  

---

### ✅ Conclusão
Apesar dessa limitação, o **pluviômetro de báscula** é o instrumento mais utilizado em:  
- Hidrologia aplicada  
- Monitoramento meteorológico  
- Sistemas de alerta de enchentes  

---


## 📈 Conclusões Estatísticas

### 🕔 Intervalos de 5 minutos
- **Média:** 0.054 mm | **Desvio padrão:** 0.58 mm  
- ⚠️ **75% dos registros = zero**, evidenciando baixa frequência de chuva  
- 🌧️ Pico intenso: **37 mm em apenas 5 minutos!**  
- 📉 Boxplot achatado e cheio de outliers — pouca variabilidade, dominado por extremos  
- 👉 **Pouco útil para análise estatística detalhada**  

---

### 🕐 Dados Horários
- **Média:** 0.657 mm/h | **Desvio padrão:** 4.50 mm  
- 🌧️ Máximo: **129 mm/h** (eventos extremos)  
- ⚠️ Muitos valores zerados ainda prejudicam a representatividade  

---

### 📅 Dados Diários
- **Média:** 15.77 mm/dia | **Desvio padrão:** 47.03 mm  
- 📌 Mediana: **1.0 mm**, mas máximo chega a **692 mm**  
- 📈 Boxplot mais informativo, revelando melhor distribuição entre dias secos e chuvosos  

---

### 🗓️ Dados Mensais
- **Média:** 479.83 mm/mês | **Desvio padrão:** 449.76 mm  
- 🌧️ Máximo: **1571 mm/mês**  
- 📊 Melhor escala para análise: menos zeros, maior tendência e padrão de distribuição  

---

## 🧠 Conclusão Geral
- ⏱️ **Escalas menores** (5 min / hora) → dominadas por zeros e outliers → dificultam a análise.  
- 📆 **Escalas maiores** (diária / mensal) → oferecem melhor distribuição e **maior confiabilidade estatística**.  
- ⚙️ O uso de `resample().sum()` foi essencial para acumular corretamente os totais de chuva.  
- 📌 Para análises futuras ou modelos, recomenda-se **trabalhar com dados diários ou mensais**.  

---

## 📊 Considerações sobre os Boxplots
- Nas escalas curtas (5 min e hora), os boxplots mostraram-se **pouco representativos**, com grande concentração em zero e muitos valores extremos.  
- ✅ Nas escalas **diária e mensal**, os boxplots se tornam **mais estáveis**, com menor distorção e maior representatividade da realidade pluviométrica.  

