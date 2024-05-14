class Livro:
    def __init__(self, titulo, autor, ano, genero, num_paginas, emprestado=False):
        self.titulo = titulo
        self.autor = autor
        self.ano = ano
        self.genero = genero
        self.num_paginas = num_paginas
        self.emprestado = emprestado

    def __str__(self):
        status = "Disponível" if not self.emprestado else "Emprestado"
        return f"{self.titulo} - {self.autor} ({self.ano}) - Gênero: {self.genero}, Páginas: {self.num_paginas}, Status: {status}"


class Biblioteca:
    def __init__(self):
        self.livros = []

    def adicionar_livro(self, livro):
        self.livros.append(livro)

    def remover_livro(self, titulo):
        for livro in self.livros:
            if livro.titulo == titulo:
                self.livros.remove(livro)
                print(f"O livro '{titulo}' foi removido da biblioteca.")
                return
        print(f"O livro '{titulo}' não foi encontrado na biblioteca.")

    def listar_livros(self):
        print("Livros na biblioteca:")
        for livro in self.livros:
            print(livro)


# Exemplo de uso:
minha_biblioteca = Biblioteca()

livro1 = Livro("Dom Quixote", "Miguel de Cervantes", 1605, "Ficção", 863)
livro2 = Livro("A Metamorfose", "Franz Kafka", 1915, "Ficção", 224, emprestado=True)
livro3 = Livro("1984", "George Orwell", 1949, "Ficção", 328)

minha_biblioteca.adicionar_livro(livro1)
minha_biblioteca.adicionar_livro(livro2)
minha_biblioteca.adicionar_livro(livro3)

minha_biblioteca.listar_livros()

# Duando o livro "Dom Quixote"
minha_biblioteca.remover_livro("Dom Quixote")

minha_biblioteca.listar_livros()
