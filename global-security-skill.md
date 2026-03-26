### 🧠 Antigravity Global Skill: Segurança, Padrão MVP e Agentic Capabilities

**Dono do Manual:** Vinicius (costemani-tech)
**OBJETIVO:** Este é o cérebro de instruções global para todos os projetos (Meu Plantão, Bolão, Dívidas, etc).

**1. REFERÊNCIA TÉCNICA E CAPACIDADES (AGENT SKILLS):**
* **Documentação Base:** https://developers.googleblog.com/closing-the-knowledge-gap-with-agent-skills/
* **Instrução:** Utilize o conceito de "Agent Skills" do Gemini para realizar chamadas de função (Function Calling). Você deve agir como um Agente Executor: automatize a criação de tabelas, configuração de RLS e validação de deploy sempre que possível.

**2. PADRÃO DE SEGURANÇA (BANCO DE DADOS):**
* **Auth:** Priorize sempre Login por E-mail (OTP/Magic Link) para eliminar a gestão de senhas.
* **Row Level Security (RLS):** Toda tabela deve ser blindada. A regra padrão é: `auth.uid() = user_id`. Impeça acessos cruzados entre usuários.
* **Integridade:** Antes de qualquer alteração no banco, valide se o script SQL segue o princípio do menor privilégio.

**3. PADRÃO DE DESENVOLVIMENTO (FRONT-END):**
* **Hospedagem:** Foco inicial em Vercel, mas mantenha a lógica agnóstica para possíveis migrações (ex: Trapiche Cloud).
* **PWA Instalável:** Todo app deve conter `manifest.json`, meta tags de mobile-web-app e ícones (192px/512px).
* **Offline-First:** Implemente cache local (localStorage/SWR) para garantir funcionamento em locais de baixa conectividade (áreas de sombra em hospitais).

**4. PADRÃO DE UX E USABILIDADE:**
* **Toque no Celular:** Botões e áreas clicáveis devem ter no mínimo 44px de altura/largura.
* **Flexibilidade:** Em listas de seleção (escalas, categorias, etc), inclua sempre a opção "Outro (Personalizado)".
* **Gestão de Dados:** Garanta que o usuário sempre tenha a opção de Deletar/Remover registros que ele mesmo criou (CRUD completo).
