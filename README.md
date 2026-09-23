# Pagode do Lukinha — V12 Admin

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
A V13 está conectada ao projeto Supabase `pagodedolukinha`. O acesso ao Admin usa Supabase Auth; crie o usuário em Authentication → Users.

## Produção com Supabase
1. Crie/abra o projeto Supabase.
2. Rode `supabase-schema.sql` no SQL Editor.
3. Em Authentication, crie o usuário administrador.
4. `supabase-config.js` já contém a Project URL e a publishable key pública do projeto `pagodedolukinha`.
5. Faça deploy. O admin passa automaticamente do modo local para Supabase.

Nunca coloque `service_role` no frontend.
