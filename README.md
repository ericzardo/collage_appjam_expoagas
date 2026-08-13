# 🚀 CashbackStrat 1.0: Inteligência em Fidelização
> **Simulador de Sustentabilidade Financeira para Campanhas de Cashback.**

O **CashbackStrat** é a "calculadora de bolso do CMO", desenvolvida especificamente para o setor supermercadista (Varejo Alimentar). Ele transforma a complexidade das planilhas financeiras em uma interface dinâmica de tomada de decisão, permitindo que gestores validem se uma promoção de cashback gera crescimento real ou apenas erosão de margem.

---

## 🎯 1. Visão Estratégica e Proposta de Valor

No varejo de margens apertadas (referência: *Revista AGAS, pág. 24*), o cashback é uma faca de dois gumes. Se mal planejado, ele se torna um desconto tardio que destrói o lucro. O **CashbackStrat** atua em três pilares:

1.  **Proteção de Margem:** Garante que o custo do benefício nunca supere o lucro bruto da venda.
2.  **Foco no Upsell:** Utiliza o "Gatilho de Ativação" para forçar o aumento do ticket médio.
3.  **Eficiência de Marketing:** Compara o custo de manter um cliente atual (Cashback) contra o custo de adquirir um novo (CAC Social Media).

---

## 🧠 2. O Motor de Cálculo (Lógica Interna)

O aplicativo utiliza uma **Abordagem Conservadora**, aplicando automaticamente uma **Margem de Segurança Operacional de 0,5%** sobre o faturamento total para cobrir taxas de gateway e administração.

### As Fórmulas Core:
1.  **Custo Real do Cashback (CC):**
    `CC = (Gatilho * %Cashback) * %Taxa_de_Resgate`
    *Nota: A taxa de resgate (Breakage) ajusta o custo com base na probabilidade real de uso do crédito.*

2.  **Lucro na Campanha (Margem Residual):**
    `MC = (Gatilho * %Margem_Bruta) - CC - (Gatilho * 0.005)`

3.  **Esforço de Upsell (Ponto de Equilíbrio):**
    `Aumento_Necessário = CC / %Margem_Bruta`
    *Indica quanto o ticket precisa subir para que o cashback se pague sozinho.*

4.  **CAC Integrado:**
    `CAC_Total = (Investimento_Mídia / Qtd_Clientes_Estimada) + CC`

---

## 🛠️ 3. Dicionário de Usabilidade (Human-Centric)

Para democratizar o uso entre diferentes níveis de gerência, o app substitui jargões técnicos por conceitos intuitivos através de tooltips:

*   **Ticket Médio Atual:** "O ponto de partida. Quanto seu cliente gasta hoje sem o benefício."
*   **Gatilho de Ativação:** "A meta. O valor mínimo que o cliente precisa gastar para ganhar o prêmio."
*   **Taxa de Uso (Resgate):** "A margem de esquecimento. Nem todos os clientes voltam para usar o crédito, o que economiza fôlego para a loja."
*   **Sobras no Bolso (Margem Residual):** "O que realmente fica com a loja após pagar o fornecedor e o cashback."

---

## 📊 4. Interface e Experiência do Usuário (UX/UI)

O design segue a estética **Glassmorphism** (Cartões Translúcidos), focada em clareza e hierarquia de informação:

### Navegação Estruturada
*   **Simulador (Home):** O painel interativo principal.
*   **Como Funciona:** Documentação educativa sobre os cálculos.
*   **Estratégia:** Direcionamentos sobre como aplicar as métricas no mundo real.

### Visualização de Dados
*   **Semáforo de Saúde:** Um indicador visual instantâneo.
    *   🔴 **Risco:** Gatilho menor que o Ticket Médio (Prejuízo).
    *   🟡 **Atenção:** Margem apertada, lucro por venda estável.
    *   🟢 **Sustentável:** Aumento de faturamento cobre o benefício e gera lucro incremental.
*   **Gráfico Comparativo:** Gráfico de barras dinâmico (Chart.js) que compara o lucro de uma venda comum "Hoje" contra o lucro da venda na "Campanha".

---

## 📈 5. Cenários de Simulação Prática

| Cenário | Ticket Médio | Gatilho | Cashback | Resultado | Insight |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Agressivo** | R$ 80 | R$ 120 | 10% | 🟡 Alerta | Aumentou venda, mas o cashback de 10% é pesado para a margem. |
| **Sustentável** | R$ 80 | R$ 130 | 5% | 🟢 Sustentável | O aumento de R$ 50 no ticket paga o cashback com folga. |
| **Erro Operacional**| R$ 100 | R$ 100 | 5% | 🔴 Risco | Você está dando dinheiro para quem já iria comprar esse valor. |

---

## 🚀 6. Roadmap Tecnológico
- [x] **Fase 1:** Implementação da lógica matemática e segurança operacional.
- [x] **Fase 2:** Interface responsiva com Tailwind CSS e Glassmorphism.
- [x] **Fase 3:** Tooltips explicativos e navegação estratégica.
- [ ] **Fase 4:** Exportação de relatório em PDF para apresentações de diretoria.
- [ ] **Fase 5:** Modo "Multi-Loja" para comparação de filiais.

---

**CashbackStrat 1.0** — *Transformando cashback de custo em investimento.*