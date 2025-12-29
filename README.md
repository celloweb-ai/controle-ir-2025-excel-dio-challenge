# 🧾 Organizador de Declaração de Imposto de Renda

<div align="center">

![Banner](https://img.shields.io/badge/IRPF-2025-green?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![DIO](https://img.shields.io/badge/DIO-Bootcamp-blueviolet?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completo-success?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.0.0-informational?style=for-the-badge)

**📊 Ferramenta Excel Profissional para Organização de IR 2025**

*Desenvolvido como parte do desafio DIO Bootcamp*

[🚀 Download](#-como-usar) •
[📖 Documentação](#-documentação-adicional) •
[✨ Funcionalidades](#-funcionalidades) •
[🎯 Roadmap](#-roadmap) •
[💬 FAQ](#-perguntas-frequentes-faq)

</div>

---

## 🎬 Preview Visual

<div align="center">

### 📊 Dashboard Executivo
![Dashboard](images/dashboard_screenshot.png)
*Painel executivo com resumo fiscal completo e navegação rápida*

### 💰 Gestão de Rendimentos
![Rendimentos](images/rendimentos_screenshot.png)
*Controle detalhado de todas as fontes de renda*

### 📈 Resumo Fiscal Consolidado
![Resumo](images/resumo_screenshot.png)
*Consolidação automática com cálculos de imposto*

</div>

---

## 📊 Sobre o Projeto

Esta é uma **ferramenta completa desenvolvida em Microsoft Excel** para auxiliar na organização e reunião de informações essenciais para a declaração de imposto de renda 2025. A solução foi construída como parte do desafio DIO Bootcamp, aplicando conceitos avançados de:

- 🎯 **Organização de Dados**: Estruturação lógica de informações fiscais
- ✅ **Validação de Dados**: Uso de validadores do Excel para garantir integridade
- 🔢 **Fórmulas e Funções**: Cálculos automáticos e consolidação de dados
- 🎨 **Interface de Usuário**: Design profissional e navegabilidade intuitiva
- 📚 **Documentação Técnica**: README estruturado e arquivos de suporte
- 🔄 **Controle de Versão**: Utilização do GitHub para versionamento

### 🎯 Objetivos Alcançados

| Objetivo | Status | Descrição |
|----------|--------|------------|
| ✅ Agregador de Dados | Completo | Sistema validado e eficiente para coleta de informações fiscais |
| ✅ Navegação Intuitiva | Completo | Menus interativos entre todas as abas |
| ✅ Validações Automáticas | Completo | Controle de entrada de dados em tempo real |
| ✅ Cálculos Automáticos | Completo | Resumo fiscal com cálculos dinâmicos |
| ✅ Interface Profissional | Completo | Design moderno e user-friendly |
| ✅ Documentação Completa | Completo | Guias técnicos e de usuário |

---

## ✨ Funcionalidades

### 📊 Dashboard Executivo
```
📈 Resumo Fiscal 2025
├── 💰 Rendimentos Totais
├── 📉 Deduções Totais
├── 💼 Despesas Profissionais
├── 📊 Base de Cálculo
├── 💵 Imposto Estimado (15%)
└── 🏠 Patrimônio Total
```
- ⏱️ Data de última atualização
- 🧭 Menu de navegação rápida entre abas
- 📊 Indicadores visuais coloridos

### 💵 Controle de Rendimentos
- 📅 Registro detalhado de lançamentos por data
- 🏷️ Categorias pré-definidas:
  - 💼 Salário
  - 🏠 Aluguel
  - 💰 Honorários
  - 📝 Outros rendimentos
- ➕ Soma automática de valores
- 💲 Formatação monetária brasileira (R$)

### 📋 Gestão de Deduções
- 🏷️ Categorias de deduções:
  - 🏛️ Previdenciária (INSS)
  - 📚 Educação
  - 🏥 Saúde
  - 👨‍👩‍👧‍👦 Dependentes
- 📅 Rastreamento por data e descrição
- 🔢 Totalização automática

### 💼 Despesas Profissionais
- 📦 Controle de despesas dedutíveis:
  - 📎 Material de escritório
  - 💻 Software/Licenças
  - 🏢 Aluguel comercial
  - ⚡ Energia/Água
  - 🚗 Transporte profissional
- 📊 Organização cronológica
- 🧮 Cálculo automático de totais

### 🏠 Bens e Direitos
- 📋 Registro de patrimônio:
  - 🏠 Imóveis (residenciais e comerciais)
  - 🚗 Veículos
  - 📈 Investimentos (ações, títulos, fundos)
  - 💎 Outros bens
- 📝 Campos detalhados:
  - 📄 Descrição completa
  - 📍 Localização
  - 📅 Data de aquisição
  - 💰 Valor atualizado
  - 📌 Observações
- 🔢 Soma automática do patrimônio total

### 📈 Resumo Fiscal Automático
- 🔄 Consolidação de todos os lançamentos
- 🧮 Cálculos automáticos:
  - 📊 Base de cálculo (Rendimentos - Deduções - Despesas)
  - 💵 Imposto estimado (alíquota de 15%)
  - 🏠 Patrimônio total declarado
- 👀 Visão consolidada para declaração

---

## 📁 Estrutura do Projeto

```
Organizador_Declaracao_Imposto_Renda/
│
├── 📄 README.md                      # Documentação principal
├── 📜 LICENSE                        # Licença MIT
├── 📝 CONTRIBUTING.md                # Guia de contribuição
├── 📋 CHANGELOG.md                   # Histórico de versões
├── ⚙️ .gitattributes                 # Git LFS para arquivos Excel
│
├── 📂 excel/
│   ├── 📊 Controle_IR_2025.xlsx      # Planilha principal
│   ├── 🏦 bancos_apoio.xlsx          # Lista de bancos (validador)
│   └── 📘 projeto_completo.xlsx      # Exemplo completo
│
├── 📂 scripts/
│   └── 📝 script_de_alinhamentos.txt # VBA para alinhamento de ícones
│
├── 📂 docs/
│   ├── 📖 ESTRUTURA.md               # Estrutura das planilhas
│   ├── 🔢 FORMULAS.md                # Documentação de fórmulas
│   └── 📘 GUIA_USO.md                # Guia passo a passo
│
└── 📂 images/
    ├── 🖼️ dashboard_screenshot.png   # Screenshot do Dashboard
    ├── 🖼️ rendimentos_screenshot.png # Screenshot de Rendimentos
    └── 🖼️ resumo_screenshot.png      # Screenshot do Resumo
```

---

## 🚀 Como Usar

### 📋 Pré-requisitos

- ✅ Microsoft Excel 2016 ou superior
- ✅ Windows, macOS ou Linux (com LibreOffice Calc)
- ✅ Conhecimentos básicos de Excel

### 📥 Instalação

#### Método 1: Clone via Git

```bash
# Clone o repositório
git clone https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda.git

# Entre no diretório
cd Organizador_Declaracao_Imposto_Renda
```

#### Método 2: Download Direto

1. Clique no botão verde **"Code"**
2. Selecione **"Download ZIP"**
3. Extraia os arquivos em uma pasta local

### 🎯 Primeiros Passos

#### 1️⃣ Abra a Planilha Principal

```
📂 excel/ → 📊 Controle_IR_2025.xlsx
```

#### 2️⃣ Navegue pelas Abas

- Use os **botões de navegação** no Dashboard
- Ou clique nas **abas** na parte inferior

#### 3️⃣ Preencha Seus Dados

| Aba | O que inserir | Exemplo |
|-----|---------------|----------|
| 💰 **Rendimentos** | Data, categoria, descrição e valor | 15/01/2025, Salário, Pagamento mensal, R$ 5.000,00 |
| 📉 **Deduções** | Gastos dedutíveis por categoria | 20/02/2025, Saúde, Plano de saúde, R$ 450,00 |
| 💼 **Despesas** | Despesas relacionadas ao trabalho | 10/03/2025, Software, Licença Office, R$ 300,00 |
| 🏠 **Bens** | Patrimônio detalhadamente | Apartamento, Rua X 123, 2020, R$ 300.000,00 |

#### 4️⃣ Consulte o Resumo

- Acesse **"Resumo Fiscal"** ou **"Dashboard"**
- 🔄 Todos os cálculos são atualizados automaticamente

### 💡 Dicas de Ouro

| 💡 Dica | Descrição |
|---------|------------|
| 💾 **Backup Regular** | Salve cópias da planilha antes de grandes alterações |
| 🏷️ **Use Categorias** | Padronize seus lançamentos com as categorias pré-definidas |
| 👀 **Monitore** | Verifique o resumo fiscal periodicamente |
| 📄 **Documentos** | Mantenha recibos e notas organizados fisicamente |
| 📘 **Consulte Exemplos** | Use `projeto_completo.xlsx` para ver exemplos |

---

## 📚 Documentação Adicional

### 📖 Arquivos de Documentação

| Documento | Descrição | Link |
|-----------|-----------|------|
| 📖 **ESTRUTURA.md** | Documentação detalhada de cada aba | [Ver arquivo](docs/ESTRUTURA.md) |
| 🔢 **FORMULAS.md** | Explicação de todas as fórmulas | [Ver arquivo](docs/FORMULAS.md) |
| 📘 **GUIA_USO.md** | Guia passo a passo para iniciantes | [Ver arquivo](docs/GUIA_USO.md) |
| 📝 **CONTRIBUTING.md** | Como contribuir com o projeto | [Ver arquivo](CONTRIBUTING.md) |
| 📋 **CHANGELOG.md** | Histórico de versões e mudanças | [Ver arquivo](CHANGELOG.md) |

### 🔗 Recursos Externos

#### 📘 Microsoft Excel
- [Documentação do Excel](https://support.microsoft.com/pt-br/excel)
- [Fórmulas e Funções](https://support.microsoft.com/pt-br/office/formulas-e-funcoes-do-excel)
- [Validação de Dados](https://support.microsoft.com/pt-br/office/aplicar-validação-de-dados-a-celulas)

#### 🐙 GitHub
- [GitHub Quick Start](https://github.com/digitalinnovationone/github-quickstart)
- [Formação GitHub Certification](https://aline-antunes.gitbook.io/formacao-fundamentos-github)
- [Documentação GitHub](https://docs.github.com/pt)

#### 🏛️ Receita Federal
- [Portal IRPF 2025](https://www.gov.br/receitafederal/pt-br/assuntos/meu-imposto-de-renda)
- [Perguntas e Respostas](https://www.gov.br/receitafederal/pt-br/centrais-de-conteudo/publicacoes/perguntas-e-respostas/dirpf)

---

## 🎯 Roadmap

### ✅ Versão 1.0.0 (Atual)

- [x] Dashboard executivo com resumo fiscal
- [x] Módulo de rendimentos com categorias
- [x] Gestão de deduções e despesas
- [x] Controle de bens e direitos
- [x] Cálculos automáticos de imposto
- [x] Validações de dados
- [x] Documentação completa
- [x] Screenshots e exemplos

### 🔄 Versão 1.1.0 (Em Planejamento)

- [ ] 📊 Gráficos visuais no Dashboard
- [ ] 🔒 Proteção de células com senha
- [ ] 📅 Calendário de prazos da Receita Federal
- [ ] 💾 Função de exportação para PDF
- [ ] 🎨 Temas de cores personalizáveis
- [ ] 📱 Otimização para Excel Mobile

### 🚀 Versão 2.0.0 (Futuro)

- [ ] 🌐 Versão web da ferramenta
- [ ] 🤖 Integração com IA para sugestões
- [ ] ☁️ Sincronização com nuvem
- [ ] 📲 Aplicativo mobile nativo
- [ ] 🔗 Importação de dados bancários
- [ ] 📄 Geração automática de DARF

---

## ❓ Perguntas Frequentes (FAQ)

<details>
<summary><b>❓ A planilha funciona no Google Sheets?</b></summary>

> A planilha foi desenvolvida para Microsoft Excel, mas pode funcionar parcialmente no Google Sheets. Algumas funcionalidades avançadas e formatações podem não ser totalmente compatíveis. Recomendamos usar Excel ou LibreOffice Calc para melhor experiência.

</details>

<details>
<summary><b>❓ Posso usar em versões antigas do Excel?</b></summary>

> Recomendamos Excel 2016 ou superior para garantir compatibilidade total. Versões anteriores podem apresentar problemas com algumas fórmulas e validações.

</details>

<details>
<summary><b>❓ Como faço backup dos meus dados?</b></summary>

> Simplesmente salve uma cópia do arquivo `Controle_IR_2025.xlsx` com um nome diferente (exemplo: `Controle_IR_2025_Backup_29-12-2025.xlsx`). Recomendamos fazer backups semanais.

</details>

<details>
<summary><b>❓ A ferramenta calcula o imposto devido com precisão?</b></summary>

> A ferramenta fornece uma **estimativa** baseada na alíquota básica de 15%. O cálculo oficial do imposto depende de diversos fatores adicionais (faixa de renda, dependentes, etc.) e deve ser verificado no programa oficial da Receita Federal.

</details>

<details>
<summary><b>❓ Posso modificar as categorias?</b></summary>

> Sim! As categorias podem ser personalizadas diretamente nas células de validação. Consulte a documentação técnica em `docs/ESTRUTURA.md` para instruções detalhadas.

</details>

<details>
<summary><b>❓ Como reporto um bug ou sugiro melhorias?</b></summary>

> Você pode:
> - Abrir uma [Issue](https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda/issues) no GitHub
> - Enviar um email para marcus@vasconcellos.net.br
> - Conectar-se no [LinkedIn](https://www.linkedin.com/in/marcusvasconcellos)

</details>

<details>
<summary><b>❓ O projeto está sob qual licença?</b></summary>

> O projeto está licenciado sob a **Licença MIT**, o que significa que você pode usar, modificar e distribuir livremente, desde que mantenha os créditos originais.

</details>

---

## 👨‍💻 Autor

<div align="center">

### Marcus Vasconcellos

**Engenheiro de Eletrônica e Computação | MBA | Especialista em Automação Industrial e Cibersegurança**

[![GitHub](https://img.shields.io/badge/GitHub-celloweb--ai-181717?style=for-the-badge&logo=github)](https://github.com/celloweb-ai)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Marcus_Vasconcellos-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/marcusvasconcellos)
[![Email](https://img.shields.io/badge/Email-marcus@vasconcellos.net.br-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:marcus@vasconcellos.net.br)
[![Website](https://img.shields.io/badge/Company-@Prio3-orange?style=for-the-badge)](https://github.com/Prio3)

</div>

#### 🎓 Sobre

Engenheiro com mais de **20 anos de experiência** em liderança de projetos complexos de automação industrial e cibersegurança. Atualmente desenvolvendo projetos de **IA generativa** e **automação** na [@Prio3](https://github.com/Prio3).

#### 🏆 Especializações

- 🏭 Automação Industrial (ABB 800xA, Autronica Autrosafe)
- 🔒 Cibersegurança
- 🤖 Inteligência Artificial Generativa
- 📊 Análise de Dados
- 💼 Gestão de Projetos

---

## 🎓 Sobre o Desafio DIO

<div align="center">

![DIO](https://img.shields.io/badge/Digital_Innovation_One-Bootcamp-blueviolet?style=for-the-badge)

</div>

Este projeto foi desenvolvido como parte do **DIO Bootcamp** (Digital Innovation One), aplicando conceitos avançados de:

### 📚 Conceitos Aplicados

```
✅ Organização e estruturação de dados
✅ Criação de interfaces funcionais e amigáveis
✅ Documentação técnica profissional
✅ Controle de versão com Git e GitHub
✅ Boas práticas de desenvolvimento
✅ Validações e automações
```

### 🎯 Objetivos de Aprendizagem Alcançados

| Objetivo | Status |
|----------|--------|
| Aplicar conceitos em ambiente prático | ✅ Completo |
| Documentar processos técnicos | ✅ Completo |
| Utilizar GitHub profissionalmente | ✅ Completo |
| Criar solução robusta | ✅ Completo |
| Implementar validações e automações | ✅ Completo |

---

## 📝 Licença

Este projeto está licenciado sob a **Licença MIT** - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

### 📜 Resumo da Licença

```
✅ Uso comercial permitido
✅ Modificação permitida
✅ Distribuição permitida
✅ Uso privado permitido
❗ Sem garantia
❗ Créditos ao autor devem ser mantidos
```

---

## ⭐ Contribuições

<div align="center">

### 🤝 Como Contribuir

**Contribuições são muito bem-vindas!**

[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=for-the-badge)](CONTRIBUTING.md)

</div>

### 📋 Processo de Contribuição

1. **Fork** o projeto
2. Crie uma **branch** para sua feature
   ```bash
   git checkout -b feature/MinhaFeature
   ```
3. **Commit** suas mudanças
   ```bash
   git commit -m '✨ Adiciona MinhaFeature'
   ```
4. **Push** para a branch
   ```bash
   git push origin feature/MinhaFeature
   ```
5. Abra um **Pull Request**

### 💡 Ideias para Contribuir

- 📊 Adicionar mais categorias de rendimentos
- 🎨 Criar novos temas visuais
- 📈 Implementar gráficos dinâmicos
- 🌐 Traduzir para outros idiomas
- 📝 Melhorar a documentação
- 🐛 Reportar e corrigir bugs

---

## 📞 Suporte e Contato

### 💬 Precisa de Ajuda?

| Canal | Como Usar |
|-------|------------|
| 🐛 **GitHub Issues** | [Reportar bugs ou solicitar features](https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda/issues) |
| 💼 **LinkedIn** | [Conectar profissionalmente](https://www.linkedin.com/in/marcusvasconcellos) |
| 📧 **Email** | marcus@vasconcellos.net.br |

### 📊 Status do Projeto

![GitHub last commit](https://img.shields.io/github/last-commit/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=flat-square)

---

## 🙏 Agradecimentos

- 💜 **[Digital Innovation One (DIO)](https://www.dio.me/)** - Pela plataforma de aprendizado
- 🏢 **[@Prio3](https://github.com/Prio3)** - Pelo suporte e ambiente de desenvolvimento
- 👥 **Comunidade GitHub** - Pelas contribuições e feedback
- 🎓 **Todos os estudantes** que usarem esta ferramenta

---

<div align="center">

## 💜 Desenvolvido com paixão por [Marcus Vasconcellos](https://github.com/celloweb-ai)

**Projeto DIO Bootcamp 2025** | [Digital Innovation One](https://www.dio.me/)

---

### ⭐ Se este projeto foi útil para você, considere dar uma estrela!

[![GitHub stars](https://img.shields.io/github/stars/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=social)](https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda/stargazers)
[![GitHub watchers](https://img.shields.io/github/watchers/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=social)](https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda/watchers)
[![GitHub forks](https://img.shields.io/github/forks/celloweb-ai/Organizador_Declaracao_Imposto_Renda?style=social)](https://github.com/celloweb-ai/Organizador_Declaracao_Imposto_Renda/network/members)

---

**📅 Última atualização:** Dezembro 2025

**🔖 Versão:** 1.0.0

</div>