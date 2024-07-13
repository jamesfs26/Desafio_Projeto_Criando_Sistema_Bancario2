# 2ª Etapa do Desafio de Projeto do Curso Python AI Backend Developer (DIO) em parceria com a Vivo


Na segunda etapa do desafio de projeto do Curso Python AI Backend Developer (DIO) em parceria com a Vivo, implementamos nosso sistema bancário com novos recursos aprendidos no módulo de estrutura de dados em Python. O conhecimento de nível intermediário passado pelo professor Guilherme Carvalho (Gui) neste módulo me ensinou sobre listas, tuplas, conjuntos, dicionários e funções. Com esses conhecimentos, reestruturei o código que antes era feito em sua maioria por variáveis, estruturas condicionais e de repetição.
Descrição das Principais Mudanças, Melhorias e Funcionalidades
Etapa 1
menu = '''

[d] depositar
[s] sacar
[e] extrato
[q] sair

=>'''

saldo = 5000
limite = 1000
extrato = ""
numero_saques = 0
LIMITE_SAQUE = 5
total_saque = 0  # Variável para armazenar o total dos saques realizados

while True:

    opcao = input(menu)
    if opcao == "d":
        valor = float(input("Informe o valor de depósito: "))
        
        if valor > 0:
            saldo += valor  # Atualiza o saldo com o valor depositado
            extrato += f"Depósito: R${valor:.2f}\n"
        else:
            print("Operação falhou, o valor informado é inválido.")

    elif opcao == "s":
        valor = float(input("Informe o valor de saque: "))
      
        excedeu_saldo = valor > saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUE
       
        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente")
          
        elif excedeu_limite:
            print("Operação falhou! O valor de saque supera o limite.")

        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedidos.")

        elif valor > 0:
            saldo -= valor  # Atualiza o saldo com o valor sacado
            extrato += f"Saque: R${valor:.2f}\n"
            numero_saques += 1
            total_saque += valor  # Atualiza o total de saques realizados
        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "e":
        print("\n=============== EXTRATO ===============")
        if not extrato:
            print("Não foram realizadas movimentações.")
        else:
            print(extrato)
            print(f"Total de saques realizados: R$ {total_saque:.2f}")
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("=========================================")

    elif opcao == "q":
        break
    
    else:
        print("Operação inválida, por favor, selecione novamente a opção desejada.")

# Na primeira etapa, o código era mais simples e focava nas operações básicas de um sistema bancário. Aqui está um resumo das principais características:

    * Menu Simples: O menu oferecia opções de depósito, saque, extrato e sair.
    * Gerenciamento de Saldo: Utilização de variáveis simples (saldo, limite, extrato, numero_saques) para armazenar informações.
    * Operações: Depósitos e saques eram feitos diretamente nas variáveis.
    * Limitações: Controle de saldo insuficiente, limite de saque e número máximo de saques diários.
    * Exibição de Extrato: Exibição das transações realizadas e do saldo atual.

# Etapa 2:

Na segunda etapa, o sistema foi aprimorado com o uso de estruturas de dados mais complexas e funções, resultando em um código mais modular e escalável.
Aqui estão as melhorias e funcionalidades adicionadas:

    Uso de Estruturas de Dados:
        Listas para armazenar transações e contas.
        Dicionários para armazenar informações de clientes e contas.
    Funções: Implementação de funções para modularizar o código e facilitar a manutenção e expansão:
        menu: Exibe o menu de opções.
        depositar: Realiza depósitos em contas.
        sacar: Realiza saques, com verificação de saldo e limites.
        exibir_extrato: Exibe o extrato da conta.
        criar_usuario: Adiciona um novo usuário ao sistema.
        filtrar_usuario: Filtra usuários pelo CPF.
        criar_conta: Cria novas contas bancárias.
        listar_contas: Lista todas as contas.
        excluir_usuario: Exclui usuários do sistema.
        excluir_conta: Exclui contas bancárias.
    Código Modular: Separação de lógica em funções específicas para maior clareza e reutilização de código.
    Melhorias de Funcionalidade:
        Cadastro de Usuários e Contas: Funções dedicadas para criação e exclusão de usuários e contas.
        Controle de Transações: Armazenamento de todas as transações realizadas em listas, permitindo exibição detalhada do extrato.
        Melhoria na Verificação de Limites: Funções dedicadas para verificar saldo, limite de saque e número de saques diários.
        Listagem de Contas: Possibilidade de listar todas as contas existentes.
        Facilidade de Adição de Novos Clientes: Uso de dicionários para adicionar novos clientes de forma simples e eficaz.
        Aprimoramento da Interação com o Usuário: Exibição detalhada das transações e saldo atual no extrato.
