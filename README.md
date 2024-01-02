function calculadoraSimples() {
  while (true) {
    // Solicitar operação ao usuário
    const operacao = prompt('Escolha uma operação: (+, -, *, /) ou digite "sair" para encerrar.');

    // Verificar se o usuário deseja sair
    if (operacao.toLowerCase() === 'sair') {
      break;
    }

    // Solicitar dois números ao usuário
    const numero1 = parseFloat(prompt('Digite o primeiro número:'));
    const numero2 = parseFloat(prompt('Digite o segundo número:'));

    // Verificar a operação escolhida e realizar o cálculo
    let resultado;
    switch (operacao) {
      case '+':
        resultado = numero1 + numero2;
        break;
      case '-':
        resultado = numero1 - numero2;
        break;
      case '*':
        resultado = numero1 * numero2;
        break;
      case '/':
        // Verificar se o divisor é zero
        if (numero2 !== 0) {
          resultado = numero1 / numero2;
        } else {
          alert('Não é possível dividir por zero. Tente novamente.');
          continue; // Reinicia o loop para evitar a exibição do resultado inválido.
        }
        break;
      default:
        alert('Operação inválida. Tente novamente.');
        continue; // Reinicia o loop para evitar a exibição do resultado inválido.
    }

    // Exibir o resultado ao usuário
    alert(`Resultado: ${resultado}`);
  }

  alert('Calculadora encerrada. Obrigado!');
}

// Chame a função para iniciar a calculadora
calculadoraSimples();
