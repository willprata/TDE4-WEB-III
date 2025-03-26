#EX.1
numeros_por_extenso = (
    "zero", "um", "dois", "três", "quatro", "cinco", "seis", "sete", "oito", "nove",
    "dez", "onze", "doze", "treze", "quatorze", "quinze", "dezesseis", "dezessete", "dezoito", "dezenove", "vinte"
)

while True:
    try:
        numero = int(input("Digite um número entre 0 e 20: "))
        if 0 <= numero <= 20:
            print(f"Você digitou o número {numeros_por_extenso[numero]}.")
            break
        else:
            print("Número fora do intervalo. Tente novamente.")
    except ValueError:
        print("Entrada inválida. Digite um número inteiro.")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.2
lista = []

for i in range(10):
    numero = int(input(f"Digite o {i+1}º número: "))
    lista.append(numero)

valores_diferentes = len(set(lista))

print(f"Quantidade de valores diferentes na lista: {valores_diferentes}")


#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.3
valores = []

for i in range(4):
    numero = int(input(f"Digite o {i+1}º valor: "))
    valores.append(numero)

print(f"\nA lista de valores digitados: {valores}")
print(f"A quantidade de vezes que o valor 9 apareceu: {valores.count(9)}")

if 3 in valores:
    print(f"O primeiro valor 3 foi digitado na posição {valores.index(3)+1}")
else:
    print("O valor 3 não foi digitado.")

pares = [n for n in valores if n % 2 == 0]
print(f"Os números pares digitados foram: {pares}")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.4
import random

lançamentos = []

for i in range(50):
    lançamento = random.randint(1, 6)
    lançamentos.append(lançamento)

ocorrencias_face_6 = lançamentos.count(6)
percentual_face_6 = (ocorrencias_face_6 / 50) * 100

print(f"Percentual de ocorrências da face 6: {percentual_face_6:.2f}%")


#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.5
dicionario = {
    'olá': 'hello',
    'mundo': 'world',
    'como': 'how',
    'você': 'are you',
    'bem': 'good',
    'por': 'for',
    'favor': 'please',
    'obrigado': 'thank you'
}

palavra = input("Digite uma palavra em português para traduzir para o inglês: ").lower()

if palavra in dicionario:
    print(f"A tradução de '{palavra}' é: {dicionario[palavra]}")
else:
    print(f"A palavra '{palavra}' não foi encontrada no dicionário.")


#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.6
estoque = {}

def exibir_estoque():
    if not estoque:
        print("O estoque está vazio.")
    else:
        print("\nEstoque Atualizado:")
        for produto, quantidade in estoque.items():
            print(f"{produto}: {quantidade} unidades")

def adicionar_produto():
    produto = input("Digite o nome do produto: ").lower()
    quantidade = int(input(f"Digite a quantidade de {produto}: "))
    if produto in estoque:
        estoque[produto] += quantidade
    else:
        estoque[produto] = quantidade
    print(f"Produto '{produto}' adicionado ao estoque.")

def atualizar_produto():
    produto = input("Digite o nome do produto para atualizar a quantidade: ").lower()
    if produto in estoque:
        quantidade = int(input(f"Digite a nova quantidade de {produto}: "))
        estoque[produto] = quantidade
        print(f"Quantidade de '{produto}' atualizada.")
    else:
        print(f"Produto '{produto}' não encontrado no estoque.")

while True:
    print("\n1 - Exibir estoque")
    print("2 - Adicionar produto")
    print("3 - Atualizar produto")
    print("4 - Sair")
    
    opcao = input("Escolha uma opção: ")
    
    if opcao == '1':
        exibir_estoque()
    elif opcao == '2':
        adicionar_produto()
    elif opcao == '3':
        atualizar_produto()
    elif opcao == '4':
        print("Saindo...")
        break
    else:
        print("Opção inválida. Tente novamente.")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.7
idades = []
alturas = []

for i in range(5):
    idade = int(input(f"Digite a idade da {i+1}ª pessoa: "))
    altura = float(input(f"Digite a altura da {i+1}ª pessoa: "))
    idades.append(idade)
    alturas.append(altura)

print("\nIdades e alturas na ordem inversa:")

for i in range(4, -1, -1):
    print(f"Pessoa {i+1}: Idade = {idades[i]}, Altura = {alturas[i]}")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.8
texto = input("Digite uma string: ").lower()

frequencia = {}

for letra in texto:
    if letra.isalpha():  
        if letra in frequencia:
            frequencia[letra] += 1  
        else:
            frequencia[letra] = 1  

print("Frequência das letras:")
for letra, quantidade in frequencia.items():
    print(f"{letra}: {quantidade}")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.9
def calcular_media(notas):
    soma = sum(notas.values())  
    quantidade = len(notas)  
    media = soma / quantidade  
    return {"média": media}  

alunos_notas = {
    "João": 7.5,
    "Maria": 8.0,
    "Pedro": 6.5,
    "Ana": 9.0
}
resultado = calcular_media(alunos_notas)
print(resultado)

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.10
texto = input("Digite uma frase: ").lower()
palavras = texto.split()
contagem_palavras = {}

for palavra in palavras:
    if palavra in contagem_palavras:
        contagem_palavras[palavra] += 1
    else:
        contagem_palavras[palavra] = 1

print("Contagem de palavras:")
print(contagem_palavras)

#-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.11
def verificar_numero(n):
    if n > 0:
        print("Positivo")
    elif n < 0:
        print("Negativo")
    else:
        print("Zero")

#-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.12
def valor_absoluto(n):
    print(abs(n))

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.13
def verificar_soma(a, b, limite):
    if a + b > limite:
        return True
    else:
        return False
#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.14
def somaImposto(taxaImposto, custo):
    custo_com_imposto = custo + (custo * (taxaImposto / 100))
    return custo_com_imposto
  
taxa = float(input("Digite a taxa de imposto (%): "))
custo_item = float(input("Digite o custo do item: "))

custo_final = somaImposto(taxa, custo_item)
print(f"O custo final com imposto é: {custo_final}")

#--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#EX.15
def quantidade_digitos(n):
    return len(str(abs(n)))
  
numero = int(input("Digite um número inteiro: "))
print(f"A quantidade de dígitos é: {quantidade_digitos(numero)}")
