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
