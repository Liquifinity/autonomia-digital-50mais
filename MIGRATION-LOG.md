# Registro da separação do site

Atualizado em 2026-10-02.

## Estado observado

- O domínio público respondeu HTTP 200; o servidor informou Railway.
- O HTML vivo em `/` tem o mesmo Git blob SHA de `aerina/public/index.html`: `5eb95e4933af56fb1ce2c050faf3b08ecbcbc501`.
- O `/app.js` vivo tem o mesmo Git blob SHA de `aerina/public/app.js`: `4b932f9933c96d73b200e458e9c44ece07eb4b72`.
- A `main` deste repo tem vitrine documental e assets, sem `index.html` nem `app.js`. Hoje, Aerina guarda a fonte do site público.
- Aerina tem 53 assets públicos com cerca de 64 MB, incluindo dois vídeos. A página também compartilha a origem HTTP com APIs e áreas de membros.

## Decisão de corte

Não mover nem apagar a fonte atual antes de preparar o novo serviço. O site precisa continuar com as rotas/formulários atuais e acessar a API operacional Aerina. A transferência precisa de estratégia para os binários e teste de proxy/API no mesmo domínio.

## Próximas ações

1. Preparar serviço estático dono da vitrine neste repo; escolher hospedagem de vídeos/assets.
2. Encaminhar endpoints operacionais à Aerina por configuração de ambiente, sem versionar credenciais.
3. Testar página, assets, formulários, rotas e gravação em staging.
4. Migrar domínio com rollback pronto.
5. Remover do repo Aerina só os arquivos da vitrine depois do corte. Manter API, membros e dados operacionais em Aerina.

Nenhum código, dado operacional ou deploy mudou neste registro.
