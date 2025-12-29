# 🏛️ Estrutura das Planilhas

## 📊 Visão Geral

Este documento detalha a estrutura completa de cada aba da planilha `Controle_IR_2025.xlsx`, incluindo campos, validações, fórmulas e layout.

---

## 🎯 1. Dashboard

### Objetivo
Fornecer uma visão executiva consolidada de todos os dados fiscais com navegação rápida.

### Estrutura

#### Seção: Cabeçalho
```
Linha 1-2: Título "CONTROLE DE IMPOSTO DE RENDA 2025"
Linha 3: Subtítulo "RESUMO FISCAL 2025"
```

#### Seção: Indicadores Principais
| Indicador | Célula | Fórmula | Formato |
|-----------|---------|---------|--------|
| Rendimentos Totais | D4 | =SOMA(Rendimentos!E:E) | R$ #.##0,00 |
| Deduções Totais | D5 | =SOMA(Deduções!E:E) | R$ #.##0,00 |
| Despesas Profissionais | D6 | =SOMA(Despesas!E:E) | R$ #.##0,00 |
| Base de Cálculo | D7 | =D4-D5-D6 | R$ #.##0,00 |
| Imposto Estimado (15%) | D8 | =D7*0,15 | R$ #.##0,00 |
| Patrimônio Total | D9 | =SOMA(Bens!E:E) | R$ #.##0,00 |

#### Seção: Menu de Navegação
```
Colunas A-B (Linhas 12-17):
- Botão: Dashboard (aba atual)
- Botão: Rendimentos (link para aba)
- Botão: Deduções (link para aba)
- Botão: Despesas Profissionais (link para aba)
- Botão: Bens e Direitos (link para aba)
- Botão: Resumo Fiscal (link para aba)
```

#### Seção: Rodapé
```
Linha 20: "Atualizado em" | =HOJE()
```

