# Pagode do Lukinha — V13 Admin

## O que entrou
- novo `/admin.html` responsivo;
- login;
- Dashboard;
- edição da Home;
- CRUD completo de Agenda (criar, editar e excluir);
- CRUD completo de Vídeos do YouTube;
- edição de “Por trás da resenha”;
- edição de contato, WhatsApp e Instagram;
- site público já lê as alterações do admin;
- integração preparada para Supabase Auth + Database;
- fallback local para testar antes de conectar o Supabase.

## Teste local
Abra `admin.html` no mesmo domínio/origem do site.
Login de demonstração: `admin@lukinha.local` / `lukinha`.

## Produção com Supabase
1. Crie/abra o projeto Supabase.
2. Rode `supabase-schema.sql` no SQL Editor.
3. Em Authentication, crie o usuário administrador.
4. Preencha `supabase-config.js` com Project URL e a chave pública `anon`.
5. Faça deploy. O admin passa automaticamente do modo local para Supabase.

Nunca coloque `service_role` no frontend.


## V15 — Ordem dos vídeos
No Admin > Vídeos, arraste os cards pelo ícone ☰. A ordem é persistida no campo `sort_order` do Supabase (ou no armazenamento local durante testes) e a página pública respeita essa sequência.

## V16
Correção definitiva do alinhamento da Agenda: data, cidade e botão + agora usam faixas flex independentes, impedindo sobreposição em desktop e mobile.

## V17 — revisão responsiva
- Breakpoints consolidados para desktop, tablet e mobile.
- Agenda mobile usa grid rígido DATA | CIDADE | + para impedir sobreposição.
- Galeria de vídeos permanece em 3 colunas no mobile, com cards compactos e apenas título.
- Hero, Resenha, Contato, footer e header receberam composição específica para telas pequenas.
- Correção de overflow horizontal e dimensionamento fluido de tipografia/imagens.

## V19 — Supabase conectado
- Frontend configurado com o Project URL do Supabase e a Publishable key.
- O URL deve ser a raiz do projeto (`https://...supabase.co`), sem `/rest/v1/`; a biblioteca Supabase adiciona as rotas necessárias.
- Execute `supabase-schema.sql` no SQL Editor do projeto antes de usar o Admin, caso as tabelas/policies ainda não existam.
- O login do Admin passa a usar Supabase Auth quando a configuração acima está presente.
- Nunca adicione `service_role` ou Secret key ao frontend.
