# 🔢 Documentação de Fórmulas

## 📊 Fórmulas Utilizadas no Projeto

Documentação completa de todas as fórmulas do Excel utilizadas na planilha **Controle_IR_2025.xlsx**.

---

## 📊 Dashboard

### Rendimentos Totais
```excel
=SOMA(Rendimentos!D:D)
```
**Função:** Soma todos os valores da coluna D (Valor) da aba Rendimentos
**Resultado:** Valor total de todos os rendimentos registrados

### Deduções Totais
```excel
=SOMA(Deducoes!D:D)
```
**Função:** Soma todos os valores da coluna D da aba Deduções
**Resultado:** Valor total de todas as deduções

### Despesas Profissionais
```excel
=SOMA(Despesas!D:D)
```
**Função:** Soma todos os valores da coluna D da aba Despesas
**Resultado:** Valor total das despesas profissionais

### Base de Cálculo
```excel
=B4-B5-B6
```
**Função:** Calcula a base tributável
**Fórmula:** Rendimentos - Deduções - Despesas
**Resultado:** Valor sobre o qual o imposto é calculado

### Imposto Estimado (15%)
```excel
=B7*0.15
```
**Função:** Calcula imposto simples de 15%
**Observação:** Esta é uma **estimativa simplificada**. O cálculo oficial considera:
- Tabela progressiva de alíquotas
- Deduções específicas por faixa
- Imposto retido na fonte

### Patrimônio Total
```excel
=SOMA(Bens!E:E)
```
**Função:** Soma todos os valores da coluna E (Valor) da aba Bens
**Resultado:** Valor total do patrimônio declarado

### Data de Atualização
```excel
=HOJE()
```
**Função:** Retorna a data atual do sistema
**Formato:** DD/MM/AAAA
**Atualização:** Automática ao abrir o arquivo

---

## 💰 Rendimentos

### Total de Rendimentos
```excel
=SOMA(D2:D1000)
```
**Função:** Soma valores de rendimento (linhas 2 a 1000)
**Localização:** Última linha da coluna D
**Formato:** R$ #.##0,00

### Validação de Categoria
```excel
Lista: Salário;Aluguel;Honorários;Outros
```
**Tipo:** Validação de Lista
**Aplica-se à:** Coluna B (Categoria)
**Permite:** Apenas valores pré-definidos

### Formatação Condicional - Valores Altos
```excel
=D2>10000
```
**Condição:** Se valor > R$ 10.000,00
**Formato:** Fundo verde claro
**Objetivo:** Destacar rendimentos significativos

---

## 📉 Deduções

### Total de Deduções
```excel
=SOMA(D2:D1000)
```
**Função:** Soma todas as deduções registradas
**Formato:** R$ #.##0,00

### Validação de Categoria
```excel
Lista: Previdência (INSS);Educação;Saúde;Dependentes
```
**Tipo:** Validação de Lista
**Aplica-se à:** Coluna B

### Alerta de Limite - Educação
```excel
=SOMASE(B:B;"Educação";D:D)>3561.50
```
**Condição:** Se total de Educação > R$ 3.561,50
**Formato:** Fundo amarelo + Mensagem de alerta
**Mensagem:** "Atenção: Limite de dedução de educação excedido"

---

## 💼 Despesas Profissionais

### Total de Despesas
```excel
=SOMA(D2:D1000)
```
**Função:** Soma todas as despesas profissionais
**Formato:** R$ #.##0,00

### Validação de Categoria
```excel
Lista: Material;Software;Aluguel;Energia;Água;Transporte
```
**Tipo:** Validação de Lista
**Aplica-se à:** Coluna B

### Total por Categoria
```excel
=SOMASE(B:B;"Software";D:D)
```
**Função:** Soma despesas de uma categoria específica
**Exemplo:** Total gasto em Software/Licenças

---

## 🏠 Bens e Direitos

### Patrimônio Total
```excel
=SOMA(E2:E1000)
```
**Função:** Soma valor de todos os bens declarados
**Formato:** R$ #.##0,00

### Validação de Tipo
```excel
Lista: Imóvel Residencial;Imóvel Comercial;Veículo;Investimentos;Outros
```
**Tipo:** Validação de Lista
**Aplica-se à:** Coluna A (Tipo)

### Total por Tipo de Bem
```excel
=SOMASE(A:A;"Veículo";E:E)
```
**Função:** Soma valor de um tipo específico de bem
**Exemplo:** Total investido em veículos

### Bens Adquiridos no Ano
```excel
=SOMASE(D:D;">="&DATA(2025;1;1);E:E)
```
**Função:** Soma bens adquiridos a partir de 01/01/2025
**Uso:** Identificar aquisições recentes

---

## 📈 Resumo Fiscal

### Todas as Fórmulas do Resumo

#### 1. Total de Rendimentos
```excel
=SOMA(Rendimentos!D:D)
```

#### 2. Total de Deduções
```excel
=SOMA(Deducoes!D:D)
```

#### 3. Total de Despesas
```excel
=SOMA(Despesas!D:D)
```

#### 4. Base de Cálculo
```excel
=B4-B5-B6
```

#### 5. Alíquota Efetiva
```excel
=SE(B7>0;B8/B7;0)
```
**Função:** Calcula % de imposto sobre rendimento
**Formato:** Percentual (0,00%)

#### 6. Patrimônio Declarado
```excel
=SOMA(Bens!E:E)
```

#### 7. Variação Patrimonial
```excel
=SE(H2>0;(B9-H2)/H2;0)
```
**Função:** Calcula variação % vs. ano anterior
**Requer:** Valor do patrimônio do ano anterior em H2

---

## 🧐 Fórmulas Avançadas

### Média Mensal de Rendimentos
```excel
=SOMA(Rendimentos!D:D)/12
```
**Função:** Divide total por 12 meses
**Uso:** Planejamento financeiro

### Rendimentos por Período
```excel
=SOMASES(Rendimentos!D:D;Rendimentos!A:A;">="&DATA(2025;1;1);Rendimentos!A:A;"<="&DATA(2025;3;31))
```
**Função:** Soma rendimentos do 1º trimestre
**Parâmetros:** Data inicial e final

### Maior Despesa Registrada
```excel
=MÁXIMO(Despesas!D:D)
```
**Função:** Identifica maior valor de despesa
**Complementar:** Usar `=ÍNDICE()` e `=CORRESP()` para identificar descrição

### Contador de Lançamentos
```excel
=CONT.VALORES(Rendimentos!D:D)-1
```
**Função:** Conta quantos rendimentos foram registrados
**-1:** Desconta linha de cabeçalho

---

## ⚠️ Observações Importantes

### 🚨 Limitações do Cálculo
1. **Alíquota simplificada:** O cálculo usa 15% fixo, mas o IR tem tabela progressiva
2. **Deduções:** Alguns limites não são verificados automaticamente
3. **Imposto retido:** Não considera IRRF já descontado

### 🔧 Manutenção
- **Atualizar anualmente:** Limites de dedução mudam
- **Validar categorias:** Adicionar novas conforme necessário
- **Testar fórmulas:** Após qualquer alteração estrutural

### 📚 Referências
- [Tabela Progressiva IR 2025](https://www.gov.br/receitafederal)
- [Limites de Dedução](https://www.gov.br/receitafederal/pt-br/assuntos/meu-imposto-de-renda)

---

💜 **Dica:** Para modificar fórmulas, sempre faça um backup da planilha antes!