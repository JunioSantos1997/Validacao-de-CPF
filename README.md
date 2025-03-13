# Validador de CPF - Algoritmo em JavaScript

## 🚀 Visão Geral

Esse algoritmo em **JavaScript** valida CPFs de forma eficiente e simples, aplicando a fórmula oficial dos dígitos verificadores. Ideal para projetos que necessitam garantir a autenticidade de dados cadastrais!

## 🛠️ Tecnologias Utilizadas

- **JavaScript**: Linguagem principal para implementar a lógica de validação.
- **Array Manipulation**: Utilização de métodos como `.slice()`, `.reduce()` e `.splice()` para validar o CPF de forma concisa e otimizada.
- **Expressões Regulares**: Limpeza do CPF para remover caracteres não numéricos.

## ⚙️ Como Funciona

1. **Limpeza**: O CPF é transformado em uma string numérica, removendo pontuações com expressões regulares.
2. **Validação dos Dígitos**:
   - O **primeiro dígito** é calculado com base nos 9 primeiros números usando um array e um peso específico.
   - O **segundo dígito** é calculado a partir dos 10 números, já considerando o primeiro dígito.
3. **Resultado**: Se os dígitos calculados coincidem com os fornecidos, o CPF é válido.

## 🔥 Código de Exemplo

```javascript
let cpf = '705.484.450-52'; // CPF para validação
let cpfLimpo = cpf.replace(/\D+/g, ''); // Remove caracteres não numéricos
let cpfArray = Array.from(cpfLimpo); // Converte CPF em array de números
let cpfValidado = validaDigito2(validaDigito1(cpfArray)); // Valida os dígitos
let cpfFinal = cpfValidado.join(''); // Recria o CPF validado

if (cpfFinal === cpfLimpo) {
    console.log(`O CPF ${cpf} é válido!`);
} else {
    console.log('CPF INVÁLIDO!');
}
