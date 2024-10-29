# alurajail
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aluraflix</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Aluraflix</h1>
    </header>
    <main>
        <div class="add-movie">
            <input type="text" id="movieTitle" placeholder="Nome do Filme">
            <input type="text" id="movieImage" placeholder="URL da Imagem">
            <button onclick="addMovie()">Adicionar Filme</button>
        </div>
        <div id="movieCatalog" class="catalog"></div>
    </main>
    <script src="script.js"></script>
</body>
</html>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
}

header {
    margin-bottom: 20px;
}

h1 {
    color: #FF6347;
}

.add-movie {
    margin-bottom: 20px;
}

input {
    padding: 10px;
    margin-right: 10px;
    border: none;
    border-radius: 5px;
}

button {
    padding: 10px 20px;
    background-color: #FF6347;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.catalog {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

.movie-card {
    background-color: #333;
    border-radius: 10px;
    overflow: hidden;
    width: 200px;
    text-align: center;
}

.movie-card img {
    width: 100%;
    height: 300px;
    object-fit: cover;
}

.movie-card h3 {
    padding: 10px;
    font-size: 18px;
}

const movieCatalog = document.getElementById("movieCatalog");

function addMovie() {
    const movieTitle = document.getElementById("movieTitle").value;
    const movieImage = document.getElementById("movieImage").value;

    if (movieTitle && movieImage) {
        // Cria a estrutura do card de filme
        const movieCard = document.createElement("div");
        movieCard.classList.add("movie-card");

        const img = document.createElement("img");
        img.src = movieImage;
        img.alt = `Imagem do filme ${movieTitle}`;

        const title = document.createElement("h3");
        title.innerText = movieTitle;

        movieCard.appendChild(img);
        movieCard.appendChild(title);
        movieCatalog.appendChild(movieCard);

        // Limpa os campos de entrada
        document.getElementById("movieTitle").value = "";
        document.getElementById("movieImage").value = "";
    } else {
        alert("Por favor, insira o nome e a URL da imagem do filme.");
    }
}
