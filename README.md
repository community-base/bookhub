# BookHub GitHub v2.1

Biblioteca de documentos em GitHub Pages, com interface escura e abas independentes **PDF** e **Word (.doc / .docx)**.

## Recursos

- Buscar repositórios públicos de um usuário ou organização GitHub.
- Navegar por pastas e subpastas e selecionar fontes.
- Identificar arquivos de extensão `.pdf`, `.doc` e `.docx` (sem diferenciação de maiúsculas/minúsculas).
- Sincronizar os documentos e retornar ao catálogo ao salvar as fontes.
- Exibir PDFs na aba **PDF**, com tentativa de miniatura da primeira página usando PDF.js.
- Exibir DOC e DOCX na aba **Word**, com ícone de documento. Não é feita conversão de Word em HTML ou geração automática de capa.
- Pesquisar e abrir arquivos em nova aba.
- Salvar fontes e índice de documentos no armazenamento local do navegador.

## Publicação

1. Copie `index.html` para a raiz do seu repositório GitHub público, com o nome todo em minúsculas.
2. Em **Settings → Pages**, configure `Deploy from a branch`, branch `main`, pasta `/ (root)`.
3. Abra a URL publicada pelo GitHub Pages e use **Adicionar fontes** para pesquisar contas e selecionar pastas.

## Observações e limites

- Apenas repositórios **públicos** são pesquisados; nenhum token é solicitado.
- A API GitHub pode limitar requisições, e repositórios grandes podem exceder o limite de árvores recursivas; nesse caso o aplicativo apresenta um erro e mantém o último catálogo salvo da fonte.
- Os arquivos `.doc` e `.docx` são identificados e linkados, mas podem ser **baixados pelo navegador** em vez de pré-visualizados; o GitHub não oferece um leitor Word embutido universal.
- Miniaturas PDF podem falhar por limites de rede, CORS ou por arquivos inválidos; será mostrada uma capa substituta.
- A sincronização acontece ao salvar fontes, manualmente e periodicamente enquanto a página estiver aberta.
- O catálogo e as fontes são locais ao navegador, não são automaticamente compartilhados com todos os visitantes.
- O nome de repositório deve ser público e os arquivos devem estar versionados na branch padrão.

## Alterações v2.1

- Correção da descoberta para incluir PDF, DOC e DOCX em todas as subpastas da árvore consultada.
- Duas abas com contadores de documentos e cartões específicos por formato.
- Mantido o fluxo de seleção e salvamento da versão v2.0.
