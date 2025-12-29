# 🏛️ Estrutura das Planilhas

## 📊 Visão Geral

O arquivo **Controle_IR_2025.xlsx** é composto por 6 abas principais, cada uma com uma função específica no processo de organização da declaração de imposto de renda.

---

## 1️♣ Dashboard

### 🎯 Objetivo
Centralizar informações fiscais e facilitar navegação.

### 🗂️ Estrutura

| Célula | Conteúdo | Fórmula/Validação |
|--------|----------|---------------------|
| **B4** | Rendimentos Totais | `=SOMA(Rendimentos!D:D)` |
| **B5** | Deduções Totais | `=SOMA(Deducoes!D:D)` |
| **B6** | Despesas Profissionais | `=SOMA(Despesas!D:D)` |
| **B7** | Base de Cálculo | `=B4-B5-B6` |
| **B8** | Imposto Estimado (15%) | `=B7*0.15` |
| **B9** | Patrimônio Total | `=SOMA(Bens!E:E)` |
| **B11** | Data de Atualização | `=HOJE()` |

### 🎨 Formatação
- **Cores:** Verde para valores positivos, Vermelho para alertas
- **Fonte:** Calibri 14pt para títulos, 12pt para valores
- **Bordas:** Linhas sólidas ao redor de cada seção

### 🔘 Botões de Navegação
Botões com hyperlinks para cada aba:
```vba
=HYPERLINK("#Rendimentos!A1","💰 Rendimentos")
=HYPERLINK("#Deducoes!A1","📉 Deduções")
=HYPERLINK("#Despesas!A1","💼 Despesas")
=HYPERLINK("#Bens!A1","🏠 Bens")
=HYPERLINK("#Resumo!A1","📈 Resumo")
```

---

## 2️♣ Rendimentos

### 🎯 Objetivo
Registrar todas as fontes de renda do contribuinte.

### 📊 Colunas

| Coluna | Título | Tipo | Validação |
|--------|---------|------|-------------|
| **A** | Data | Data | Formato: DD/MM/AAAA |
| **B** | Categoria | Lista | Salário, Aluguel, Honorários, Outros |
| **C** | Descrição | Texto | Máximo 255 caracteres |
| **D** | Valor | Moeda | Formato: R$ #.##0,00 |

### 📋 Categorias Disponíveis
```
💼 Salário
🏠 Aluguel Recebido
💰 Honorários Profissionais
📈 Investimentos (Dividendos)
📄 Outros Rendimentos
```

### 🔢 Linha de Total
**Última linha:** `=SOMA(D2:D1000)` - Soma automática

---

## 3️♣ Deduções

### 🎯 Objetivo
Controlar gastos dedutíveis do IR.

### 📊 Colunas

| Coluna | Título | Tipo | Validação |
|--------|---------|------|-------------|
| **A** | Data | Data | Formato: DD/MM/AAAA |
| **B** | Categoria | Lista | INSS, Educação, Saúde, Dependentes |
| **C** | Descrição | Texto | Máximo 255 caracteres |
| **D** | Valor | Moeda | Formato: R$ #.##0,00 |

### 🏛️ Categorias e Limites (2025)

| Categoria | Limite Anual | Observações |
|-----------|--------------|----------------|
| **🏛️ Previdência (INSS)** | Sem limite | Contribuições oficiais |
| **🎓 Educação** | R$ 3.561,50 por pessoa | Ensino formal |
| **🏥 Saúde** | Sem limite | Despesas médicas comprovadas |
| **👨‍👩‍👧‍👦 Dependentes** | R$ 2.275,08 por dependente | Por ano |

---

## 4️♣ Despesas Profissionais

### 🎯 Objetivo
Registrar despesas relacionadas à atividade profissional.

### 📊 Colunas

| Coluna | Título | Tipo | Validação |
|--------|---------|------|-------------|
| **A** | Data | Data | Formato: DD/MM/AAAA |
| **B** | Categoria | Lista | Material, Software, Aluguel, Energia, Transporte |
| **C** | Descrição | Texto | Máximo 255 caracteres |
| **D** | Valor | Moeda | Formato: R$ #.##0,00 |

### 💼 Categorias para Profissionais Autônomos
```
📏 Material de Escritório
💻 Software e Licenças
🏬 Aluguel Comercial
⚡ Energia e Água
🚗 Transporte Profissional
📡 Internet e Telefonia
```

---

## 5️♣ Bens e Direitos

### 🎯 Objetivo
Declarar patrimônio do contribuinte.

### 📊 Colunas

| Coluna | Título | Tipo | Validação |
|--------|---------|------|-------------|
| **A** | Tipo | Lista | Imóvel, Veículo, Investimento, Outros |
| **B** | Descrição | Texto | Máximo 500 caracteres |
| **C** | Localização | Texto | Endereço completo |
| **D** | Data Aquisição | Data | Formato: DD/MM/AAAA |
| **E** | Valor | Moeda | Formato: R$ #.##0,00 |
| **F** | Observações | Texto | Informações adicionais |

### 🏗️ Tipos de Bens
```
🏠 Imóvel Residencial
🏬 Imóvel Comercial
🚗 Veículo
📈 Ações e Fundos
💰 Títulos Públicos
💳 Aplicações Financeiras
💎 Outros Bens
```

---

## 6️♣ Resumo Fiscal

### 🎯 Objetivo
Consolidar todos os dados para visão final.

### 📊 Estrutura de Cálculos

```
┌──────────────────────────┐
│ RESUMO FISCAL 2025       │
├──────────────────────────┤
│ Rendimentos       R$ XXX │
│ (-) Deduções      R$ XXX │
│ (-) Despesas       R$ XXX │
├──────────────────────────┤
│ Base de Cálculo   R$ XXX │
│ Imposto (15%)     R$ XXX │
├──────────────────────────┤
│ Patrimônio Total  R$ XXX │
└──────────────────────────┘
```

### 📄 Fórmulas do Resumo

| Item | Fórmula | Descrição |
|------|---------|-------------|
| **Total Rendimentos** | `=SOMA(Rendimentos!D:D)` | Soma todos os rendimentos |
| **Total Deduções** | `=SOMA(Deducoes!D:D)` | Soma todas as deduções |
| **Total Despesas** | `=SOMA(Despesas!D:D)` | Soma todas as despesas |
| **Base de Cálculo** | `=B4-B5-B6` | Rendimentos - Deduções - Despesas |
| **Imposto Estimado** | `=B7*0.15` | 15% da base de cálculo |
| **Patrimônio Total** | `=SOMA(Bens!E:E)` | Soma valor de todos os bens |

---

## 🔒 Proteções e Validações

### 🚫 Células Bloqueadas
- Células de fórmula estão protegidas contra edição acidental
- Apenas campos de entrada estão liber