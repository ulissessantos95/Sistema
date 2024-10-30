# Sistema
Sistema de login
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Biblioteca</title>
</head>
<body>
    <h1>Biblioteca</h1>
    <div class="container">
        <div class="bib">
            <h3>Cadastro</h3>
            <label for="cadTitulo">Titulo</label>&nbsp;
            <input type="text" id="cadTitulo" placeholder="Ex:Predador Americano"><br><br>
            <label for="cadAutor">Autor</label>&nbsp;
            <input type="text" id="cadAutor" placeholder="Ex:Maureen Callahan"><br><br>
            <label for="cadGen">Genero</label>&nbsp;
            <input type="text" id="cadGen" placeholder="Ex:Documentario"><br><br>
            <label for="cadEditora">Genero</label>&nbsp;
            <input type="text" id="cadEditora" placeholder="Ex:Darkside"><br><br>
            <label for="CadIsbn">Isbn</label>&nbsp;
            <input type="text" id="cadIsbn" placeholder="Ex:123"><br>

            <button onclick="add()">Cadastrar Livro</button>
        </div>
        <div class="bib">
            <h3>Listagem de Livros</h3>
            <p id="acervo"></p>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

////////////////////////////////////////////////////////////////////////

let biblioteca = [];
let inputTitulo = document.getElementById("cadTitulo");
let inputAutor = document.getElementById("cadAutor");
let inputGenero = document.getElementById("cadGen");
let inputEditora = document.getElementById("cadEditora");
let inputIsbn = document.getElementById("ISBN");
let acervo = document.getElementById("acervo");


function add(){
let livros = {
    titulo: inputTitulo.value,
    autor: inputAutor.value,
    genero: inputGenero.value,
    editora: inputEditora.value,
    isbn: inputIsbn.value, 

}
biblioteca.push(livros)
inputTitulo.value = null;
inputAutor.value = null;
inputGenero.value = null;
inputEditora.value = null;
inputIsbn.value = null;
listagem();

}

function listagem(){
    let livros = '';
    for (let livro of biblioteca){
        livros += "Titulo:"+livro.titulo+"<br>";
        livros += "Autor:"+livro.autor+"<br>";
        livros += "Genero:"+livro.genero+"<br>";
        livros += "Editora:"+livro.editora+"<br>";
        livros += "ISBN:"+livro.isbn+"<br>";
        livros += "-------------------------- <br>";
    }
    acervo.innerHTML = livros;
}
