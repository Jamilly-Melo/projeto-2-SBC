# Projeto II - Controlador Fuzzy para Avaliação do Risco de Fungos em Plantações

## Descrição do Domínio

Este projeto implementa um controlador fuzzy do tipo Mamdani, desenvolvido com a biblioteca scikit-fuzzy em Python, para auxiliar na avaliação do risco de desenvolvimento de doenças fúngicas em plantações.

O controlador utiliza lógica fuzzy para representar diferentes graus de pertinência das variáveis linguísticas, permitindo uma tomada de decisão mais flexível e próxima das condições reais observadas em uma plantação.

O sistema considera duas variáveis de entrada:
- Umidade do ambiente
- Temperatura ambiente

A partir dessas informações, o controlador calcula um índice de risco de desenvolvimento de fungos, classificando-o como baixo, médio ou alto. A inferência é realizada pelo método de Mamdani, utilizando funções de pertinência triangulares, uma base de regras fuzzy e defuzzificação para obtenção do resultado final.

---

## Variáveis Linguísticas

### Entrada 1 - Umidade do Ambiente
- Baixa
- Média
- Alta

### Entrada 2 - Temperatura Ambiente
- Baixa
- Ideal
- Alta

### Saída - Risco de Fungos
- Baixo
- Médio
- Alto

---

## Descrição das Regras

A base de conhecimento é composta por nove regras fuzzy, cobrindo todas as combinações possíveis entre as variáveis linguísticas de entrada. Sendo elas:

**Regra 1:** Umidade baixa e temperatura baixa resultam em baixo risco de fungos.

**Regra 2:** Umidade baixa e temperatura ideal resultam em baixo risco de fungos.

**Regra 3:** Umidade baixa e temperatura alta resultam em baixo risco de fungos.

**Regra 4:** Umidade média e temperatura baixa resultam em baixo risco de fungos.

**Regra 5:** Umidade média e temperatura ideal resultam em risco médio de fungos.

**Regra 6:** Umidade média e temperatura alta resultam em alto risco de fungos.

**Regra 7:** Umidade alta e temperatura baixa resultam em risco médio de fungos.

**Regra 8:** Umidade alta e temperatura ideal resultam em alto risco de fungos.

**Regra 9:** Umidade alta e temperatura alta resultam em alto risco de fungos.

---

## Casos de Teste

### Caso de Teste 1 - Alto Risco de Fungos

#### Entrada
```
Controlador Fuzzy para o Risco de Fungos

Digite a umidade do ambiente (0 a 100%): 90
Digite a temperatura (0 a 40 °C): 30
```

#### Saída Obtida
```
Resultado:

Risco de fungos: 84.44%
Classificação: Alto risco.
Recomendação: Avaliar a necessidade de aplicação de fungicida.
```

A elevada umidade do ambiente, combinada com uma temperatura alta, favorece significativamente o desenvolvimento de fungos. Dessa forma, o controlador fuzzy classificou a situação como de alto risco, indicando a necessidade de monitoramento e possível aplicação de fungicida.

### Caso de Teste 2 - Baixo Risco de Fungos

#### Entrada
```
Controlador Fuzzy para o Risco de Fungos

Digite a umidade do ambiente (0 a 100%): 20
Digite a temperatura (0 a 40 °C): 12
```

#### Saída Obtida
```
Resultado:

Risco de fungos: 16.89%
Classificação: Baixo risco.
Recomendação: Manter o monitoramento da plantação.
```

Nesse cenário, a baixa umidade do ambiente reduz significativamente as condições favoráveis ao desenvolvimento de fungos. Assim, o controlador classificou o risco como baixo.

### Caso de Teste 3 - Risco Médio de Fungos

#### Entrada
```
Controlador Fuzzy para o Risco de Fungos

Digite a umidade do ambiente (0 a 100%): 65
Digite a temperatura (0 a 40 °C): 18
```

#### Saída Obtida
```
Resultado:

Risco de fungos: 55.92%
Classificação: Risco moderado.
Recomendação: Intensificar o monitoramento.
```

Embora a umidade do ambiente seja elevada, a temperatura mais baixa reduz parcialmente as condições para o desenvolvimento de fungos. Dessa forma, o controlador fuzzy classificou o cenário como de risco médio.

---

## Como Executar

### 1. Executar o Programa

Abra o arquivo `projeto_II.ipynb` no Google Colab e execute todas as células em ordem.

Ao final da execução, o programa solicitará ao usuário os valores de umidade do ambiente e temperatura.

### 2. Saída Esperada

Após receber os valores informados pelo usuário, o controlador fuzzy realizará a inferência utilizando o método de Mamdani e exibirá o índice de risco de desenvolvimento de fungos, classificando-o como baixo, médio ou alto, além de apresentar uma recomendação correspondente ao cenário avaliado.

---
