# IgesDF Core

**Contribuidores:** [marcoscti](https://github.com/marcoscti)
**Tags:** shortcodes, custom post types, CPT, open graph, og tags, cache, vlibras, acessibilidade
**Requer no mínimo:** 4.9
**Testado até:** 6.4
**Versão estável:** 1.0.0
**Licença:** GPLv2 ou posterior
**URI da Licença:** https://www.gnu.org/licenses/gpl-2.0.html

Um plugin personalizado para armazenar funcionalidades centrais do site IgesDF, incluindo tipos de post personalizados, shortcodes, otimizações de performance e recursos de acessibilidade.

## Descrição

O `IgesDF Core` é um plugin privado desenvolvido para o Instituto de Gestão em Saúde do Distrito Federal (IGESDF). Ele centraliza funcionalidades essenciais que antes faziam parte de um tema filho. Essa abordagem torna o tema independente da lógica de negócio e facilita a manutenção.

O plugin implementa várias funcionalidades-chave:

*   **Tipos de Post Personalizados (CPTs):** Cria vários CPTs para gerenciar conteúdos específicos como notícias, processos seletivos, atos oficiais e mais.
*   **Shortcodes Dinâmicos:** Fornece um conjunto de shortcodes poderosos para exibir conteúdo complexo e filtrável no front-end, como linhas do tempo e listas de documentos.
*   **Melhorias de Performance:** Inclui um sistema de cache simples mas eficaz baseado em arquivos e remove o jQuery Migrate para acelerar o site.
*   **SEO & Mídias Sociais:** Gera e insere automaticamente tags Open Graph (OG) dinâmicas e imagens para um melhor compartilhamento em redes sociais.
*   **Acessibilidade:** Integra o widget do VLibras, oferecendo tradução para Língua Brasileira de Sinais para os usuários.
*   **Customização do Admin:** Personaliza a tela de login do WordPress com o logo do IGESDF.

## Funcionalidades

*   **Logo de Login Personalizado:** Substitui o logo padrão do WordPress na tela `wp-login.php`.
*   **Tags Open Graph (OG) Dinâmicas:**
    *   Gera automaticamente uma imagem OG de 600x315px a partir da imagem destacada de um post.
    *   Salva as imagens geradas no diretório `wp-content/uploads/og/`.
    *   Injeta todas as meta tags OG necessárias (`og:title`, `og:description`, `og:image`, etc.) no `<head>` de páginas singulares para um compartilhamento otimizado.
    *   Fornece uma imagem de fallback para OG.
*   **Tipos de Post Personalizados (CPTs):**
    *   **Estimativas (`ato`):** Para gerenciar atos e estimativas oficiais.
    *   **Processo Seletivo (`processo`):** Para processos de seleção de emprego.
    *   **Notícias (`noticia`):** Para artigos de notícias.
    *   **Impresso (`impresso`):** Para comunicados à imprensa e materiais impressos.
    *   **Inexigibilidade / Dispensa (`dispensa`):** Para avisos de contratação legal.
    *   **Produções (`producao`):** Para outras produções institucionais.
*   **Menus de Navegação Personalizados:** Registra quatro locais de menu: `Menu Topo`, `Menu Social`, `Menu Principal` e `Menu Unidades`.
*   **Integração VLibras:** Adiciona o widget oficial de acessibilidade em Língua Brasileira de Sinais (`VLibras`) no rodapé do site.
*   **Performance:**
    *   Remove o `jquery-migrate.js` do front-end.
    *   Implementa um sistema de cache HTML simples para usuários não logados, armazenando arquivos estáticos no diretório `/cache/`. O cache é automaticamente limpo quando os posts são atualizados.
*   **Integração CSS do Elementor:** Enfileira a folha de estilo de um template específico do Elementor globalmente.

## Instalação

1.  Faça o upload da pasta `igesdf-core` para o diretório `/wp-content/plugins/`.
2.  Ative o plugin através do menu 'Plugins' no WordPress.
3.  As funcionalidades do plugin, como os Tipos de Post Personalizados e recursos de back-end, estarão ativos imediatamente.
4.  Para usar os shortcodes, adicione o bloco de shortcode correspondente em suas páginas ou posts.

## Shortcodes

Os seguintes shortcodes estão disponíveis:

### `[linha_do_tempo]`
Exibe uma linha do tempo filtrável para "Atos" (Estimativas).
- **Funcionalidade:** Permite aos usuários filtrar posts por ano, categoria e status (`Em andamento`, `Finalizado`, `Suspenso ou cancelado`). Utiliza AJAX para carregar e exibir os resultados dinamicamente.

### `[inexigibilidade_busca]`
Cria uma lista pesquisável e filtrável para os posts de "Inexigibilidade" and "Dispensa".
- **Funcionalidade:** Renderiza uma lista de posts com um campo de busca e filtros de categoria. Inclui paginação.

### `[proc_seletivo]`
Exibe uma lista de "Processos Seletivos".
- **Funcionalidade:** Mostra oportunidades de emprego com indicadores de status (ex: `Inscrições abertas`, `Em andamento`). Inclui um formulário de busca.

### `[proc_seletivo_get_status]`
Exibe o status de um processo seletivo específico.
- **Uso:** Destinado para uso dentro do loop em um template single do CPT `processo`.

### `[proc_seletivo_get_prazo]`
Exibe o prazo de inscrição para um processo seletivo.
- **Uso:** Destinado para uso dentro do loop em um template single do CPT `processo`.

### `[proc_seletivo_inscricoes_botao]`
Exibe um botão "Inscreva-se" se um processo seletivo estiver com inscrições abertas.
- **Uso:** Destinado para uso dentro do loop em um template single do CPT `processo`.

### `[single_audio]`
Incorpora um player de áudio único.
- **Funcionalidade:** Usa AmplitudeJS para criar um player para um arquivo de áudio anexado a um post (ex: via campo personalizado).

### `[archive_audio]`
Exibe uma playlist de todos os posts que contêm áudio.
- **Funcionalidade:** Cria uma playlist completa com AmplitudeJS, buscando todos os posts com um arquivo de áudio associado.

## Changelog

### 1.0.0
*   Lançamento inicial.
*   Plugin criado para abstrair as funcionalidades principais do tema.
*   Adicionados Tipos de Posts Personalizados, shortcodes, gerenciamento de tags OG e recursos de performance.

