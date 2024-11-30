import json
from datetime import datetime

# Função para carregar dados de um arquivo JSON
def carregar_dados():
    try:
        with open("dados.json", "r") as arquivo:
            return json.load(arquivo)
    except FileNotFoundError:
        return {"pacientes": []}

# Função para salvar dados em um arquivo JSON
def salvar_dados(dados):
    with open("dados.json", "w") as arquivo:
        json.dump(dados, arquivo, indent=4)

# Função para cadastrar novo paciente
def cadastrar_paciente(dados):
    print("\nCadastro de Novo Paciente:")
    nome = input("Nome: ")
    nome_social = input("Nome social: ")
    telefone = input("Telefone: ")
    celular = input("Celular: ")
    contato_emergencia = input("Nome para contato de emergência: ")
    telefone_emergencia = input("Telefone de contato de emergência: ")
    data_proxima_consulta = input("Data da próxima consulta (dd/mm/aaaa): ")
    valor_consulta = input("Valor atual da consulta: ")

    paciente = {
        "nome": nome,
        "nome_social": nome_social,
        "telefone": telefone,
        "celular": celular,
        "contato_emergencia": contato_emergencia,
        "telefone_emergencia": telefone_emergencia,
        "data_proxima_consulta": data_proxima_consulta,
        "historico_consultas": [],
        "valor_consulta": valor_consulta
    }

    dados["pacientes"].append(paciente)
    salvar_dados(dados)
    print("Paciente cadastrado com sucesso!\n")

# Função para listar os pacientes com todos os detalhes
def listar_pacientes(dados):
    print("\nLista de Pacientes:")
    if not dados["pacientes"]:
        print("Nenhum paciente cadastrado.")
    else:
        for i, paciente in enumerate(dados["pacientes"], start=1):
            print(f"{i}. Nome: {paciente['nome']}")
            print(f"   Nome Social: {paciente['nome_social']}")
            print(f"   Telefone: {paciente['telefone']}")
            print(f"   Celular: {paciente['celular']}")
            print(f"   Contato de Emergência: {paciente['contato_emergencia']}")
            print(f"   Telefone de Emergência: {paciente['telefone_emergencia']}")
            print(f"   Data da Próxima Consulta: {paciente['data_proxima_consulta']}")
            print(f"   Valor da Consulta: {paciente['valor_consulta']}")
            print(f"   Histórico de Consultas: {', '.join(paciente['historico_consultas']) if paciente['historico_consultas'] else 'Nenhum registro.'}")
            print("-" * 40)

# Função para editar paciente
def editar_paciente(dados):
    print("\nLista de Pacientes:")
    if not dados["pacientes"]:
        print("Nenhum paciente cadastrado.")
        return

    for i, paciente in enumerate(dados["pacientes"], start=1):
        print(f"{i}. {paciente['nome']}")

    try:
        escolha = int(input("\nSelecione o número do paciente para editar: "))
        paciente = dados["pacientes"][escolha - 1]
        print(f"\nEditando paciente: {paciente['nome']}")

        paciente['nome'] = input(f"Nome ({paciente['nome']}): ") or paciente['nome']
        paciente['nome_social'] = input(f"Nome social ({paciente['nome_social']}): ") or paciente['nome_social']
        paciente['telefone'] = input(f"Telefone ({paciente['telefone']}): ") or paciente['telefone']
        paciente['celular'] = input(f"Celular ({paciente['celular']}): ") or paciente['celular']
        paciente['contato_emergencia'] = input(f"Nome para contato de emergência ({paciente['contato_emergencia']}): ") or paciente['contato_emergencia']
        paciente['telefone_emergencia'] = input(f"Telefone de contato de emergência ({paciente['telefone_emergencia']}): ") or paciente['telefone_emergencia']

        salvar_dados(dados)
        print("Dados atualizados com sucesso!\n")
    except (ValueError, IndexError):
        print("\nOpção inválida. Retornando ao menu.")

# Função para agendar consulta
def agendar_atendimento(dados):
    print("\nLista de Pacientes:")
    for i, paciente in enumerate(dados["pacientes"], start=1):
        print(f"{i}. {paciente['nome']}")

    try:
        escolha = int(input("\nSelecione o número do paciente para agendar consulta: "))
        paciente = dados["pacientes"][escolha - 1]

        data_consulta = input("Digite a data da consulta (dd/mm/aaaa): ")
        horario_consulta = input("Digite o horário da consulta (hh:mm): ")

        consulta = f"{data_consulta} às {horario_consulta}"
        paciente["historico_consultas"].append(consulta)
        paciente["data_proxima_consulta"] = data_consulta

        salvar_dados(dados)
        print("Consulta agendada com sucesso!\n")
    except (ValueError, IndexError):
        print("\nOpção inválida. Retornando ao menu.")

# Função para exibir pacientes do dia
def pacientes_do_dia(dados):
    hoje = datetime.now().strftime("%d/%m/%Y")
    pacientes_hoje = [
        {
            "nome": p["nome"],
            "telefone": p["telefone"],
            "horario": next((h.split(" às ")[1] for h in p["historico_consultas"] if h.startswith(hoje)), "Não especificado")
        }
        for p in dados["pacientes"]
        if p.get("data_proxima_consulta") == hoje
    ]

    if not pacientes_hoje:
        print("\nNenhum paciente marcado para hoje.\n")
    else:
        print("\nPacientes do Dia:")
        for paciente in pacientes_hoje:
            print(f"Nome: {paciente['nome']}, Telefone: {paciente['telefone']}, Horário: {paciente['horario']}")
        print()

# Menu principal
def menu_principal():
    dados = carregar_dados()

    while True:
        print("Menu Principal:")
        print("1. Pacientes")
        print("2. Cadastrar Novo Paciente")
        print("3. Agendar Atendimento")
        print("4. Pacientes do Dia")
        print("5. Sair")

        try:
            escolha = int(input("Escolha uma opção: "))

            if escolha == 1:
                menu_pacientes(dados)
            elif escolha == 2:
                cadastrar_paciente(dados)
            elif escolha == 3:
                agendar_atendimento(dados)
            elif escolha == 4:
                pacientes_do_dia(dados)
            elif escolha == 5:
                print("Saindo do sistema. Até logo!")
                break
            else:
                print("\nOpção inválida. Tente novamente.\n")
        except ValueError:
            print("\nEntrada inválida. Por favor, insira um número.\n")

# Menu de Pacientes
def menu_pacientes(dados):
    while True:
        print("\nMenu de Pacientes:")
        print("1. Listar Pacientes")
        print("2. Editar Paciente")
        print("3. Voltar")
        try:
            escolha = int(input("Escolha uma opção: "))

            if escolha == 1:
                listar_pacientes(dados)
            elif escolha == 2:
                editar_paciente(dados)
            elif escolha == 3:
                break
            else:
                print("\nOpção inválida. Tente novamente.\n")
        except ValueError:
            print("\nEntrada inválida. Por favor, insira um número.\n")

# Executa o menu principal
if __name__ == "__main__":
    menu_principal()
