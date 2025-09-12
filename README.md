
# FarmTech — Previsão de Rendimento de Safra (PBL Fase 5)

**Projeto:** Previsão de rendimento de safra e análise de tendências de produtividade  
**Curso:** FIAP — Fase 5  
**Aluno:** Gustavo Andrade — RM564102  
**Arquivo principal (Jupyter Notebook):** `Gustavo_andrade_RM564102_pbl_fase4_FIX.ipynb`

---

## 1. Descrição rápida
Este projeto utiliza dados meteorológicos e de umidade/solo para **prever o rendimento (ton/ha)** de diferentes culturas e **explorar tendências** por meio de clusterização e detecção de outliers.  
Foram aplicados métodos de regressão supervisionada e de aprendizado não supervisionado.

---

## 2. Base de dados
Arquivo: `crop_yield.csv` (fornecido pelo portal da disciplina)

Variáveis:
- **Cultura** — nome da safra
- **Precipitação (mm dia 1)**
- **Umidade específica a 2 metros (g/kg)**
- **Umidade relativa a 2 metros (%)**
- **Temperatura a 2 metros (ºC)**
- **Rendimento** — toneladas por hectare (variável alvo)

---

## 3. Objetivos
1. Realizar Análise Exploratória de Dados (EDA).  
2. Detectar tendências e cenários discrepantes com técnicas de **clusterização** e análise de outliers.  
3. Treinar e comparar **5 modelos de regressão** diferentes.  
4. Avaliar modelos com métricas: **R², RMSE, MAE**.  
5. Salvar o melhor modelo e gerar previsões.  

---
```

---

## 5. Requisitos
Instalar dependências a partir do `requirements.txt`:
```
numpy
pandas
scikit-learn
matplotlib
seaborn
joblib
xgboost
jupyterlab
```

Criação do ambiente virtual:
```bash
python -m venv venv
source venv/bin/activate     # Linux/Mac
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

---

## 6. Como executar
1. Coloque `crop_yield.csv` na pasta `data/`.  
2. Abra o Jupyter:
```bash
jupyter lab
# ou
jupyter notebook
```
3. Execute o arquivo: `notebooks/Gustavo_andrade_RM564102_pbl_fase4_FIX.ipynb`  
4. Siga as seções já estruturadas no notebook.

---

## 7. Modelos testados
- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Gradient Boosting Regressor  
- Random Forest Regressor  

---

## 8. Métricas e resultados
Resumo dos modelos no conjunto de teste:

| Modelo             | R² (teste) | MAE (teste) | RMSE (teste) |
|--------------------|------------|-------------|--------------|
| Random Forest      | **0.9953** | **2540.29** | **4282.97** |
| Linear Regression  | 0.9950     | 3132.80     | 4394.17     |
| Lasso Regression   | 0.9949     | 3187.15     | 4425.63     |
| Ridge Regression   | 0.9948     | 3295.54     | 4490.91     |
| Gradient Boosting  | 0.9891     | 3461.38     | 6495.30     |

➡️ **Melhor modelo:** `RandomForest Regressor`

---

## 9. Artefatos gerados
- `artefatos/modelo_melhor.joblib` — modelo salvo para reuso.  
- `artefatos/previsoes_test.csv` — previsões no conjunto de teste.  

---

## 10. Vídeo demonstrativo
Link do YouTube (não listado):  
➡️ https://youtu.be/uQokP6aTSGI 

---

## 11. Observações
- O notebook já contém comentários e explicações em Markdown.  
- O nome do arquivo segue o padrão exigido pela FIAP.  
---

## 12. Contato
Gustavo Andrade — RM564102  
Email: gustavohenriqueandrade.gh@gmail.com


---

## 13. Licença
Este projeto é distribuído sob a licença MIT.

# FarmTech – Entrega 2: Estimativa de Custos AWS

## 1. Configuração da Instância (Simulada)

- **Tipo de Instância:** t3.micro (mais próxima do requisito)  
- **vCPUs:** 2  
- **Memória:** 1 GiB  
- **Armazenamento:** 50 GB EBS (simulado)  
- **Rede:** Até 5 Gbps  

> Observação: A AWS não oferece instância com exatamente 2 vCPUs + 1 GiB + 50 GB. Usamos a **instância mais próxima disponível** (t3.micro) e adicionamos um **volume EBS de 50 GB** na simulação para atender ao requisito.

---

## 2. Estimativa de Custos por Região

| Região | Tipo de Instância | RAM | Armazenamento | Preço por Hora | Preço por Mês |
|--------|-----------------|-----|---------------|----------------|---------------|
| São Paulo (sa-east-1) | t3.micro | 1 GiB | 50 GB EBS | R$0,0186 | US$6,13 |
| Virgínia do Norte (us-east-1) | t3.micro | 1 GiB | 50 GB EBS | US$0,0104 | US$3,80 |

> Valores obtidos usando **AWS Pricing Calculator**, simulando a instância mais próxima do requisito.

---

## 3. Justificativa da Escolha

Escolhemos **São Paulo (sa-east-1)**, mesmo sendo um pouco mais caro, pelos seguintes motivos:

1. **Latência menor:** sensores estão no Brasil → comunicação mais rápida.  
2. **Conformidade legal:** leis exigem armazenamento de dados dentro do país.  
3. **Acesso rápido aos dados:** servidores próximos melhoram o desempenho da aplicação.  

---

## 4. Comparação Visual de Custos

### Preço Mensal por Região

São Paulo (sa-east-1): US$6,13  
Virginia do Norte (us-east-1): US$3,80  

#### Gráfico de barras (aproximado)

São Paulo        ████████████ US$6,13  
Virginia do Norte ███████       US$3,80

---

## 5. Vídeo Demonstrativo

[Link do vídeo no YouTube]https://youtu.be/8fbr_slP8xE

> No vídeo mostramos a simulação na AWS Pricing Calculator, explicando a escolha da instância mais próxima (t3.micro com 1 GiB de RAM), o volume EBS de 50 GB e a comparação de regiões.
