1. CAPACIDADES AGÊNTICAS E MULTIMODAIS

Agent Skills: Utilize 'Function Calling' para validar o estado do banco (Supabase) antes de qualquer alteração. Atue como Agente Executor (Automação de tabelas e RLS).
GenAI Processors: Capacidade de converter fotos de escalas físicas ou PDFs em JSON estruturado para o banco de dados (Exclusivo Plano Pro).

2. SEGURANÇA E PRIVACIDADE (APPSEC - Score 91)
Isolamento RLS: Regra obrigatória em TODA tabela: (SELECT auth.uid()) = user_id.
Auth: Priorize Login por E-mail (OTP/Magic Link) para eliminar gestão de senhas.
Service Role: Chaves administrativas (service_role) são estritamente Server-Side. Nunca expor no Client/Frontend.

3. LÓGICA DE NEGÓCIO: REALIDADE DE ESCALAS
Gestão de Duplicidade: Nunca bloqueie sobreposições. Ao detectar choque de horário, exiba o Alerta Amarelo de "Confirmar Duplicidade".
Status de Conflito: Registre status_conflito: true para sinalização visual passiva no calendário.
Preservação de Histórico: Ofereça a opção "Encerrar Escala na Data X", deletando apenas plantões futuros (>= data) e mantendo o histórico trabalhado para controle financeiro.

4. UX ACESSÍVEL E CALENDÁRIO (VISUAL)
* **Pintura Total:** Fundo preenchido com a cor do hospital.
* **Lógica Noturna (Meio a Meio Vertical):** Plantões que cruzam a meia-noite usam divisão vertical (`to right`).
    * Início do Plantão (ex: 19h): Lado esquerdo transparente, lado direito pintado.
    * Término do Plantão (ex: 07h): Lado esquerdo pintado, lado direito transparente.
* **Múltiplos Plantões:** Se houver um diurno e um noturno, o lado esquerdo mostra a cor do dia e o direito a cor do início da noite.
* **Conflitos:** Se houver sobreposição total no mesmo horário, manter a cor e destacar com **Borda Âmbar 2px**.
5. REGRAS DE MONETIZAÇÃO (FREE VS PRO)
Limites Free: * Máximo de 2 Locais de Trabalho.
Máximo de 4 Plantões Extras por mês.
Alarmes: Escolha de horário livre (disponível no Free).
Paywall Pro (Acesso Restrito):
Edição de plantões já cadastrados.
Controle Financeiro completo (Saldo e lançamentos).
Compartilhamento de Agenda (Token familiar/leitura).
Exportação de Relatório: Apenas via PDF (Remover opção Excel).

6. PROTOCOLO DE AUDITORIA E BLINDAGEM (PENTEST)

Sanitização Universal: Trate todo input como "não confiável". Use queries parametrizadas e escape de caracteres (XSS).
Hardening de Erros: Proibido repassar erros crus do banco (Postgres/Supabase) para o cliente. Use mensagens amigáveis e códigos (error + code). Logs técnicos ficam apenas no servidor (console.error).
Leak Check: Impedir exposição de arquivos .env ou secrets no GitHub através de .gitignore rigoroso.
Validação Server-Side: Toda ação sensível (Delete/Pagamento) deve validar permissão e ID do usuário no servidor antes de executar.
* **Rate Limiting & Integridade:** Implemente proteção contra força bruta (limite de requests) e garanta idempotência em ações financeiras (evitar cobrança duplicada por clique duplo).
* **Hardening de Erros:** Erros enviados ao frontend devem ser genéricos (ex: "Algo deu errado"). Nunca exponha stack traces, nomes de tabelas ou detalhes internos do servidor.
* **Leak Check:** Verifique se o `.gitignore` contém `.env`, `node_modules` e pastas de build antes de qualquer push público.
* "Ocultação de Stack Trace: É proibido repassar objetos de erro crus (error, message do DB) para o cliente. Use mapeamento de mensagens amigáveis para cada tipo de falha."
* **Flexibilidade:** Inclua sempre a opção "Outro (Personalizado)" em listas de seleção.
* **Gestão de Dados:** Garanta CRUD completo (Criar, Ler, Atualizar e Deletar) para o dono do dado.
