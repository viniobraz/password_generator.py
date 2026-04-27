import random
import string


def gerar_senha(tamanho, usar_numeros=True, usar_simbolos=True):
    letras = string.ascii_letters
    numeros = string.digits
    simbolos = string.punctuation

    caracteres = letras

    if usar_numeros:
        caracteres += numeros

    if usar_simbolos:
        caracteres += simbolos

    senha = ''.join(random.choice(caracteres) for _ in range(tamanho))
    return senha


def main():
    print("=== Gerador de Senhas ===")

    tamanho = int(input("Tamanho da senha: "))
    numeros = input("Incluir números? (s/n): ").lower() == 's'
    simbolos = input("Incluir símbolos? (s/n): ").lower() == 's'

    senha = gerar_senha(tamanho, numeros, simbolos)

    print(f"\nSenha gerada: {senha}")


if __name__ == "__main__":
    main()
