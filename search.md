---
layout: page
title: Resultados da Busca
---

<h3>Resultados para: <span id="search-query"></span></h3>

<ul id="results-container"></ul>

<script src="{{ '/assets/js/simple-jekyll-search.min.js' | relative_url }}"></script>
<script>
  // Pega o termo de busca da URL (ex: ?query=meu-termo)
  const urlParams = new URLSearchParams(window.location.search);
  const searchQuery = urlParams.get('query');
  document.getElementById('search-query').textContent = searchQuery;

  var sjs = SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json',
    searchResultTemplate: '<li><a href="{url}">{title}</a><p>{content}</p></li>',
    noResultsText: 'Nenhum resultado encontrado.',
    limit: 10,
    fuzzy: false,
    // Corta o trecho do conteúdo para mostrar onde a palavra foi encontrada
    excerpt_length: 150 
  });

  // Realiza a busca automaticamente ao carregar a página
  if(searchQuery) {
    // Preenche o campo de busca com o termo da URL
    document.getElementById('search-input').value = searchQuery;
    sjs.search(searchQuery);
  }
</script>
