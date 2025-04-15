<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Minha Biblioteca</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f4f4f4;
    }
    header, footer {
      background-color: #2e3b4e;
      color: white;
      text-align: center;
      padding: 15px;
    }
    nav {
      background-color: #444;
      text-align: center;
    }
    nav a {
      color: white;
      padding: 14px 20px;
      display: inline-block;
      text-decoration: none;
    }
    nav a:hover {
      background-color: #ddd;
      color: black;
    }
    main {
      padding: 20px;
    }
    .livros, .estante, .carrinho {
      margin-bottom: 30px;
    }
    .livro {
      border: 1px solid #ccc;
      background: white;
      padding: 10px;
      margin: 10px;
      width: 180px;
      text-align: center;
    }
    .livro img {
      width: 100px;
      height: 140px;
      object-fit: cover;
    }
    .livros-container {
      display: flex;
      flex-wrap: wrap;
    }
    button {
      background-color: #2e3b4e;
      color: white;
      border: none;
      padding: 8px 12px;
      margin-top: 8px;
      cursor: pointer;
    }
    button:hover {
      background-color: #4CAF50;
    }
    .caixa {
      border-top: 2px solid #2e3b4e;
      background: white;
      padding: 15px;
    }
    ul {
      padding-left: 20px;
    }
  </style>
</head>
<body>

<header>
  <h1>Minha Biblioteca Online</h1>
</header>

<nav>
  <a href="#">Livros</a>
  <a href="#">Estante</a>
  <a href="#">Carrinho</a>
</nav>

<main>
  <!-- Lista de Livros -->
  <section class="livros">
    <h2>Livros Disponíveis</h2>
    <div class="livros-container" id="lista-livros">
      <!-- Livros são gerados aqui por JavaScript -->
    </div>
  </section>

  <!-- Estante Virtual -->
  <section class="estante">
    <h2>Sua Estante</h2>
    <div class="caixa">
      <ul id="lista-estante"></ul>
    </div>
  </section>

  <!-- Carrinho de Compras -->
  <section class="carrinho">
    <h2>Carrinho de Compras</h2>
    <div class="caixa">
      <ul id="lista-carrinho"></ul>
      <p><strong>Total:</strong> R$ <span id="total">0.00</span></p>
    </div>
  </section>
</main>

<footer>
  <p>&copy; 2025 Minha Biblioteca</p>
</footer>

<script>
  const livros = [
    { nome: "O Senhor dos Anéis", preco: 59.90, imagem: "https://via.placeholder.com/100x140?text=Livro+1" },
    { nome: "Dom Casmurro", preco: 29.90, imagem: "https://via.placeholder.com/100x140?text=Livro+2" },
    { nome: "1984", preco: 39.90, imagem: "https://via.placeholder.com/100x140?text=Livro+3" },
  ];

  const listaLivros = document.getElementById("lista-livros");
  const listaEstante = document.getElementById("lista-estante");
  const listaCarrinho = document.getElementById("lista-carrinho");
  const totalSpan = document.getElementById("total");

  let total = 0;

  function renderizarLivros() {
    livros.forEach((livro) => {
      const div = document.createElement("div");
      div.className = "livro";
      div.innerHTML = `
        <img src="${livro.imagem}" alt="${livro.nome}">
        <p><strong>${livro.nome}</strong></p>
        <p>R$ ${livro.preco.toFixed(2)}</p>
        <button onclick="adicionarEstante('${livro.nome}')">Adicionar à Estante</button>
        <button onclick="adicionarCarrinho('${livro.nome}', ${livro.preco})">Comprar</button>
      `;
      listaLivros.appendChild(div);
    });
  }

  function adicionarEstante(nome) {
    const item = document.createElement("li");
    item.textContent = nome;
    listaEstante.appendChild(item);
  }

  function adicionarCarrinho(nome, preco) {
    const item = document.createElement("li");
    item.textContent = `${nome} - R$ ${preco.toFixed(2)}`;
    listaCarrinho.appendChild(item);
    total += preco;
    totalSpan.textContent = total.toFixed(2);
  }

  renderizarLivros();
</script>

</body>
</htmlbutton {
  


