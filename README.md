# SISCOMEX — Simulador Didático de Treinamento

> Ferramenta pedagógica para a disciplina de **Comércio Exterior** do curso de **Administração — UFCAT**

---

## 🔵 Acesso rápido

**[▶ Abrir o simulador](https://wildsonbrandao.github.io/siscomex-treinamento/)**

---

## Sobre

Simulador de preenchimento da **Declaração de Importação (DI)** no SISCOMEX, desenvolvido para uso didático em sala de aula. Permite que os alunos vivenciem o fluxo real de uma operação de importação brasileira sem depender de acesso ao sistema federal.

**Desenvolvido por:** [WB Consultoria Empresarial](https://wbconsultoria.com.br) — Wildson Brandão  
**Instituição:** UFCAT — Universidade Federal de Catalão  
**Disciplina:** Comércio Exterior — Curso de Administração

---

## Funcionalidades

| Recurso | Descrição |
|---|---|
| 🗂 7 abas da DI | Importador, Exportador, Mercadoria, Transporte, Câmbio, Tributos, Registro |
| 📦 3 cenários pré-prontos | Básico (suplementos/EUA), Intermediário (equipamentos/Alemanha), Avançado (API farmacêutico/China) |
| 🔒 Controle de acesso | Login por e-mail — professor libera alunos individualmente |
| 🎛 Painel do professor | Gerencia e-mails, libera cenários por turma, exporta/importa lista de alunos |
| ✅ Validação por aba | Avanço bloqueado até todos os campos obrigatórios estarem preenchidos |
| 🧮 Cálculo tributário | II, IPI, PIS, COFINS e ICMS calculados em cascata sobre o Valor Aduaneiro (CIF) |
| 📋 Checklist documental | Invoice, Packing List, BL/AWB, Certificado de Origem, LI, ANVISA etc. |

---

## Como usar

### Para o professor

1. Faça o download do arquivo `index.html`
2. Publique no GitHub Pages (veja abaixo) ou distribua diretamente para os alunos
3. Edite a lista de e-mails autorizados no início do script:

```javascript
var authorizedEmails = [
  { email: "professor@ufcat.edu.br", role: "professor" },
  { email: "aluno1@discente.ufcat.edu.br", role: "aluno" },
  // ...
];
```

4. Faça login com seu e-mail de professor — o painel ⚙ aparecerá no canto inferior direito
5. Use o painel para liberar os cenários no momento certo da aula

### Para os alunos

1. Acesse o link fornecido pelo professor
2. Digite seu e-mail institucional
3. Preencha a DI aba por aba — não é possível avançar sem completar os campos obrigatórios
4. Use o cenário liberado pelo professor ou preencha manualmente

---

## Publicação no GitHub Pages

```bash
# 1. Crie um repositório público no GitHub chamado "siscomex-treinamento"

# 2. Clone o repositório
git clone https://github.com/[seu-usuario]/siscomex-treinamento.git
cd siscomex-treinamento

# 3. Copie o arquivo HTML como index.html
cp siscomex_simulador.html index.html

# 4. Commit e push
git add index.html
git commit -m "feat: simulador SISCOMEX v1.0.0"
git push origin main

# 5. Ative o GitHub Pages
# Repositório → Settings → Pages → Source: Deploy from branch → main / (root)
# O simulador ficará disponível em: https://[seu-usuario].github.io/siscomex-treinamento/
```

---

## Estrutura do repositório

```
siscomex-treinamento/
│
├── index.html          ← Simulador completo (arquivo único, sem dependências)
└── README.md           ← Esta documentação
```

O simulador é um **arquivo HTML único, sem dependências externas** — não requer servidor, banco de dados ou instalação de pacotes. Funciona diretamente no navegador.

---

## Tributos simulados

| Tributo | Base de Cálculo | Fundamentação |
|---|---|---|
| II — Imposto de Importação | CIF (R$) | TEC — MDIC / NCM |
| IPI | CIF + II | TIPI — Receita Federal |
| PIS/Importação (2,10%) | CIF + II + IPI | Lei 10.865/2004 |
| COFINS/Importação (9,65%) | CIF + II + IPI | Lei 10.865/2004 |
| ICMS (por dentro) | CIF + II + IPI + PIS + COFINS + despesas | CONFAZ |

> ⚠️ As alíquotas são **ilustrativas** para fins didáticos. As alíquotas reais dependem da NCM, acordos internacionais, estado de desembaraço e regime tributário do importador.

---

## Cenários disponíveis

### 📦 Básico — Suplementos Alimentares
- **Importador:** Camargo Suplementos Ltda (GO) — Simples Nacional
- **Produto:** Whey Protein 80% (NCM 2106.90.10) — 500 kg a USD 8,50/kg
- **Rota:** EUA → Porto de Santos (Marítimo) | PTAX: R$ 5,25
- **Foco:** fluxo básico, II de 10%, canal Verde

### ⚙️ Intermediário — Equipamentos Industriais
- **Importador:** MG Distribuição Industrial (MG) — Lucro Real
- **Produtos:** Redutor de velocidade + Motor elétrico (2 adições)
- **Rota:** Alemanha → Porto de Paranaguá (Marítimo) | PTAX: R$ 5,72 (EUR)
- **Foco:** Drawback, múltiplas adições, LI INMETRO, canal Amarelo

### 🏭 Avançado — API Farmacêutico
- **Importador:** FarmaInsumos Brasil S/A (SC) — Lucro Real
- **Produtos:** 3 princípios ativos (Amoxicilina, Eritromicina, Metronidazol)
- **Rota:** China → Porto de Itajaí (Marítimo) | PTAX: R$ 5,18
- **Foco:** LI ANVISA, SGP, 3 adições, canal Vermelho, alto risco regulatório

---

## Aviso legal

> Este simulador é uma **ferramenta didática** desenvolvida exclusivamente para fins de treinamento acadêmico. **Não possui qualquer validade fiscal, jurídica ou aduaneira.** Os dados, valores e cálculos apresentados são ilustrativos. Para operações reais de importação, consulte sempre a Receita Federal do Brasil, um despachante aduaneiro habilitado e a legislação vigente.

---

## Licença

MIT — uso didático livre com manutenção dos créditos ao autor.

```
Copyright (c) 2025 WB Consultoria Empresarial — Wildson Brandão
```
