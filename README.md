# Construindo-uma-Pok-dex-com-JavaScript

Construir uma Pokédex com JavaScript é uma ótima maneira de aplicar seus conhecimentos de desenvolvimento web e aprender mais sobre APIs REST. Aqui estão alguns passos que você pode seguir para criar sua Pokédex:

1. **Entenda a API REST**: Pesquise e escolha uma API Pokémon, como a [PokéAPI](https://pokeapi.co/), que é uma API RESTful pública. Familiarize-se com a documentação para entender como fazer requisições e receber dados dos Pokémon.

2. **Configure o Ambiente de Desenvolvimento**:
   - Instale o Git, se ainda não o tiver, e configure-o.
   - Crie um repositório no GitHub para o seu projeto.
   - Configure seu ambiente de desenvolvimento local com um editor de código, como o Visual Studio Code.

3. **Estruture o Projeto**:
   - Crie um arquivo HTML para a estrutura da sua Pokédex.
   - Adicione um arquivo CSS para estilizar a interface.
   - Prepare um arquivo JavaScript para lidar com a lógica e as requisições à API.

4. **Desenvolva a Interface da Pokédex**:
   - Use HTML e CSS para criar a interface do usuário.
   - Pense em como você quer exibir as informações dos Pokémon, como imagens, nomes, tipos, etc.

5. **Implemente a Lógica em JavaScript**:
   - Use `fetch` para fazer requisições à API e obter dados dos Pokémon.
   - Trate os dados recebidos e atualize a interface com as informações dos Pokémon.
   - Adicione funcionalidades como busca, filtragem e paginação, se necessário.

6. **Teste Sua Aplicação**:
   - Teste todas as funcionalidades para garantir que tudo está funcionando como esperado.
   - Verifique se a interface é responsiva e funciona bem em diferentes dispositivos.

7. **Publique e Compartilhe**:
   - Faça o deploy da sua Pokédex em um serviço de hospedagem, como o GitHub Pages.
   - Compartilhe o link do seu projeto com a comunidade e peça feedback.

8. **Use o Git/GitHub**:
   - Faça commits regulares durante o desenvolvimento para manter um histórico das suas mudanças.
   - Use branches para trabalhar em novas funcionalidades sem afetar o código principal.
   - Abra pull requests para mesclar suas alterações na branch principal quando estiverem prontas.

Vamos criar um exemplo simples de uma Pokédex em JavaScript. Neste caso, usaremos a [PokéAPI](https://pokeapi.co/) para obter informações sobre os Pokémon.

1. **Configuração Inicial**:
   - Crie um novo diretório para o projeto da Pokédex.
   - Dentro desse diretório, crie os seguintes arquivos:
     - `index.html`: Estrutura básica do HTML.
     - `styles.css`: Arquivo CSS para estilizar a interface.
     - `script.js`: Arquivo JavaScript para a lógica da Pokédex.

2. **HTML (index.html)**:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <link rel="stylesheet" href="styles.css">
       <title>Pokédex</title>
   </head>
   <body>
       <h1>Pokédex</h1>
       <div id="pokemon-list"></div>
       <script src="script.js"></script>
   </body>
   </html>
   ```

3. **CSS (styles.css)**:
   ```css
   body {
       font-family: Arial, sans-serif;
       text-align: center;
   }

   h1 {
       color: #e74c3c;
   }
   ```

4. **JavaScript (script.js)**:
   ```javascript
   const pokemonList = document.getElementById("pokemon-list");

   async function fetchPokemonData() {
       try {
           const response = await fetch("https://pokeapi.co/api/v2/pokemon?limit=10");
           const data = await response.json();
           const pokemons = data.results;

           pokemons.forEach(async (pokemon) => {
               const response = await fetch(pokemon.url);
               const pokemonData = await response.json();

               const pokemonCard = document.createElement("div");
               pokemonCard.classList.add("pokemon-card");
               pokemonCard.innerHTML = `
                   <img src="${pokemonData.sprites.front_default}" alt="${pokemon.name}">
                   <p>${pokemon.name}</p>
               `;

               pokemonList.appendChild(pokemonCard);
           });
       } catch (error) {
           console.error("Erro ao buscar dados dos Pokémon:", error);
       }
   }

   fetchPokemonData();
   ```

5. **Resultado**:
   - O código acima busca os dados dos 10 primeiros Pokémon da PokéAPI e exibe seus nomes e imagens em uma lista simples.

6. **Estilização Adicional**:
   - Você pode adicionar mais estilos ao arquivo `styles.css` para melhorar a aparência da sua Pokédex.

Lembre-se de que este é apenas um exemplo básico. Você pode expandir sua Pokédex adicionando mais funcionalidades, como detalhes individuais de cada Pokémon, pesquisa, filtros e muito mais. 

https://github.com/digitalinnovationone/js-developer-pokedex
