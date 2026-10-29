# Platform Hunter - Álgebra Linear aplicada a Jogos 2D

Projeto desenvolvido para o **TDE 03** da disciplina de **Matemática Aplicada à Computação**. Trata-se de um jogo de plataforma 2D em Python utilizando `pygame` e `numpy` para demonstrar, na prática, conceitos fundamentais de Álgebra Linear.

## Conceitos de Álgebra Linear Aplicados

- **Vetores em $\mathbb{R}^2$**: Representação de posição (`pos`), velocidade (`velocity`) e gravidade (`gravity`).
- **Base Canônica de $\mathbb{R}^2$**: Uso dos vetores canônicos $E_1 = (1, 0)$ e $E_2 = (0, 1)$.
- **Soma de Vetores e Multiplicação por Escalar**: Atualização física da posição a cada quadro ($p(t + \Delta t) = p(t) + v \cdot \Delta t$).
- **Norma e Distância Euclidiana**: Cálculo da distância entre o inimigo e o jogador ($d = \|p_{\text{player}} - p_{\text{enemy}}\|$).
- **Normalização de Vetores**: Obtenção de vetores unitários ($\hat{v} = \frac{v}{\|v\|}$) para representar direções puras.
- **Produto Interno (Escalar)**: Cálculo de $\hat{f} \cdot \hat{d} = \cos(\theta)$ para verificar se o jogador está dentro do cone de visão (FOV) de $80^\circ$ do inimigo.
- **Matrizes de Transformação Linear e Rotação 2D**: Aplicação de matriz de escala ($S$) e matriz de rotação ($R(\theta)$) compostas ($A = R \cdot S$) para rotacionar os vértices do inimigo em direção ao jogador.

## Incremento Implementado (TDE 03)

- **Mecânica de Dash (Impulso Vetorial) com `SHIFT`**:
  - Utiliza o vetor base $E_1 = (1, 0)$ e a função `normalize()` para atualizar e armazenar o vetor unitário da direção em que o jogador está olhando (`self.facing`).
  - Ao pressionar `SHIFT`, aplica uma **multiplicação por escalar** e **soma vetorial** diretamente sobre o vetor posição do jogador (`self.pos += self.facing * 110.0`), gerando um deslocamento instantâneo na direção atual com tempo de recarga (*cooldown*) de `0.8s`.

## Pré-requisitos e Execução

1. Instale as dependências:
   ```bash
   pip install pygame numpy
   ```

2. Execute o jogo:
   ```bash
   python jogo_algebra_linear.py
   ```

## Controles

| Tecla | Ação |
| :--- | :--- |
| `A` / `D` ou `Setas` | Mover horizontalmente |
| `W` / `Espaço` / `Seta Cima` | Pular |
| `SHIFT` | Dash (Impulso Vetorial) |
| `R` | Reiniciar fase |
| `ESC` | Sair do jogo |
