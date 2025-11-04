# Chrome Dino Runner

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![Pygame](https://img.shields.io/badge/Pygame-2.0+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

Uma versão alternativa e aprimorada do clássico jogo do dinossauro do Google Chrome, desenvolvido em Python utilizando a biblioteca Pygame.

## Sobre o Projeto

Este projeto foi desenvolvido como parte do **Módulo 2** do curso de admissão para a **Jala University**. O objetivo era criar uma implementação funcional e criativa do famoso jogo offline do navegador Google Chrome, adicionando mecânicas e recursos extras.

### Mecânicas do Jogo

O jogo segue a premissa clássica do Dino Runner, onde o jogador controla um dinossauro que deve:

- **Correr automaticamente** pela tela enquanto obstáculos aparecem
- **Pular** para evitar cactos e obstáculos terrestres
- **Abaixar** para desviar de pássaros que voam em diferentes alturas
- **Acumular pontos** conforme a distância percorrida aumenta
- **Sobreviver o máximo possível** para bater o recorde

### Diferenciais Implementados

Esta versão conta com recursos adicionais que expandem a experiência do jogo original:

- **Modo Alternado (Dia/Noite)**: A cada 300 pontos, o jogo alterna entre modo claro e escuro, invertendo completamente as cores do cenário, personagens e obstáculos
- **Power-ups Coletáveis**: 
  - **Escudo**: Protege o dinossauro de uma colisão
  - **Martelo**: Permite destruir obstáculos terrestres ao colidir
- **Efeitos Sonoros**: Sons para pulos, pontuação e game over
- **Sistema de Estatísticas**: Rastreamento de pontuação máxima e número de mortes
- **Dificuldade Progressiva**: Velocidade do jogo aumenta gradualmente a cada 100 pontos

## Lógica e Estrutura do Jogo

O projeto segue uma arquitetura orientada a objetos bem organizada:

### Sistema de Componentes

- **Dinosaur**: Gerencia estados do jogador (correndo, pulando, abaixado) e power-ups ativos
- **ObstaclesManager**: Spawna e controla cactos e pássaros de forma randômica
- **PowerUpManager**: Gerencia aparição e coleta de power-ups
- **CloudManager**: Adiciona nuvens decorativas ao cenário

### Loop Principal

1. **Eventos**: Captura inputs do teclado (setas, espaço, WASD)
2. **Update**: Atualiza posições, detecta colisões e calcula pontuação
3. **Draw**: Renderiza todos os elementos na tela
4. **Clock**: Mantém o jogo rodando a 30 FPS

### Sistema de Colisões

O jogo utiliza retângulos (pygame.Rect) para detecção precisa de colisões entre:
- Dinossauro e obstáculos (game over ou uso de power-up)
- Dinossauro e power-ups (ativação de habilidades)

## Como Rodar o Projeto

### Pré-requisitos

- Python 3.7 ou superior instalado
- pip (gerenciador de pacotes do Python)

### Instalação

1. **Clone o repositório**:
```bash
git clone <url-do-repositorio>
cd dino-runner
```

2. **Instale as dependências**:
```bash
pip install -r requirements.txt
```

3. **Execute o jogo**:
```bash
python main.py
```

## Controles

| Tecla | Ação |
|-------|------|
| `↑` / `Espaço` / `W` | Pular |
| `↓` / `S` | Abaixar |
| `Qualquer tecla` | Iniciar/Reiniciar jogo |

## 📁 Estrutura do Projeto

```
dino_runner/
│
├── assets/                      # Recursos do jogo
│   ├── Dino/                    # Sprites do dinossauro
│   ├── Cactus/                  # Sprites dos cactos
│   ├── Bird/                    # Sprites dos pássaros
│   ├── Other/                   # Outros recursos (nuvens, power-ups, etc)
│   └── sons/                    # Efeitos sonoros
│
├── components/                  # Componentes do jogo
│   ├── dinosaur.py              # Classe do personagem jogável
│   ├── game.py                  # Loop principal e gerenciamento do jogo
│   │
│   ├── obstacles/               # Sistema de obstáculos
│   │   ├── obstacles.py         # Classe base de obstáculos
│   │   ├── cactus.py            # Implementação dos cactos
│   │   ├── bird.py              # Implementação dos pássaros
│   │   └── obstacles_manager.py # Gerenciador de obstáculos
│   │
│   ├── power_ups/               # Sistema de power-ups
│   │   ├── power_up.py          # Classe base de power-ups
│   │   ├── shield.py            # Implementação do escudo
│   │   ├── hammer.py            # Implementação do martelo
│   │   └── power_up_manager.py  # Gerenciador de power-ups
│   │
│   └── clouds/                  # Sistema de nuvens decorativas
│       ├── cloud.py             # Classe de nuvem individual
│       └── clouds_magager.py    # Gerenciador de nuvens
│
├── utils/                       # Utilitários
│   └── constants.py             # Constantes globais e assets
│
├── main.py                      # Ponto de entrada do jogo
└── requirements.txt             # Dependências do projeto
```

## 🛠️ Tecnologias Utilizadas

- **Python 3.7+**: Linguagem principal
- **Pygame**: Biblioteca para desenvolvimento de jogos 2D
- **Random**: Geração de elementos aleatórios
- **OS**: Manipulação de caminhos de arquivos

> Este projeto foi desenvolvido para fins educacionais como parte do curso de admissão da Jala University, conquistando o primeiro lugar no sistema de pontuação de projetos.
