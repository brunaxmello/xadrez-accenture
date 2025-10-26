# Sistema de Xadrez - Movimento do Peão

Este projeto simula o jogo de xadrez, focado na implementação robusta e validada do movimento do peão. Utiliza uma arquitetura modular em Java para gerenciar o tabuleiro, as peças e o fluxo do jogo, com interações via `JOptionPane`.

## Funcionalidades Implementadas
* **Tabuleiro Matriz 8x8:** O tabuleiro é representado por uma matriz de peças (`matriz 8x8 de Peao`), com os peões posicionados nas linhas 1 (brancas) e 6 (pretas).
* **Movimento do Peão (Regras Específicas):**
    * **Avanço Inicial:** Peões podem avançar 1 casa ou 2 casas no primeiro movimento.
    * **Bloqueio:** Verifica se há peça na frente.
    * **Direção:** Não permite avançar para trás.
    * **Validação:** Não é permitido sobrescrever peça aliada ou realizar movimentos fora do tabuleiro.
* **Interação com o Usuário:** Leitura de coordenadas de origem e destino via caixa de diálogo (`JOptionPane`).
* **Fluxo de Jogo:** Gerenciado pela classe `Jogo`, com loop principal para solicitação de movimento e alternância de turno.

## Arquitetura de Classes

O sistema é dividido em quatro pacotes principais:

## Arquitetura de Classes

| Pacote | Classe | Responsabilidade Principal |
| :--- | :--- | :--- |
| `xadrez.controle` | `Jogo` | Controla o fluxo do jogo, entrada do usuário, alternância de turnos e exibe o tabuleiro. |
| `xadrez.peca` | `Peao` | Representa o peão, encapsulando posição, cor, e regras de movimento/captura. |
| `xadrez.peca` | `Cor` | Enum interno que define as cores (`BRANCO`, `PRETO`) para peças e comparação de turnos. |
| `xadrez.tabuleiro` | `Tabuleiro` | Representa a matriz 8x8 e gerencia a posição, adição e remoção das peças. |
| `xadrez.exceptions`| `XadrezException` | Classe customizada para tratar erros de regras do jogo (ex: movimento inválido, posição fora do tabuleiro) e feedback de erro ao jogador. |


## Tratamento de Erros
* **Feedback Completo:** Mensagens de sucesso, cancelamento, e feedback de erro ao jogador.
* **Tratamento de Exceções:** Entrada de coordenadas inválida ou movimentos que violam as regras são tratados com exceções.

 ## Como Iniciar
1.  O tabuleiro é exibido na tela, mostrando os peões com representação Unicode.
2.  O jogador insere as coordenadas de origem e destino (Linha/Coluna).
3.  O sistema executa o movimento ou exibe um erro.
4.  O turno é alternado.
