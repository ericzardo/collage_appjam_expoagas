# 📋 Briefing de Projeto: CashbackStrat 1.0
> **Conceito:** Simulador de Sustentabilidade de Campanhas de Cashback.
> **Público-alvo:** Gestores de Marketing e Analistas de Trade Marketing de Supermercados.
> **Stack Sugerida:** HTML5, Tailwind CSS (estilo startup), JavaScript Vanilla e Chart.js.

---

## 1. Posicionamento e Proposta de Valor
No cenário atual (Revista AGAS, pág. 24), o cashback é uma ferramenta poderosa de fidelização, mas perigosa para a margem bruta. O **CashbackStrat** posiciona-se como a "calculadora de bolso do CMO", permitindo simular se uma promoção de "dinheiro de volta" é um investimento em crescimento ou uma erosão de lucro.

**Diferencial:** Diferente de planilhas complexas, ele entrega uma interface dinâmica de startup que separa o "Custo de Marketing" (CAC) do "Custo de Mercadoria".

---

## 2. Pilares de Funcionamento (Lógica Interna)

### A. Abordagem Conservadora
O app não ignora os custos ocultos. Ele aplica automaticamente uma **Margem de Segurança Operacional de 0,5%** sobre o faturamento da campanha para cobrir taxas de transação e custos de software, garantindo que o resultado simulado seja pé no chão.

### B. Módulo de CAC (Custo de Aquisição de Cliente)
O cashback é tratado como uma ferramenta de retenção. O app calculará o "CAC de Retorno": quanto custou em cashback para garantir que o cliente voltasse à loja uma segunda vez, comparando esse valor com o custo de um anúncio em redes sociais.

---

## 3. Estrutura de Dados (Inputs e Outputs)

### Entrada de Dados (O que o usuário preenche)
1.  **Ticket Médio Atual (R$):** O gasto médio do cliente hoje.
2.  **Margem Bruta Média (%):** A margem que a loja opera (ex: 25%).
3.  **Investimento em Mídia (R$):** Quanto será gasto em anúncios para divulgar a campanha.
4.  **Porcentagem de Cashback (%):** O valor prometido ao cliente.
5.  **Gatilho de Ativação (R$):** Valor mínimo de compra para ganhar o benefício.
6.  **Taxa de Resgate Estimada (%):** Porcentagem de clientes que de fato usarão o crédito (Breakage).

### Saída de Dados (O que o app responde)
1.  **Margem Residual Pós-Campanha:** O lucro que sobra após o cashback e custos operacionais.
2.  **Ponto de Equilíbrio (Break-even):** O quanto o Ticket Médio precisa subir para a margem não cair.
3.  **CAC Real da Campanha:** O custo total (Mídia + Cashback usado) dividido pelo número de clientes.
4.  **Índice de Sustentabilidade:** Um medidor visual (Semáforo de Startup).

---

## 4. Arquitetura da Interface (UX/UI Startup Style)

O design deve seguir a estética *Glassmorphism* (cartões translúcidos) com bordas arredondadas e cores vibrantes.

*   **Header:** Logo "CashbackStrat" + Badge "Modo Conservador Ativado".
*   **Sidebar Esquerda (Control Panel):** Sliders dinâmicos para ajustar % de Cashback e Gatilho. O resultado na tela muda instantaneamente ao arrastar.
*   **Main Dashboard (O Centro):**
    *   **Card de Semáforo:** Um círculo grande que muda de cor (Verde, Esmeralda, Laranja, Carmim).
    *   **Gráfico de Barras Duplo:** Comparando "Margem Sem Cashback" vs "Margem Com Cashback".
    *   **Widget de Insight:** Texto dinâmico como: *"Atenção: Para esta campanha ser saudável, seu ticket deve subir R$ 15,00. Sugerimos subir o gatilho para R$ X".*
*   **Footer:** Comparativo de CAC: *"Cada cliente fiel está custando R$ 4,50. Um novo cliente via Facebook custaria R$ 12,00. Economia de 62%."*

---

## 5. Algoritmo de Cálculo (Documentação para Dev)

Para a Prova de Conceito, utilizaremos as seguintes fórmulas:

1.  **Custo do Cashback (CC):**
    `CC = (Gatilho * %Cashback) * %Taxa_de_Resgate`
2.  **Margem de Contribuição Final (MCF):**
    `MCF = (Gatilho * Margem_Bruta) - CC - (Gatilho * 0.005)`
3.  **Aumento de Ticket Necessário:**
    `Aumento = CC / Margem_Bruta`
4.  **Cálculo de CAC Integrado:**
    `CAC_Total = (Investimento_Mídia / Qtd_Clientes) + CC`

---

## 6. Fluxo de Uso (User Stories)

1.  **Configuração:** O gestor abre o app e insere que seu supermercado tem um ticket médio de R$ 80,00 e margem de 20%.
2.  **Simulação:** Ele desliza o cashback para 10%. O app imediatamente fica **Vermelho**, indicando que ele perderá metade do lucro.
3.  **Ajuste:** O gestor aumenta o "Gatilho de Ativação" para R$ 120,00 (forçando o Upsell).
4.  **Validação:** O app fica **Verde**. O insight diz: *"Ao subir o ticket para R$ 120, o lucro em Reais por cliente aumenta 12%, mesmo pagando o cashback"*.
5.  **Decisão:** O gestor exporta o resumo para apresentar à diretoria.

---

## 7. Roadmap de Entrega (PoC)
*   [ ] **Fase 1:** Codificação da lógica matemática em JS.
*   [ ] **Fase 2:** Montagem do layout responsivo com Tailwind.
*   [ ] **Fase 3:** Implementação dos gráficos interativos (Chart.js).
*   [ ] **Fase 4:** Teste de estresse com margens baixas (setor de hortifruti).