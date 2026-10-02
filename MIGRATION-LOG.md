# Registro da separação do site

Atualizado em 2026-10-02.

## Estado observado

- Os domínios público apex e `www` responderam HTTP 200; servidor informou Railway.
- O HTML vivo em `/` tem o mesmo Git blob SHA de `aerina/public/index.html`: `5eb95e4933af56fb1ce2c050faf3b08ecbcbc501`.
- O `/app.js` vivo tem o mesmo Git blob SHA de `aerina/public/app.js`: `4b932f9933c96d73b200e458e9c44ece07eb4b72`.
- A `main` deste repo tem vitrine documental e assets, sem `index.html` nem `app.js`. Hoje, Aerina guarda a fonte do site público.
- Aerina tem 53 assets públicos com cerca de 64 MB, incluindo dois vídeos. A página também compartilha a origem HTTP com APIs e áreas de membros.
- O CNAME público aponta para `75f3suqr.up.railway.app`, mas a chamada direta a esse host em `/health` retornou 404 “Application not found”. Ainda não há hostname de upstream confirmado para o novo proxy.

## Decisão de corte

Não mover nem apagar a fonte atual antes de preparar o novo serviço. O site precisa continuar com as rotas/formulários atuais e acessar a API operacional Aerina. A transferência precisa de estratégia para os binários e teste de proxy/API no mesmo domínio.

## Próximas ações

1. Confirmar no painel Railway o domínio privado/público correto do serviço Aerina e seu healthcheck.
2. Preparar serviço estático dono da vitrine neste repo; escolher hospedagem de vídeos/assets.
3. Encaminhar endpoints operacionais à Aerina por configuração de ambiente, sem versionar credenciais.
4. Testar página, assets, formulários, rotas e gravação em staging.
5. Migrar domínio com rollback pronto.
6. Remover do repo Aerina só os arquivos da vitrine depois do corte. Manter API, membros e dados operacionais em Aerina.

Nenhum código, dado operacional ou deploy mudou neste registro.
