# Backlog do Projeto: Sistema de Gestão de Pedidos para Empresa Calçadista

**Versão:** MVP 1.0.0  
**Tecnologias:** Flask (Backend), HTML/CSS/JavaScript (Frontend), MySQL (Banco de Dados) Não definido ainda
**Aluno:** Guilherme Henrique Leão Pereira  
**Curso:** Tecnologia em Gestão da Produção Industrial - FATEC Franca

---

## Contexto do Cliente

**Segmento:** Fabricação de solados para calçados  
**Localização:** Franca/SP  
**Tipo:** Empresa familiar de pequeno porte  
**Clientes-alvo:** Fabricantes de calçados de pequeno, médio e grande porte que terceirizam produção de solados

**Missão:** Fabricar e fornecer solados conforme as necessidades dos clientes, consolidando-se no mercado com uma base de clientes confiáveis.

**Visão:** Crescer no ramo sem perder qualidade dos produtos e serviços, tornando-se uma fábrica de médio ou grande porte na cidade.

**Valores:** 
- Qualidade na fabricação dos produtos
- Pontualidade nas entregas
- Atendimento às necessidades dos clientes

**Desafio atual:** Oscilação de preços de matérias-primas e alta competitividade no mercado de Franca. Gestão manual (cadernos e mensagens) gera riscos de perda de informações, falhas em prazos e dificuldade no controle financeiro.

---

## Definição do MVP

O MVP (Produto Mínimo Viável) deste projeto consiste na versão mais enxuta do sistema que permite ao proprietário gerenciar pedidos de forma digital, **alinhando-se aos valores da empresa de pontualidade e qualidade no atendimento**. O sistema substituirá o método manual atual, reduzindo erros e permitindo que a empresa **cresça de forma organizada e escalável**, conforme sua visão estratégica.

O foco é entregar valor rapidamente, validar a solução com o usuário real e demonstrar como a tecnologia pode **consolidar a base de clientes** através de melhor gestão e comunicação.

---

## 1. Configuração e Infraestrutura Essencial

**Descrição:** Preparação do ambiente técnico e modelagem do banco de dados.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **Configuração Inicial** | Configurar ambiente de desenvolvimento (Python, Flask, MySQL) | **M** |
| | Configurar controle de versão Git e repositório GitHub | **M** |
| | Criar estrutura de pastas do projeto (MVC) | **M** |
| **Modelagem do Banco** | Definir modelo conceitual (DER) com entidades: Usuario, Pedido, Item_Pedido, Produto, Material, Estoque | **M** |
| | Criar modelo lógico e físico do banco de dados | **M** |
| | Criar scripts SQL para criação das tabelas no MySQL | **M** |
| | Implementar relacionamentos e chaves estrangeiras | **M** |

---

## 2. Funcionalidades Essenciais - Módulo de Autenticação

**Descrição:** Permitir login seguro de proprietário e clientes no sistema.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **UC 001: Fazer Login** | Como proprietário/cliente, eu quero fazer login com email e senha para acessar o sistema de forma segura (RF014) | **M** |
| | Implementar tela de login com validação de credenciais | **M** |
| | Implementar recuperação de senha | **S** |
| | Como sistema, devo criptografar as senhas armazenadas no banco | **M** |

---

## 3. Funcionalidades Essenciais - Gestão de Pedidos (Cliente)

**Descrição:** Permitir que clientes criem e acompanhem seus pedidos.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **UC 007: Preencher Dados do Pedido** | Como cliente, eu quero informar tipo de sola, tamanhos, quantidade de pares, materiais e foto de referência para especificar meu pedido (RF009) | **M** |
| | Como cliente, eu quero informar o preço por par e data de entrega desejada (RF009) | **M** |
| | Como cliente, eu quero adicionar observações e avisos sobre o pedido (RF009) | **M** |
| **UC 008: Fazer o Pedido** | Como cliente, eu quero revisar os dados e confirmar o pedido para enviá-lo ao proprietário | **M** |
| **UC 002: Acessar Área de Pedidos** | Como cliente, eu quero visualizar meus pedidos (novos, em produção, concluídos) para acompanhar o status (RF002) | **M** |
| | Como cliente, eu quero ver a data estimada de entrega de cada pedido | **S** |

---

## 4. Funcionalidades Essenciais - Gestão de Pedidos (Proprietário)

**Descrição:** Permitir que o proprietário gerencie os pedidos recebidos.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **UC 002: Acessar Área de Pedidos** | Como proprietário, eu quero visualizar pedidos novos, pendentes e atrasados para gerenciar a produção (RF002) | **M** |
| **UC 003: Confirmar Pedidos** | Como proprietário, eu quero analisar as informações do pedido para decidir se aceito ou recuso | **M** |
| **UC 004: Aceitar Pedido** | Como proprietário, eu quero aceitar um pedido para movê-lo para status "Em Produção" | **M** |
| **UC 005: Recusar Pedido** | Como proprietário, eu quero recusar um pedido informando o motivo (opcional) para notificar o cliente (RN001) | **M** |
| **UC 006: Finalizar Pedido** | Como proprietário, eu quero marcar um pedido como concluído para notificar o cliente que está pronto | **M** |
| **UC 011: Calcular Tempo do Pedido** | Como sistema, devo calcular automaticamente o tempo estimado de entrega baseado na complexidade e na fila de produção | **S** |

