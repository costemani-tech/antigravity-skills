Antigravity Global Skill: Segurança e Padrão MVP
OBJETIVO: Sempre que o Vinicius iniciar um projeto (Plantão, Bolão, etc), estas regras devem ser aplicadas automaticamente.

1. PADRÃO DE BANCO DE DADOS (SUPABASE):

Auth: Usar sempre Login por E-mail (OTP) para evitar gestão de senhas.

Segurança (RLS): Toda tabela deve ter RLS habilitado. A regra padrão é: auth.uid() = user_id.

2. PADRÃO DE FRONT-END (VERCEL/NEXT.JS):

PWA: Todo app deve ter manifest.json e ícones configurados para ser instalável.

Offline-First: Salvar dados críticos no localStorage para funcionar sem internet (áreas de sombra de hospital).

3. DESIGN UX:

Focar em botões grandes (mínimo 44px) para uso fácil no celular durante o trabalho.

Clique no botão verde "Commit changes..." no canto superior direito e depois em "Commit changes" novamente.