### Cores e Formatação
- **Título**: Fonte Arial 18pt, Negrito, Centralizado
- **Indicadores**: Fonte Arial 12pt, Alinhamento à direita
- **Valores**: Fonte Arial 14pt, Negrito, Cor azul (#0066CC)
- **Botões**: Fundo cinza claro (#E8E8E8), Borda 1pt

---

## 💵 2. Rendimentos

### Objetivo
Registrar todos os tipos de rendimentos recebidos durante o ano-calendário.

### Estrutura da Tabela

| Coluna | Campo | Tipo | Validação | Largura |
|--------|-------|------|------------|--------|
| B | DATA | Data | dd/mm/aaaa | 12 |
| C | CATEGORIA | Lista | Salário, Aluguel, Honorários, Outros | 20 |
| D | DESCRIÇÃO | Texto | Máx 100 caracteres | 40 |
| E | VALOR | Moeda | > 0 | 15 |

### Categorias Disponíveis
1. **Salário**: Rendimentos de trabalho assalariado
2. **Aluguel**: Renda de locação de imóveis
3. **Honorários**: Pagamentos por serviços profissionais
4. **Outros**: Rendimentos diversos

### Fórmulas
```excel
TOTAL (Eúltima linha): =SOMA(E6:E1000)
```

### Layout
```
Linha 1-3: Cabeçalho "2. RENDIMENTOS"
Linha 4: "Registre seus lançamentos abaixo"
Linha 5: Cabeçalhos da tabela
Linha 6+: Dados (linhas de lançamento)
Última linha: TOTAL
```

### Menu de Navegação
Mesma estrutura do Dashboard nas colunas A-B

---

## 📋 3. Deduções

### Objetivo
Controlar gastos dedutíveis do imposto de renda.

### Estrutura da Tabela

| Coluna | Campo | Tipo | Validação | Largura |
|--------|-------|------|------------|--------|
| B | DATA | Data | dd/mm/aaaa | 12 |
| C | CATEGORIA | Lista | Ver categorias abaixo | 25 |
| D | DESCRIÇÃO | Texto | Máx 100 caracteres | 40 |
| E | VALOR | Moeda | > 0 | 15 |

### Categorias de Deduções
1. **Previdenciária (INSS)**: Contribuições obrigatórias e privadas
2. **Educação**: Despesas com ensino próprio e dependentes
3. **Saúde**: Planos de saúde, consultas, exames
4. **Dependentes**: Pensão alimentícia e outros gastos

### Limites de Dedução (IRPF 2025)
- **Educação**: R$ 3.561,50 por pessoa
- **Dependentes**: R$ 2.275,08 por dependente
- **Saúde**: Sem limite
- **Previdenciária**: Sem limite

### Fórmulas
```excel
TOTAL (Eúltima linha): =SOMA(E6:E1000)
```

### Layout
Idêntico à aba Rendimentos, com categorias específicas

---

## 💼 4. Despesas Profissionais

### Objetivo
Registrar despesas relacionadas à atividade profissional.

### Estrutura da Tabela

| Coluna | Campo | Tipo | Validação | Largura |
|--------|-------|------|------------|--------|
| B | DATA | Data | dd/mm/aaaa | 12 |
| C | CATEGORIA | Lista | Ver categorias abaixo | 25 |
| D | DESCRIÇÃO | Texto | Máx 100 caracteres | 40 |
| E | VALOR | Moeda | > 0 | 15 |

### Categorias de Despesas
1. **Material**: Suprimentos de escritório e insumos
2. **Software/Licenças**: Ferramentas digitais profissionais
3. **Aluguel**: Espaço comercial, coworking
4. **Energia/Água**: Contas de utilidades do espaço profissional
5. **Transporte**: Combustível, passagens relacionadas ao trabalho
6. **Outros**: Despesas profissionais diversas

### Fórmulas
```excel
TOTAL (Eúltima linha): =SOMA(E6:E1000)
```

### Observações
- Apenas profissionais autônomos podem deduzir despesas profissionais
- Mantenha comprovação documental de todas as despesas
- Limite de dedução pode variar conforme legislação

---

## 🏠 5. Bens e Direitos

### Objetivo
Inventário completo do patrimônio para declaração.

### Estrutura da Tabela

| Coluna | Campo | Tipo | Validação | Largura |
|--------|-------|------|------------|--------|
| B | DESCRIÇÃO | Texto | Máx 200 caracteres | 30 |
| C | LOCALIZAÇÃO | Texto | Endereço completo | 35 |
| D | DATA AQUISIÇÃO | Data | dd/mm/aaaa | 15 |
| E | VALOR | Moeda | > 0 | 15 |
| F | OBSERVAÇÕES | Texto | Livre | 30 |

### Tipos de Bens e Direitos

#### Imóveis
- Apartamentos
- Casas
- Terrenos
- Salas comerciais
- Garagens

#### Veículos
- Automóveis
- Motocicletas
- Barcos
- Aeronaves

#### Investimentos
- Ações
- Fundos de investimento
- Títulos públicos
- Poupança
- CDBs
- Criptomoedas

#### Outros Bens
- Joias
- Obras de arte
- Equipamentos profissionais
- Móveis e eletrodomésticos (acima de R$ 5.000)

### Fórmulas
```excel
TOTAL (Eúltima linha): =SOMA(E6:E1000)
```

### Observações Importantes
- Declarar bens acima de R$ 5.000,00 (limite de 2025)
- Usar valor de aquisição, não valor de mercado
- Para imóveis, incluir benfeitorias se houver
- Investimentos: usar saldo em 31/12 do ano-calendário

---

## 📈 6. Resumo Fiscal

### Objetivo
Consolidar automaticamente todos os dados para visão final da declaração.

### Estrutura

#### Seção: Consolidação

| Item | Célula | Fórmula | Formato |
|------|---------|---------|--------|
| Total de Rendimentos | D6 | =Rendimentos!E[fim] | R$ #.##0,00 |
| Total de Deduções | D7 | =Deduções!E[fim] | R$ #.##0,00 |
| Total de Despesas Profissionais | D8 | =Despesas!E[fim] | R$ #.##0,00 |
| Base de Cálculo | D9 | =D6-D7-D8 | R$ #.##0,00 |
| Imposto Estimado (15%) | D10 | =D9*0,15 | R$ #.##0,00 |
| Patrimônio Total Declarado | D11 | =Bens!E[fim] | R$ #.##0,00 |

### Fórmulas Detalhadas

#### Base de Cálculo
```excel
=MAX(0, [Rendimentos] - [Deduções] - [Despesas Profissionais])
```

#### Imposto Estimado (Simplificado - 15%)
```excel
=SE([Base de Cálculo] > 0, [Base de Cálculo] * 0,15, 0)
```

### Observações
- Cálculo simplificado para estimativa
- Alíquota real varia conforme tabela progressiva
- Consulte contador para cálculo preciso
- Valores negativos são tratados como zero

---

## 🔗 Relacionamentos entre Abas

```
[Dashboard]
    │
    ├──▶ [Rendimentos] ────────┐
    │                             │
    ├──▶ [Deduções] ─────────├──▶ [Resumo Fiscal]
    │                             │
    ├──▶ [Despesas Profissionais] ─┤
    │                             │
    └──▶ [Bens e Direitos] ──────┘
```

### Dependências de Dados
- **Dashboard** ← Lê de todas as outras abas
- **Resumo Fiscal** ← Lê de: Rendimentos, Deduções, Despesas, Bens
- **Demais abas** → Independentes (apenas entrada de dados)

---

## ⚙️ Configurações Globais

### Formatação de Números
```
Moeda: R$ #.##0,00
Data: dd/mm/aaaa
Percentual: 0,00%
```

### Proteção de Células
- **Células de fórmula**: Protegidas (não editáveis)
- **Células de entrada**: Desbloqueadas (editáveis)

### Validações de Dados
- **Datas**: Apenas datas válidas do ano-calendário
- **Valores**: Apenas números positivos
- **Categorias**: Listas suspensas predefinidas

---

## 📌 Notas Técnicas

### Performance
- Planilha otimizada para até 1.000 lançamentos por aba
- Fórmulas utilizam referências fixas para evitar recalculo excessivo
- Formatação condicional limitada para manter performance

### Compatibilidade
- Microsoft Excel 2016+
- LibreOffice Calc 7.0+
- Google Sheets (com limitações de formatação)

### Backup
Recomenda-se backup automático ou manual diário.

---

*Última atualização: Dezembro 2025*