---

## 5. Funcionalidades Essenciais - Cálculos Financeiros

**Descrição:** Calcular automaticamente custos, preços e lucros dos pedidos.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **RF001: Cálculo de Preço Total** | Como sistema, devo calcular e exibir o preço total do pedido (quantidade × preço por par) | **M** |
| **RF002: Cálculo de Custo** | Como sistema, devo calcular o custo total de matérias-primas utilizadas no pedido | **M** |
| **RF003: Cálculo de Lucro** | Como sistema, devo calcular o lucro (valor total - custo de materiais) e exibir para o proprietário | **M** |

---

## 6. Funcionalidades Essenciais - Comunicação

**Descrição:** Sistema de mensagens entre cliente e proprietário.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **RF004/RF005: Sistema de Chat** | Como cliente/proprietário, eu quero enviar mensagens de texto para negociar detalhes do pedido (RN001) | **M** |
| **RF006: Envio de Anexos** | Como cliente/proprietário, eu quero enviar fotos e vídeos através do chat para esclarecer detalhes | **S** |
| | Como sistema, devo exibir histórico completo das conversas | **S** |

---

## 7. Funcionalidades Essenciais - Notificações

**Descrição:** Alertar usuários sobre eventos importantes.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **UC 010: Notificar Proprietário** | Como sistema, devo enviar notificação ao proprietário quando um novo pedido for criado (RF010) | **M** |
| **UC 013: Notificar Cliente** | Como sistema, devo notificar o cliente quando seu pedido for aceito, recusado ou concluído (RF010) | **M** |
| **RF010: Alertas de Entrega** | Como sistema, devo enviar notificações automáticas quando a data de entrega estiver próxima (RN002) | **M** |

---

## 8. Funcionalidades de Suporte - Gestão de Materiais e Estoque

**Descrição:** Controlar materiais disponíveis para produção.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **Cadastro de Materiais** | Como proprietário, eu quero cadastrar materiais (nome, tipo, preço unitário) para usar nos pedidos | **M** |
| **Controle de Estoque** | Como proprietário, eu quero registrar a quantidade disponível de cada material para evitar aceitar pedidos sem insumos | **S** |
| | Como sistema, devo alertar quando um material atingir a quantidade mínima | **S** |
| | Como proprietário, eu quero registrar a localização física do material no depósito | **C** |

---

## 9. Funcionalidades de Suporte - Gestão de Produtos

**Descrição:** Cadastrar tipos de solados produzidos.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **Cadastro de Produtos** | Como proprietário, eu quero cadastrar tipos de produtos (solados) com nome, descrição e tempo base de produção | **M** |
| **RF007: Lista de Clientes** | Como proprietário, eu quero visualizar todos os clientes cadastrados com histórico de pedidos | **S** |

---

## 10. Funcionalidades de Suporte - Ferramentas Internas

**Descrição:** Recursos para organização interna do proprietário.

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **RF013: Bloco de Notas** | Como proprietário, eu quero ter um bloco de notas interno para fazer anotações (RN006) | **S** |
| **RF011: Produção Diária** | Como proprietário, eu quero visualizar a quantidade de pares a serem produzidos por dia até a entrega | **S** |
| **RF008: Número de Contato** | Como cliente, eu quero visualizar o número de contato da empresa para emergências | **M** |

---

## 11. Requisitos Não Funcionais Essenciais

| Feature | Tarefa / User Story | Prioridade |
|---------|-------------------|------------|
| **RNF001: Leveza e Desempenho** | O aplicativo deve ser leve e otimizado para rodar sem dificuldades em dispositivos simples | **M** |
| **RNF006: Usabilidade** | O aplicativo deve ser intuitivo para usuários com pouca experiência tecnológica (seu pai e clientes) | **M** |
| **RNF007: Disponibilidade** | O sistema deve funcionar 24 horas por dia para atender imprevistos | **M** |
| **RNF002: Acessibilidade Visual** | Botões grandes e textos maiores que o padrão para facilitar a leitura | **S** |
| **RNF003: Design de Interface** | Seguir esquema de cores com verde como cor principal e tons neutros | **S** |
| **RNF004: Escalabilidade** | O banco de dados deve ser expansível para suportar crescimento futuro da empresa | **S** |

---

## 12. Funcionalidades para Versões Futuras (Won't Have / Could Have)

**Descrição:** Funcionalidades que agregarão valor mas não são críticas para o MVP. Estas funcionalidades apoiarão a **visão de crescimento** da empresa em versões futuras.

