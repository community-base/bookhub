# BookHub GitHub v2.2

Biblioteca de documentos **PDF, DOC e DOCX** em repositórios públicos do GitHub.

## Novidades
- Abas separadas para PDF e Word, com contadores independentes.
- Varredura de **pastas e subpastas**, inclusive quando o Git Trees retorna resultado truncado ou inacessível: fallback para a API `contents`.
- Ao abrir um repositório no explorador, a **raiz é pré-selecionada** para incluir todas as subpastas. Marcar uma pasta específica substitui a seleção abrangente.
- Mostra o caminho da pasta de cada documento nos cartões.
- Mantém os registros anteriores de uma fonte quando a nova consulta falha.

## Publicação
Envie `index.html` à raiz de `community-base/bliblioteca` (branch `main`) e mantenha Pages em `main` / `(root)`.

## Uso
1. Clique em **Adicionar fontes**.
2. Informe a conta GitHub, pesquise e selecione um repositório.
3. A raiz já aparece marcada (inclui subpastas). Opcionalmente, escolha pastas específicas.
4. Clique em **Salvar e sincronizar**.
5. Volte ao catálogo e alterne entre **PDF** e **Word**.

**Atenção**: só são acessíveis repositórios públicos. A API pública do GitHub limita consultas sem autenticação, principalmente para repositórios com muitas pastas. A primeira página de PDFs pode não ser renderizada quando o servidor impede o carregamento cruzado; o catálogo ainda apresenta um cartão e permite abrir o documento. O navegador não renderiza DOCX nativamente.
