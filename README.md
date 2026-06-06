# Análise de Mercado de Jogos, Plataformas e Avaliações (2012–2016)  
## Limpeza de Dados, Tendências de Lançamentos, Ciclo de Plataformas e Testes de Hipóteses

## Objetivo do Projeto
Este projeto analisa o mercado global de videogames entre 2012 e 2016, avaliando:

- padrões de lançamento ao longo dos anos  
- ciclo de vida das principais plataformas  
- relação entre avaliações (usuários e crítica) e vendas  
- diferenças regionais de consumo  
- comportamento por gênero  
- testes estatísticos para comparar plataformas e gêneros  

O trabalho inclui limpeza de dados, análise exploratória, visualizações e testes de hipóteses.

---

## Preparação e Limpeza dos Dados

### **1. Ajuste dos tipos de dados**
- A coluna **year_of_release** estava como `float64`, o que não faz sentido para anos.  
  → Convertida para `object` para facilitar o tratamento de valores ausentes.  
- A coluna **user_score** estava como `object` e continha valores como `"tbd"`.  
  → Esses valores foram tratados como ausentes e substituídos por `NaN`.  
  → Em seguida, convertida para `float64`.

### **2. Possíveis causas de valores ausentes**
- Falta de interesse do usuário em avaliar  
- Ausência de avaliação da crítica especializada  
- Falhas ou inconsistências na coleta de dados  

---

## Análise Temporal dos Lançamentos

### **Tendências observadas**
- Forte crescimento no início dos anos 2000, possivelmente ligado à transição de gerações de consoles e expansão digital.  
- Queda acentuada entre **2011 e 2012**, indicando:
  - fim de ciclo de geração  
  - mudança no mercado para jogos mais complexos e de maior qualidade  

### **Recorte utilizado**
Para garantir consistência, foram analisados apenas os anos **2012 a 2016**, totalizando 5 anos.

---

## Ciclo de Vida das Plataformas

### **Comportamento geral**
- Plataformas começam com poucos lançamentos  
- Crescem rapidamente nos anos seguintes  
- Sofrem queda quando uma nova geração surge  
- Consolidação leva **1–2 anos**  
- Ciclo médio de vida: **8–10 anos**

### **Exemplos**
- **PS2** atingiu seu auge nos anos 2000 e perdeu força com novas plataformas.  
- **PS3 e Xbox 360** cresceram por 4 anos e caíram bruscamente a partir de 2012.  
- **Wii e 3DS** seguem padrão semelhante.  
- **PS4** ultrapassou 100 milhões de vendas, mas também apresentou queda posterior.

---

## Correlação entre Avaliações e Vendas (PS4)

- **Correlação user_score × vendas:** **-0.03**  
  → Praticamente nenhuma relação.  
  → Jogos bem avaliados pelos usuários não necessariamente vendem mais.

- **Correlação critic_score × vendas:** **0.40**  
  → Correlação moderada positiva.  
  → Avaliações da crítica influenciam mais as vendas do que as dos usuários.

---

## Desempenho de Jogos Multiplataforma

- Jogos como **GTA V** vendem muito mais em consoles de mesa do que em portáteis.  
- O desempenho varia fortemente entre plataformas.  
- Não existe equilíbrio: a mesma franquia pode ter sucesso em uma plataforma e fracasso em outra.  
- Campanhas de marketing devem considerar **onde está o público-alvo**.

---

## Análise por Gênero

### **Quantidade de títulos**
- **Ação** domina amplamente.  
- **Sports** e **Role-Playing** aparecem em seguida.  
- **Misc** tem volume maior do que muitos gêneros tradicionais.  
- Demais gêneros têm números menores e estáveis.

### **Vendas por gênero**
- **Ação** continua líder absoluto.  
- **Shooter** e **Sports** vêm logo atrás.  
- **Misc** apresenta vendas relevantes.  
- **RPG** mantém vendas consistentes.  
- Gêneros menores permanecem nichados.

---

## Diferenças Regionais

### **Plataformas**
- **América do Norte:** Sony e Microsoft dominam; Wii forte no início.  
- **Europa:** Sony domina amplamente; Xbox aparece em segundo.  
- **Japão:** Nintendo domina com DS/3DS; Microsoft quase inexistente.

### **Gêneros**
- **AN:** Action, Shooter, Sports  
- **UE:** Action, Sports, Shooter  
- **JP:** RPG, Adventure, Action  

**Resumo:**  
Ocidente prefere ação e competição; Japão prefere RPG e narrativas profundas.

---

## Classificação ESRB por Região

- **América do Norte:** E domina; T e M quase empatados.  
- **Europa:** E lidera; M e T próximos.  
- **Japão:** E e T dominam; M muito menor.

**Conclusão:**  
A classificação **E** é a mais vendida globalmente, mas T e M têm peso maior no Ocidente.

---

## Testes de Hipóteses

### **Hipótese 1 — user_score: Xbox One vs PC**
- p‑valor < 0.05  
→ **Rejeitamos H₀**  
→ As médias são diferentes.

### **Hipótese 2 — user_score: Action vs Sports**
- p‑valor ≈ 0.115  
→ **Não rejeitamos H₀**  
→ Não há evidência de diferença entre as médias.

### **Metodologia**
- H₀ sempre representa “não diferença”  
- H₁ representa “diferença”  
- Nível de significância: **5%**  
- Teste utilizado: **t de Student para duas amostras independentes**

---

## Conclusão Geral

O mercado de jogos entre 2012 e 2016 apresenta:

- forte influência de ciclos de geração de consoles  
- domínio de gêneros como Ação, Shooter e Sports  
- diferenças culturais marcantes entre regiões  
- impacto maior da crítica do que dos usuários nas vendas  
- variação significativa no desempenho de jogos multiplataforma  
- evidências estatísticas claras em algumas comparações e ausência em outras  

O conjunto da análise oferece uma visão robusta sobre comportamento do mercado, preferências regionais e dinâmica das plataformas.

---

## Tecnologias Utilizadas
- Python  
- Pandas / NumPy  
- SciPy (teste t)  
- Visualização (Matplotlib / Seaborn)  
- Jupyter Notebook  

---

## Estrutura do Repositório
