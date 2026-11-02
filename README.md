# BookHub GitHub v2.0

Biblioteca visual de arquivos PDF em **repositórios públicos do GitHub**. Aplicação em um único arquivo `index.html`, com interface dark, pronta para hospedagem no GitHub Pages.

## Como usar

1. Abra o BookHub e clique em **Adicionar fontes**.
2. Digite o nome de usuário ou organização do GitHub (por exemplo, `community-base`) e clique em **Buscar**.
3. Selecione um repositório na lista; a árvore de pastas e subpastas será exibida.
4. Marque a **raiz** para catalogar todos os PDFs desse repositório ou marque apenas as pastas desejadas. Repita para outros repositórios.
5. Clique em **Salvar e sincronizar**. O painel de fontes fecha e o catálogo passa a mostrar os documentos encontrados.
6. Use **Sincronizar** para atualizar o catálogo manualmente. O aplicativo também sincroniza ao iniciar, caso existam fontes salvas.

## Capas dos PDFs

O BookHub tenta renderizar a primeira página usando PDF.js (carregado de `cdnjs.cloudflare.com`). Caso o arquivo não possa ser lido pelo navegador devido a CORS, tamanho ou formato, mostra uma capa substituta. O botão **Abrir PDF** continua disponível.

## Dados e privacidade

- A lista de fontes e o catálogo ficam no `localStorage` **somente deste navegador**; não são compartilhados automaticamente entre visitantes ou dispositivos.
- Não há login, token ou acesso a repositórios privados nesta versão.
- O aplicativo lê apenas repositórios públicos. Os documentos são abertos a partir de URLs públicas do GitHub.
- O GitHub limita requisições anônimas. A descoberta inicial pode falhar com erro `403` quando o limite for excedido.
- Alguns repositórios grandes podem ter árvores truncadas; o aplicativo avisa quando não é possível garantir a listagem completa.
- **Sincronização ocorre com a página aberta** ou quando ela é aberta novamente. Não há serviço de segundo plano.
- O aplicativo depende de conexão à internet para usar a API GitHub e PDF.js.

## Publicação no GitHub Pages

Envie `index.html`, `README.md` e `.nojekyll` à raiz da branch `main` de seu repositório. Acesse **Settings → Pages → Deploy from a branch → main → / (root)**. Para o repositório `community-base/bliblioteca`, o endereço esperado é `https://community-base.github.io/bliblioteca/`.

## Limitações e próximas etapas

A importação automática é exclusiva de repositórios **públicos**. O futuro **BookHub Drive** será outro aplicativo, com autenticação OAuth do Google, permissões das pastas e API Google Drive. Para catálogos realmente compartilhados, deve ser criada uma publicação de manifesto de livros ou um backend autorizado.

## Histórico

- v2.0: separação do Google Drive; busca de repositórios; seleção por pasta; sincronização com preservação dos dados quando uma fonte falha; catálogo de capas; leitura de PDFs em nova aba.
