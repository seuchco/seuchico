# Análise de Gargalos e Melhorias - Projeto "seuchico"

Após a análise do código fonte do repositório, foram identificados os seguintes pontos de melhoria, divididos por categorias:

## 1. Estrutura e Organização de Código
- **Repetição de Código (DRY):** O cabeçalho (`header`) e o rodapé (`footer`) estão duplicados em todos os arquivos HTML (`index.html`, `sobre.html`, `projetos.html`). Isso dificulta a manutenção, pois qualquer alteração precisa ser feita em três lugares diferentes.
- **Falta de Componentização:** Como o projeto usa HTML puro, seria interessante considerar o uso de um gerador de sites estáticos (como Jekyll ou Eleventy) ou simplesmente usar JavaScript para carregar componentes comuns.
- **CSS Desorganizado:** O arquivo `main.css` contém algumas propriedades órfãs ou com erros de sintaxe (ex: `margin: left 75px; right: 90px;` na linha 89).

## 2. Performance e SEO
- **Carregamento de Fontes:** As fontes do Google Fonts são carregadas sem a diretiva `preconnect`, o que pode atrasar levemente a renderização.
- **Metadados de SEO:** Faltam meta tags de Open Graph (para compartilhamento em redes sociais) e uma descrição (`meta description`) mais detalhada para cada página.
- **Scripts Bloqueantes:** O script `script.js` é carregado no final do body em algumas páginas, mas no `index.html` ele sequer está sendo chamado, o que faz com que a funcionalidade de esconder o header no scroll não funcione na home.

## 3. Acessibilidade (A11y)
- **Contraste e Semântica:** Embora o uso de `article` e `section` seja bom, faltam atributos `aria-label` em elementos interativos e uma melhor estruturação de níveis de cabeçalho (H1, H2, H3) para leitores de tela.
- **Navegação:** O link ativo no menu não possui uma classe visual ou de acessibilidade (`aria-current="page"`) para indicar em qual página o usuário está.

## 4. Experiência do Usuário (UX)
- **Responsividade:** O layout usa grid, o que é ótimo, mas a `header` fixa com `padding: 40px` pode ocupar muito espaço em telas pequenas.
- **Feedback Visual:** Falta um estado de "active" ou "hover" mais pronunciado nos cards de projetos.

## 5. Repositório e Documentação
- **README Inexistente/Pobre:** O repositório não possui um README que explique como rodar o projeto localmente ou qual o objetivo técnico.
- **Issues:** Não há rastreamento de tarefas ou bugs no GitHub.
