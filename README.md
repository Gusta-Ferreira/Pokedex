# Pokédex - Projeto de Treinamento

Este é um projeto desenvolvido para praticar e aprimorar habilidades em HTML, CSS e JavaScript. A aplicação permite buscar e visualizar informações de Pokémons utilizando a API PokeAPI.

## Tecnologias Utilizadas
- HTML5
- CSS3
- JavaScript (ES6+)
- PokeAPI (https://pokeapi.co/)

## Funcionalidades
- Buscar um Pokémon pelo nome ou número na Pokédex.
- Exibir imagem animada do Pokémon (caso esteja disponível na API).
- Navegar entre os Pokémons anteriores e próximos.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

```
/
|-- index.html      # Estrutura do site
|-- style.css       # Estilização do site
|-- script.js       # Lógica e manipulação da API
```

## Como Usar
1. Clone ou baixe este repositório.
2. Abra o arquivo `index.html` em um navegador.
3. Use a barra de pesquisa para buscar um Pokémon pelo nome ou número.
4. Utilize os botões "Anterior" e "Próximo" para navegar entre os Pokémons.

## Exemplo de Código
### JavaScript (Busca e Renderização do Pokémon)
```js
const fetchPokemon = async (pokemon) => {
  const APIResponse = await fetch(`https://pokeapi.co/api/v2/pokemon/${pokemon}`);
  if (APIResponse.status === 200) {
    return await APIResponse.json();
  }
};

const renderPokemon = async (pokemon) => {
  const data = await fetchPokemon(pokemon);
  if (data) {
    pokemonName.innerHTML = data.name;
    pokemonNumber.innerHTML = data.id;
    pokemonImage.src = data.sprites.versions['generation-v']['black-white'].animated.front_default;
  } else {
    pokemonName.innerHTML = 'Not found :c';
  }
};
```

---
Desenvolvido para fins de aprendizado e aprimoramento.

