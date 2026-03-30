### 🧠 costemani-tech: Global Agentic Framework (v2.0)

**Dono:** Vinicius (costemani-tech)
**OBJETIVO:** Cérebro de instruções global para todos os projetos (Meu Plantão, Bolão, Dívidas). Atuar como Agente Executor Autônomo utilizando padrões oficiais google-gemini.

---

### 1. CAPACIDADES AGÊNTICAS (AGENT SKILLS)
* **Documentação Base:** https://developers.googleblog.com/closing-the-knowledge-gap-with-agent-skills/
* **Function Calling:** Estruture a lógica como "Tools". O Agente deve validar o estado atual do banco antes de propor alterações.
* **Agente Executor:** Automatize criação de tabelas, configuração de RLS e validação de deploy sempre que possível.

### 2. PADRÃO DE SEGURANÇA (BANCO DE DADOS)
* **Auth:** Priorize sempre Login por E-mail (OTP/Magic Link) para eliminar a gestão de senhas.
* **Row Level Security (RLS):** Toda tabela deve ser blindada. Regra obrigatória: `(SELECT auth.uid()) = user_id`.
* **Menor Privilégio:** Chaves 'service_role' são estritamente Server-Side. Nunca expor no Front-end.

### 3. PROCESSAMENTO MULTIMODAL (GENAI PROCESSORS)
* **Extração de Dados:** Utilize a lógica de 'google-gemini/genai-processors' para converter fotos de escalas, comprovantes ou PDFs em JSON estruturado para o banco de dados.
* **Validação de Visão:** Ao processar imagens, confirme campos críticos com o usuário antes de salvar.

### 4. LÓGICA DE NEGÓCIO E RESILIÊNCIA (COOKBOOK STANDARDS)
* **Tratamento de Conflitos:** Siga o padrão 'google-gemini/cookbook'. Nunca bloqueie o usuário. Para sobreposições, ofereça alertas (ex: 'Plantão Pago' ou 'Troca').
* **Offline-First:** Implemente cache local (localStorage/SWR). Se o sinal falhar, enfileire a ação e sincronize no reestabelecimento.

### 5. PADRÕES DE UX E USABILIDADE (MOBILE-FIRST)
* **Toque no Celular:** Botões e áreas clicáveis devem ter no mínimo 44px de altura/largura.

### 🛡️ 6. PROTOCOLO DE AUDITORIA E BLINDAGEM (APPSEC)
* **Zero-Exposure:** Proibido expor API Keys, Secrets ou arquivos `.env` no frontend ou commits. Use variáveis de ambiente na Vercel/Supabase.
* **Sanitização Universal:** Todo input (campos, URLs, queryParams) deve ser tratado como "não confiável". Use queries parametrizadas (ORMs) para impedir SQL Injection e escape de caracteres para evitar XSS.
* **Validação Server-Side:** Nunca confie apenas na trava da interface (frontend). Toda ação sensível (Delete/Update/Pagamento) deve validar permissão e ID do usuário no servidor antes de executar.
* **Rate Limiting & Integridade:** Implemente proteção contra força bruta (limite de requests) e garanta idempotência em ações financeiras (evitar cobrança duplicada por clique duplo).
* **Hardening de Erros:** Erros enviados ao frontend devem ser genéricos (ex: "Algo deu errado"). Nunca exponha stack traces, nomes de tabelas ou detalhes internos do servidor.
* **Leak Check:** Verifique se o `.gitignore` contém `.env`, `node_modules` e pastas de build antes de qualquer push público.
* **Flexibilidade:** Inclua sempre a opção "Outro (Personalizado)" em listas de seleção.
* **Gestão de Dados:** Garanta CRUD completo (Criar, Ler, Atualizar e Deletar) para o dono do dado.
