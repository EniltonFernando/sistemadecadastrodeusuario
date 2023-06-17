# sistemadecadastrodeusuario
Crie um sistema de cadastro de usuários.

# Definindo a classe User
class User:
    def __init__(self, id, nome, cpf, idade):
        self.id = id
        self.nome = nome
        self.cpf = cpf
        self.idade = idade

# Criando uma lista vazia para armazenar os usuários
usuarios = []

# Função para exibir as informações de um usuário
def exibir_usuario(usuario):
    print(f"ID: {usuario.id}")
    print(f"Nome: {usuario.nome}")
    print(f"CPF: {usuario.cpf}")
    print(f"Idade: {usuario.idade}")
    print()

# Função para inserir um novo usuário
def inserir_usuario(id, nome, cpf, idade):
    usuario = User(id, nome, cpf, idade)
    usuarios.append(usuario)
    print("Usuário inserido com sucesso!")

# Função para alterar o nome de um usuário
def alterar_nome_usuario(id_usuario, novo_nome):
    for usuario in usuarios:
        if usuario.id == id_usuario:
            usuario.nome = novo_nome
            print("Nome do usuário alterado com sucesso!")
            return
    print("Usuário não encontrado.")

# Função para excluir um usuário
def excluir_usuario(id_usuario):
    for i, usuario in enumerate(usuarios):
        if usuario.id == id_usuario:
            del usuarios[i]
            print("Usuário excluído com sucesso!")
            return
    print("Usuário não encontrado.")

# Inserindo 5 usuários no sistema
inserir_usuario(1, "João", "111.111.111-11", 25)
inserir_usuario(2, "Maria", "222.222.222-22", 30)
inserir_usuario(3, "Pedro", "333.333.333-33", 28)
inserir_usuario(4, "Ana", "444.444.444-44", 35)
inserir_usuario(5, "José", "555.555.555-55", 40)

# Alterando o nome do usuário número 2
alterar_nome_usuario(2, "Mariana")

# Inserindo um novo usuário no sistema
inserir_usuario(6, "Carlos", "666.666.666-66", 45)

# Excluindo o penúltimo usuário
excluir_usuario(5)

# Exibindo os usuários restantes no sistema
print("Usuários cadastrados:")
for usuario in usuarios:
    exibir_usuario(usuario)
