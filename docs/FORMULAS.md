# 🧮 Documentação de Fórmulas

## 📊 Visão Geral

Este documento detalha todas as fórmulas utilizadas na planilha `Controle_IR_2025.xlsx`, com explicações passo a passo e exemplos práticos.

---

## 📁 Índice de Fórmulas

1. [Fórmulas do Dashboard](#-1-fórmulas-do-dashboard)
2. [Fórmulas de Totalização](#-2-fórmulas-de-totalização)
3. [Fórmulas de Validação](#-3-fórmulas-de-validação)
4. [Fórmulas do Resumo Fiscal](#-4-fórmulas-do-resumo-fiscal)
5. [Fórmulas Auxiliares](#-5-fórmulas-auxiliares)

---

## 🏗️ 1. Fórmulas do Dashboard

### 1.1. Rendimentos Totais

**Localização**: Dashboard!D4

```excel
=SOMA(Rendimentos!E6:E1000)
```

**Explicação**:
- `SOMA()`: Função que adiciona todos os valores de um intervalo
- `Rendimentos!E6:E1000`: Referência ao intervalo de valores na aba Rendimentos
  - `Rendimentos!` = Nome da aba
  - `E6:E1000` = Intervalo da coluna E (valores), linhas 6 a 1000

**Exemplo**:
```
Se Rendimentos!E6:E10 contém:
E6: R$ 5.000,00
E7: R$ 5.000,00
E8: R$ 5.000,00
E9: R$ 1.500,00
E10: R$ 2.000,00

Resultado: R$ 18.500,00
```

### 1.2. Deduções Totais

**Localização**: Dashboard!D5

```excel
=SOMA(Deduções!E6:E1000)
```

**Explicação**:
Idêntica à fórmula anterior, mas referenciando a aba de Deduções.

### 1.3. Despesas Profissionais Totais

**Localização**: Dashboard!D6

```excel
=SOMA('Despesas Profissionais'!E6:E1000)
```

**Explicação**:
- `'Despesas Profissionais'!` = Nome da aba com espaços (requer aspas simples)
- Mesma lógica de soma das demais abas

### 1.4. Base de Cálculo

**Localização**: Dashboard!D7

```excel
=D4-D5-D6
```

**Explicação**:
- Cálculo: Rendimentos - Deduções - Despesas
- Resultado é a base tributável estimada

**Exemplo**:
```
D4 (Rendimentos): R$ 18.500,00
D5 (Deduções):  R$ 2.950,00
D6 (Despesas):    R$ 1.980,00

Base = 18.500 - 2.950 - 1.980 = R$ 13.570,00
```

### 1.5. Imposto Estimado (15%)

**Localização**: Dashboard!D8

```excel
=D7*0,15
```

**Explicação**:
- Multiplica a Base de Cálculo por 15%
- `0,15` = 15% em formato decimal
- Cálculo simplificado (alíquota única)

**Observação**:
Esta é uma estimativa. A tabela progressiva real do IRPF possui múltiplas alíquotas:
- Até R$ 2.112,00: Isento
- R$ 2.112,01 a R$ 2.826,65: 7,5%
- R$ 2.826,66 a R$ 3.751,05: 15%
- R$ 3.751,06 a R$ 4.664,68: 22,5%
- Acima de R$ 4.664,68: 27,5%

### 1.6. Patrimônio Total

**Localização**: Dashboard!D9

```excel
=SOMA('Bens e Direitos'!E6:E1000)
```

**Explicação**:
- Soma todos os valores de bens e direitos declarados
- Representa o patrimônio total do contribuinte

### 1.7. Data de Atualização

**Localização**: Dashboard!D20

```excel
=HOJE()
```

**Explicação**:
- `HOJE()`: Função que retorna a data atual do sistema
- Atualiza automaticamente sempre que a planilha é aberta

---

## ➕ 2. Fórmulas de Totalização

### 2.1. Total de Rendimentos

**Localização**: Rendimentos!E[fim da tabela]

```excel
=SOMA(E6:E999)
```

**Variante com SUBTOTAL** (recomendada):

```excel
=SUBTOTAL(9,E6:E999)
```

**Explicação de SUBTOTAL**:
- `SUBTOTAL(9, intervalo)`: Função de soma que ignora linhas ocultas
- `9` = Código para SOMA
- Útil quando filtros são aplicados

**Outras funções SUBTOTAL**:
- 1 = MÉDIA
- 2 = CONT.NÚMEROS
- 3 = CONT.VALORES
- 4 = MÁXIMO
- 5 = MÍNIMO
- 9 = SOMA

### 2.2. Total com Condição (SOMASE)

**Exemplo**: Somar apenas rendimentos de "Salário"

```excel
=SOMASE(Rendimentos!C6:C999,"Salário",Rendimentos!E6:E999)
```

**Explicação**:
- `SOMASE(intervalo_critério, critério, intervalo_soma)`
- `C6:C999` = Coluna de Categorias
- `"Salário"` = Critério de busca
- `E6:E999` = Coluna de Valores a somar

**Exemplo Prático**:
```
C6: Salário | E6: R$ 5.000,00 ✓
C7: Salário | E7: R$ 5.000,00 ✓
C8: Aluguel | E8: R$ 1.500,00 ✗
C9: Salário | E9: R$ 5.000,00 ✓

Resultado: R$ 15.000,00
```

### 2.3. Total com Múltiplas Condições (SOMASES)

**Exemplo**: Somar deduções de "Educação" acima de R$ 1.000

```excel
=SOMASES(Deduções!E6:E999, Deduções!C6:C999, "Educação", Deduções!E6:E999, ">1000")
```

**Explicação**:
- `SOMASES(intervalo_soma, intervalo_crit1, crit1, intervalo_crit2, crit2, ...)`
- Permite múltiplos critérios simultâneos

---

## ✅ 3. Fórmulas de Validação

### 3.1. Validação de Data (Ano Correto)

**Aplicação**: Colunas de DATA em todas as abas

**Fórmula de Validação**:
```excel
=E(ANO(B6)=2025, B6<=HOJE())
```

**Explicação**:
- `E()`: Função lógica AND (todas as condições devem ser verdadeiras)
- `ANO(B6)=2025`: Verifica se o ano da data é 2025
- `B6<=HOJE()`: Verifica se a data não é futura

**Mensagem de Erro**:
```
"Data inválida! Use datas de 2025 até hoje."
```

### 3.2. Validação de Valor Positivo

**Aplicação**: Colunas de VALOR

**Fórmula de Validação**:
```excel
=E6>0
```

**Explicação**:
- Aceita apenas valores maiores que zero
- Impede valores negativos ou zero

**Mensagem de Erro**:
```
"O valor deve ser maior que zero."
```

### 3.3. Validação de Lista (Categorias)

**Aplicação**: Colunas de CATEGORIA

**Configuração**:
- Tipo: Lista
- Fonte: `Salário;Aluguel;Honorários;Outros`

**Alternativa com referência a intervalo**:
```excel
=ValidacoesList!A2:A5
```

Onde `ValidacoesList` é uma aba oculta com as listas.

---

## 📈 4. Fórmulas do Resumo Fiscal

### 4.1. Base de Cálculo com Proteção

**Localização**: Resumo Fiscal!D9

```excel
=MÁXIMO(0, D6-D7-D8)
```

**Explicação**:
- `MÁXIMO(0, cálculo)`: Garante que o resultado nunca seja negativo
- Se (Rendimentos - Deduções - Despesas) < 0, retorna 0
- Previne valores negativos de imposto

**Exemplo**:
```
Rendimentos: R$ 10.000,00
Deduções: R$ 8.000,00
Despesas: R$ 5.000,00

Sem MÁXIMO: 10.000 - 8.000 - 5.000 = -3.000 (erro!)
Com MÁXIMO: MÁXIMO(0, -3.000) = 0 (correto)
```

### 4.2. Imposto com Tabela Progressiva (Avançado)

**Fórmula Completa**:

```excel
=SE(D9<=2112,00, 0,
  SE(D9<=2826,65, (D9*0,075)-158,40,
  SE(D9<=3751,05, (D9*0,15)-370,40,
  SE(D9<=4664,68, (D9*0,225)-651,73,
  (D9*0,275)-884,96))))
```

**Explicação**:
Estrutura de SE aninhado para tabela progressiva:

1. **Faixa 1** (até R$ 2.112,00): Isento (0%)
2. **Faixa 2** (R$ 2.112,01 a R$ 2.826,65): 7,5% - R$ 158,40
3. **Faixa 3** (R$ 2.826,66 a R$ 3.751,05): 15% - R$ 370,40
4. **Faixa 4** (R$ 3.751,06 a R$ 4.664,68): 22,5% - R$ 651,73
5. **Faixa 5** (acima de R$ 4.664,68): 27,5% - R$ 884,96

**Exemplo de Cálculo**:
```
Base = R$ 5.000,00 (Faixa 5)
Imposto = (5.000 * 0,275) - 884,96
Imposto = 1.375 - 884,96
Imposto = R$ 490,04
```

### 4.3. Percentual Efetivo de Tributação

```excel
=SE(D9>0, D10/D9, 0)
```

**Explicação**:
- `D10/D9` = Imposto / Base de Cálculo
- `SE(D9>0, ...)`: Evita divisão por zero
- Retorna a alíquota efetiva paga

**Exemplo**:
```
Imposto: R$ 2.035,50
Base: R$ 13.570,00

Alíquota Efetiva = 2.035,50 / 13.570,00 = 15%
```

---

## 🛠️ 5. Fórmulas Auxiliares

### 5.1. Contagem de Lançamentos

```excel
=CONT.VALORES(Rendimentos!B6:B999)
```

**Explicação**:
- `CONT.VALORES()`: Conta células não vazias
- Útil para saber quantos lançamentos foram feitos

### 5.2. Última Data de Lançamento

```excel
=MÁXIMO(Rendimentos!B6:B999)
```

**Explicação**:
- `MÁXIMO()` em intervalo de datas retorna a data mais recente

### 5.3. Média de Rendimentos Mensais

```excel
=MÉDIA(Rendimentos!E6:E999)
```

**ou com proteção**:

```excel
=SE(CONT.VALORES(Rendimentos!E6:E999)>0, MÉDIA(Rendimentos!E6:E999), 0)
```

### 5.4. Maior Rendimento

```excel
=MÁXIMO(Rendimentos!E6:E999)
```

### 5.5. Menor Dedução

```excel
=SE(CONT.VALORES(Deduções!E6:E999)>0, MÍNIMO(Deduções!E6:E999), 0)
```

### 5.6. Formatação Condicional - Alertas

**Destacar deduções acima do limite de educação**:

```excel
=E(C6="Educação", E6>3561,50)
```

**Formatação**: Fundo vermelho claro

---

## 📊 Fórmulas Estatísticas Avançadas

### Variância de Rendimentos

```excel
=VAR.P(Rendimentos!E6:E999)
```

### Desvio Padrão

```excel
=DESVPAD.P(Rendimentos!E6:E999)
```

### Mediana

```excel
=MED(Rendimentos!E6:E999)
```

---

## 🔗 Fórmulas de Referência Cruzada

### Busca de Valor por Categoria (PROCV)

```excel
=PROCV("Salário", Rendimentos!C6:E999, 3, FALSO)
```

**Explicação**:
- `PROCV(valor_procurado, tabela, coluna, correspondencia_exata)`
- Busca "Salário" na 1ª coluna e retorna valor da 3ª coluna

### Índice e Correspondência (INDEX + MATCH)

```excel
=ÍNDICE(Rendimentos!E6:E999, CORRESP("Salário", Rendimentos!C6:C999, 0))
```

**Explicação**:
- Mais flexível que PROCV
- `CORRESP()` encontra a posição
- `ÍNDICE()` retorna o valor naquela posição

---

## ⚠️ Tratamento de Erros

### SEERRO - Tratamento Genérico

```excel
=SEERRO(D7*0,15, "Erro no cálculo")
```

**Explicação**:
- Se a fórmula retornar erro, exibe a mensagem
- Útil para prevenir #DIV/0!, #REF!, #VALOR!

### SEÉ.ERROS - Verificação de Erro

```excel
=SE(NÃO(É.ERROS(D7)), D7*0,15, 0)
```

**Explicação**:
- `É.ERROS()`: Retorna VERDADEIRO se houver erro
- `NÃO(É.ERROS())`: Inverte a lógica

---

## 📝 Boas Práticas

### 1. Usar Referências Nomeadas

**Criar nome para intervalo**:
```
Fórmulas > Definir Nome
Nome: TotalRendimentos
Refere-se a: =Rendimentos!$E$6:$E$999
```

**Usar na fórmula**:
```excel
=SOMA(TotalRendimentos)
```

**Vantagens**:
- Fórmulas mais legíveis
- Fácil manutenção
- Menos erros de referência

### 2. Usar Referências Absolutas vs. Relativas

**Relativa** (ajusta ao copiar):
```excel
=A1+B1
```

**Absoluta** (fixa ao copiar):
```excel
=$A$1+$B$1
```

**Mista** (fixa apenas linha ou coluna):
```excel
=$A1+B$1
```

### 3. Documentar Fórmulas Complexas

**Adicionar comentário na célula**:
```
Botão direito > Inserir Comentário

"Esta fórmula calcula o imposto usando a tabela progressiva
do IRPF 2025 com 5 faixas de tributação."
```

---

## 🧑‍🏫 Exemplos Práticos Completos

### Exemplo 1: Dashboard Completo

```excel
' Célula D4 - Rendimentos Totais
=SOMA(Rendimentos!E:E)

' Célula D5 - Deduções Totais
=SOMA(Deduções!E:E)

' Célula D6 - Despesas Totais
=SOMA('Despesas Profissionais'!E:E)

' Célula D7 - Base de Cálculo
=MÁXIMO(0, D4-D5-D6)

' Célula D8 - Imposto Estimado
=D7*0,15

' Célula D9 - Patrimônio
=SOMA('Bens e Direitos'!E:E)
```

### Exemplo 2: Resumo por Categoria

Criar tabela auxiliar com totais por categoria:

```excel
' Coluna A: Categorias
A2: Salário
A3: Aluguel
A4: Honorários

' Coluna B: Totais
B2: =SOMASE(Rendimentos!C:C, A2, Rendimentos!E:E)
B3: =SOMASE(Rendimentos!C:C, A3, Rendimentos!E:E)
B4: =SOMASE(Rendimentos!C:C, A4, Rendimentos!E:E)
```

---

## 🔍 Troubleshooting - Erros Comuns

### Erro #REF!

**Causa**: Referência inválida (aba/célula deletada)

**Solução**:
```excel
' Antes (com erro)
=Rendimentos!E6  ' (se aba foi renomeada)

' Corrigir para
='Nova Aba'!E6
```

### Erro #DIV/0!

**Causa**: Divisão por zero

**Solução**:
```excel
' Antes
=D10/D9

' Corrigido
=SE(D9<>0, D10/D9, 0)
```

### Erro #VALOR!

**Causa**: Tipo de dados incomp atível

**Solução**:
```excel
' Converter texto para número
=VALOR(SUBSTITUIR(A1,"R$ ",""))
```

---

## 📚 Referências

### Documentação Oficial Microsoft
- [Funções do Excel (por categoria)](https://support.microsoft.com/pt-br/office/funcoes-do-excel-por-categoria-5f91f4e9-7b42-46d2-9bd1-63f26a86c0eb)
- [Visão geral de fórmulas no Excel](https://support.microsoft.com/pt-br/office/visao-geral-de-formulas-no-excel-ecfdc708-9162-49e8-b993-c311f47ca173)

### Tabela IRPF 2025
- [Tabela Progressiva Mensal - Receita Federal](https://www.gov.br/receitafederal/pt-br/assuntos/orientacao-tributaria/tributos/irpf-imposto-de-renda-pessoa-fisica)

---

*Última atualização: Dezembro 2025*