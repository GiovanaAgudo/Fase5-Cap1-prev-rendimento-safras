#  FarmTech Solutions — Previsão de Rendimento Agrícola com Machine Learning

##  Sobre o projeto

Este projeto foi desenvolvido no contexto da **PBL Fase 5** do curso de Inteligência Artificial da FIAP.

Neste desafio, atuamos como uma equipe de consultoria em Inteligência Artificial chamada **FarmTech Solutions**, responsável por analisar dados agrícolas de uma fazenda de médio porte, com aproximadamente **200 hectares de área cultivada** (equivalente a cerca de 210 campos de futebol oficiais).

O objetivo do projeto é utilizar **técnicas de Ciência de Dados e Machine Learning** para compreender padrões presentes nas condições ambientais da produção agrícola e desenvolver modelos capazes de **prever o rendimento das safras**.

A base de dados utilizada contém informações relacionadas a:

- tipo de cultura cultivada
- precipitação
- umidade específica do ar
- umidade relativa
- temperatura
- rendimento da safra

A partir dessas variáveis, buscamos identificar padrões de produtividade e construir modelos preditivos que possam apoiar análises estratégicas no contexto agrícola.

---

##  Objetivos do trabalho

O projeto foi desenvolvido com os seguintes objetivos principais:

- realizar uma **análise exploratória dos dados** para compreender a estrutura da base e identificar padrões iniciais;
- aplicar técnicas de **aprendizado não supervisionado** para identificar agrupamentos entre cenários agrícolas e detectar possíveis outliers;
- desenvolver **modelos de regressão supervisionada** capazes de prever o rendimento das safras a partir das variáveis disponíveis;
- avaliar e comparar diferentes algoritmos de Machine Learning;
- interpretar os resultados obtidos e discutir limitações e possíveis melhorias futuras.

---

##  Abordagem utilizada

A solução desenvolvida combina técnicas de análise de dados e Machine Learning, incluindo:

- análise exploratória de dados (EDA)
- clusterização com **K-Means**
- identificação de outliers
- modelos de regressão supervisionada
- avaliação com métricas de desempenho

Entre os algoritmos utilizados estão:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Support Vector Regressor (SVR)
- Gradient Boosting Regressor

Todos os detalhes da análise, implementação dos modelos, interpretação dos resultados e conclusões estão documentados no notebook do projeto.

---

##  Notebook do projeto

O desenvolvimento completo da solução está documentado no notebook abaixo:

 **Abrir o notebook:**  
[GiovanaAgudo_rm566773_pbl_fase5.ipynb](./GiovanaAgudo_rm566773_pbl_fase5.ipynb)

Nele é possível encontrar:

- o carregamento e preparação da base de dados
- toda a análise exploratória realizada
- a aplicação dos algoritmos de clusterização
- o desenvolvimento e avaliação dos modelos de regressão
- a interpretação dos resultados obtidos
- as conclusões do projeto

O notebook apresenta todo o passo a passo da solução de forma detalhada e comentada.

---

## 🎥 Demonstração em vídeo - Entrega 1
O vídeo apresenta uma visão geral do problema, da base de dados, da abordagem adotada e dos principais resultados obtidos com os modelos de Machine Learning.

*https://www.youtube.com/watch?v=Q9Nh9kcU-HI*

---

---

# Infraestrutura em Nuvem – Estimativa de Custos AWS

Para viabilizar a execução do modelo de Machine Learning desenvolvido neste projeto, foi realizada uma estimativa de custos utilizando a **AWS Pricing Calculator**. O objetivo foi simular a hospedagem de uma API responsável por receber dados provenientes de sensores agrícolas e executar previsões de rendimento de safra utilizando o modelo treinado.

Essa infraestrutura permitiria que sensores instalados na fazenda enviassem dados continuamente para a nuvem, onde o modelo de Machine Learning realizaria inferências em tempo real.

---

# Arquitetura proposta

A arquitetura proposta consiste em uma instância **Amazon EC2** executando um ambiente Linux simples responsável por:

- Receber dados coletados por sensores agrícolas
- Armazenar dados temporários
- Executar o modelo de Machine Learning treinado
- Disponibilizar uma API para previsões de produtividade

Essa instância funcionaria como o ponto central de processamento dos dados coletados no campo.

---

# Configuração da máquina

Para a estimativa, foi utilizada uma configuração simples de máquina virtual com os seguintes recursos:

| Recurso | Configuração |
|------|------|
| Serviço | Amazon EC2 |
| Sistema operacional | Linux |
| Instância | t3.micro |
| CPUs | 2 vCPU |
| Memória | 1 GiB |
| Rede | até 5 Gigabit |
| Armazenamento | 50 GB (EBS gp3) |
| Modelo de cobrança | On-Demand |

Essa configuração é suficiente para hospedar uma API leve de Machine Learning e processar requisições de sensores agrícolas.

---

# Comparação de custos por região

Foi realizada uma comparação entre duas regiões da AWS:

- **US East (N. Virginia)**
- **South America (São Paulo)**

| Região AWS | Instância | CPUs | Memória | Armazenamento | Custo mensal |
|------|------|------|------|------|------|
| US East (N. Virginia) | t3.micro | 2 vCPU | 1 GiB | 50 GB | $11.59 |
| South America (São Paulo) | t3.micro | 2 vCPU | 1 GiB | 50 GB | $13.15 |


[saopaulo-BR.png](./img/saopaulo-BR.png)
 
[virginia-EUA.png](./img/virginia-EUA.png)
 
Embora a região norte-americana apresente um custo ligeiramente menor, a diferença é relativamente pequena.

---

# Justificativa da escolha da região

Apesar do menor custo apresentado pela região **US East (N. Virginia)**, a região **South America (São Paulo)** foi considerada a opção mais adequada para o cenário proposto.

Essa escolha se baseia nos seguintes fatores:

**Menor latência**

Os sensores agrícolas instalados na fazenda precisam enviar dados com frequência para a API. Utilizar uma região geograficamente mais próxima reduz o tempo de comunicação entre os dispositivos e o servidor.

**Conformidade com legislações de dados**

Em muitos cenários, o armazenamento de dados fora do país pode apresentar restrições legais relacionadas à **Lei Geral de Proteção de Dados (LGPD)**. Hospedar os dados dentro do território brasileiro reduz riscos regulatórios.

**Maior confiabilidade para sistemas em tempo real**

Aplicações que dependem de coleta contínua de dados, como monitoramento agrícola, se beneficiam de infraestrutura mais próxima da origem dos dados.

---

# Conclusão

A região **US East (N. Virginia)** apresentou o menor custo mensal estimado. Entretanto, considerando requisitos operacionais, latência e possíveis restrições legais relacionadas ao armazenamento de dados, a região **South America (São Paulo)** foi considerada a escolha mais adequada para a implantação da infraestrutura do sistema.

Essa decisão prioriza desempenho e conformidade regulatória, mantendo ao mesmo tempo um custo operacional relativamente baixo para a execução da solução proposta.

## 🎥 Demonstração em vídeo - Entrega 2
O vídeo demonstra como utilizamos a AWS Pricing Calculator para estimar os custos de infraestrutura em nuvem e comparar duas regiões da AWS, identificando a melhor opção para hospedar nossa solução de Machine Learning.

*https://www.youtube.com/watch?v=HSdiVCVqjYA&feature=youtu.be*

---

## Autoria
**Giovana Agudo**  
RM: 566773  
FIAP — Inteligência Artificial

---