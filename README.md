# BookHub GitHub v2.5

Biblioteca digital estática (GitHub Pages) para arquivos **PDF**, **Word (.doc/.docx)** e **Markdown (.md)** de repositórios públicos.

## Recursos

- Busca de repositórios por conta GitHub e exploração de pastas e subpastas.
- Sincronização recursiva, abas por formato, pesquisa e capas da primeira página de PDFs quando acessíveis.
- Catálogo agrupado por repositório com um cabeçalho e linha azul; subpastas não criam novas divisões.
- Botão **Atualizar README** para gerar um índice de PDFs, Word e Markdown presentes nas fontes sincronizadas.
- Prévia editável do README, download para atualização manual ou publicação no GitHub após confirmação.
- Preserva o conteúdo do README **fora** do trecho entre os marcadores `<!-- BOOKHUB:INDEX:START -->` e `<!-- BOOKHUB:INDEX:END -->`.
- Verificação SHA do arquivo antes da atualização para evitar sobrescrever alterações simultâneas.

## Atualizar README

1. Sincronize os repositórios e abra **Atualizar README**.
2. Escolha o repositório e clique em **Gerar prévia**.
3. Confira o texto; o índice automático inclui as pastas, arquivos e links.
4. Clique em **Baixar README.md** para enviar manualmente ao GitHub **ou** informe um token pessoal temporário (fine-grained PAT) com a permissão `Contents: Read and write` restrita apenas ao repositório escolhido e confirme a atualização.

**Segurança:** não inclua tokens ou senhas no HTML do repositório. O token digitado não é armazenado em `localStorage`; é usado somente para a chamada à API GitHub e apagado após publicação/fechamento do painel. Evite usar tokens com permissões amplas, especialmente em computadores compartilhados. O acesso público e as políticas de CORS/permissões do navegador podem limitar a operação; nesse caso use o download manual.

A atualização **não** acontece sozinha ao adicionar um arquivo ao GitHub. Sincronize o catálogo e clique em **Atualizar README**; a publicação requer confirmação/autorização. Para atualizações automáticas mesmo com a aba fechada, configure um GitHub Actions workflow separado.

## Implantação

Coloque `index.html`, `README.md` e `.nojekyll` na raiz da branch `main` do repositório, e habilite **Settings → Pages → Deploy from a branch → main / (root)**. Em páginas de projeto, use o endereço `https://USUARIO.github.io/REPOSITORIO/`.

## Limitações

A consulta pública da API GitHub tem limites de requisições; a geração de capas PDF depende do acesso do navegador ao arquivo; arquivos DOC/DOCX/MD são links e podem abrir em nova aba ou baixar, dependendo do navegador. As fontes e o catálogo ficam salvos apenas no navegador usado. A versão é independente de Google Drive.