| Feature | Tarefa / User Story | Prioridade | Alinhamento Estratégico |
|---------|-------------------|------------|------------------------|
| **Relatórios e Dashboards** | Como proprietário, eu quero visualizar relatórios de vendas, produtos mais vendidos e lucro mensal | **C** | Apoiar decisões estratégicas de crescimento |
| | Como proprietário, eu quero gráficos de desempenho e produtividade | **C** | Medir qualidade e eficiência |
| | Como proprietário, eu quero relatório de pontualidade de entregas | **C** | Validar cumprimento do valor "pontualidade" |
| **Gestão de Clientes Avançada** | Como proprietário, eu quero categorizar clientes por porte (pequeno/médio/grande) | **C** | Segmentar base de clientes |
| | Como proprietário, eu quero histórico completo de relacionamento com cada cliente | **C** | Consolidar base de clientes confiáveis (missão) |
| **Controle de Qualidade** | Como proprietário, eu quero registrar inspeções de qualidade nos produtos | **C** | Manter padrão de qualidade (valor) |
| **Gestão Financeira Avançada** | Controle de fluxo de caixa, contas a pagar/receber | **W** | Útil para crescimento futuro |
| | Controle de oscilação de preços de matérias-primas | **C** | Lidar com desafio do mercado |
| **E-commerce** | Módulo de vendas online para novos clientes | **W** | Expansão de mercado |
| **Integração com Fornecedores** | Sistema automático de pedidos para fornecedores externos | **W** | Otimizar cadeia de suprimentos |
| **RH** | Gestão de funcionários e folha de pagamento | **W** | Necessário ao se tornar médio/grande porte |
| **RF012: Foto de Perfil** | Como cliente, eu quero configurar uma foto de perfil personalizada | **C** | Melhorar experiência do usuário |
| **App Mobile Nativo** | Versão nativa para Android/iOS (inicialmente será web responsivo) | **C** | Facilitar acesso mobile |

---

## Cronograma Estimado do MVP

| Fase | Duração | Entregas |
|------|---------|----------|
| **Sprint 1** | 2 semanas | Configuração + Modelagem do Banco + Autenticação |
| **Sprint 2** | 3 semanas | Gestão de Pedidos (Cliente) + Cálculos Financeiros |
| **Sprint 3** | 3 semanas | Gestão de Pedidos (Proprietário) + Notificações |
| **Sprint 4** | 2 semanas | Sistema de Chat + Ajustes de Usabilidade |
| **Sprint 5** | 2 semanas | Testes + Validação com usuário + Correções |

**Total:** 12 semanas (3 meses)

---

## Critérios de Aceitação do MVP

O MVP será considerado bem-sucedido se atender aos valores da empresa:

**Qualidade:**
1. ✅ Zero perda de dados de pedidos
2. ✅ Cálculos financeiros automáticos corretos (custos e lucros)
3. ✅ Interface utilizável por pessoas com baixa experiência tecnológica
4. ✅ Tempo de resposta inferior a 2 segundos para operações básicas

**Pontualidade:**
5. ✅ Sistema de notificações operacional para alertas de entrega
6. ✅ Visualização clara de prazos e datas de entrega
7. ✅ Controle de status dos pedidos em tempo real

**Atendimento ao Cliente:**
8. ✅ O proprietário conseguir gerenciar 100% dos pedidos digitalmente
9. ✅ Clientes conseguirem fazer pedidos sem assistência
10. ✅ Sistema de chat funcional para comunicação empresa-cliente

**Crescimento:**
11. ✅ Banco de dados escalável para suportar aumento de clientes
12. ✅ Histórico completo de pedidos e clientes para análise futura

---

## Metodologia de Validação

- **Testes com usuário real:** Seu pai testará o sistema em cenários reais de trabalho
- **Feedback contínuo:** Reuniões semanais para ajustes
- **Iterações rápidas:** Correções imediatas de problemas críticos
- **Métricas de sucesso:** Tempo economizado, redução de erros, satisfação do usuário

---

**Observação:** Este backlog segue a técnica MoSCoW para garantir que o MVP contenha apenas o essencial para validar a solução, permitindo lançamento rápido e coleta de feedback real do usuário final.

---

## Impacto Esperado do MVP nos Objetivos Estratégicos

**Consolidação no mercado (Missão):**
- Sistema profissional transmite confiança aos clientes
- Histórico completo facilita relacionamento de longo prazo
- Comunicação organizada através do chat

**Crescimento sustentável (Visão):**
- Base tecnológica escalável suporta aumento de demanda
- Dados organizados permitem análises estratégicas futuras
- Redução de custos operacionais libera recursos para investimento

**Qualidade e pontualidade (Valores):**
- Notificações automáticas evitam atrasos
- Cálculos precisos melhoram planejamento financeiro
- Rastreabilidade completa dos pedidos garante qualidade no atendimento

**Vantagem competitiva:**
Em um mercado competitivo como Franca, ter um sistema digital diferencia a empresa de concorrentes que ainda operam manualmente, permitindo atender melhor tanto pequenos quanto grandes clientes.