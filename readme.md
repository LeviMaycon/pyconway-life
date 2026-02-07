# Conway's Game of Life 🎮

Uma implementação otimizada do clássico **Jogo da Vida de Conway** em Python com Tkinter.

![Version](https://img.shields.io/badge/version-2.0-blue)
![Python](https://img.shields.io/badge/python-3.8+-green)
![License](https://img.shields.io/badge/license-MIT-orange)

---

<img width="1135" height="666" alt="image" src="https://github.com/user-attachments/assets/acf6b093-7670-4d24-b786-bacd67c25dd6" />


## 📖 Sobre o Projeto

Implementação do autômato celular desenvolvido pelo matemático **John Horton Conway** em 1970. Este projeto foi criado como ferramenta de estudos para compreender:

- Programação Orientada a Objetos (POO)
- Estruturas de dados matriciais
- Algoritmos de simulação e otimização
- Renderização eficiente com Tkinter
- Sistemas complexos emergentes

---

## Regras do Jogo da Vida

O comportamento de cada célula é determinado por quatro regras simples:

1. **Solidão**: Células vivas com menos de 2 vizinhos morrem
2. **Sobrevivência**: Células vivas com 2 ou 3 vizinhos sobrevivem
3. **Superpopulação**: Células vivas com mais de 3 vizinhos morrem
4. **Reprodução**: Células mortas com exatamente 3 vizinhos renascem

---

## Funcionalidades

- ✅ Grid adaptativo baseado no tamanho da tela
- ✅ Sistema de renderização otimizado (apenas mudanças)
- ✅ Geração aleatória de padrões iniciais
- ✅ Biblioteca com padrões clássicos
- ✅ Performance otimizada para 60+ FPS
- ✅ Linhas de grade visuais opcionais
- ✅ Células com atributos individuais

---

## Como Usar

### Pré-requisitos
```bash
Python 3.8+
tkinter (geralmente incluído com Python)
```

### Instalação e Execução
```bash
# Clone o repositório
git clone https://github.com/LeviMaycon/pyconway-life.git

# Entre no diretório
cd conway-game-of-life

# Execute o jogo
python game.py
```

ou
```bash
py game.py
```

---

## Controles

| Tecla | Ação |
|-------|------|
| `ESC` | Fechar aplicação |

---

## Padrões Disponíveis

| Padrão | Descrição | Tipo |
|--------|-----------|------|
| `glider` | Planador que se move diagonalmente | Móvel |
| `blinker` | Oscilador simples de período 2 | Oscilador |
| `block` | Estrutura estática | Still Life |
| `toad` | Oscilador de período 2 | Oscilador |
| `spaceship` | Nave espacial leve (LWSS) | Móvel |
| `beacon` | Oscilador de período 2 | Oscilador |
| `pulsar` | Grande oscilador de período 3 | Oscilador |
| `pentadecathlon` | Oscilador de período 15 | Oscilador |
| `glider_gun` | Gerador contínuo de gliders | Gerador |

---

## Configuração

### Usar Padrões Específicos

Modifique no método `__init__` da classe `FullScreenGrid`:
```python
# Padrão aleatório (padrão)
self.create_random_pattern(density=0.3)

# Ou use padrões específicos
self.load_pattern('glider', 10, 10)
self.load_pattern('pulsar', 50, 50)
self.load_pattern('glider_gun', 20, 30)
```

### Ajustar Velocidade

Modifique o valor em `self.root.after()`:
```python
def loop(self):
    self.next_generation()
    self.root.after(100, self.loop)  # 100ms = ~10 FPS
```

Valores menores = mais rápido (ex: 50ms = ~20 FPS)

### Ajustar Tamanho das Células
```python
grid = FullScreenGrid(cell_size=10)  # Padrão: 10 pixels
```

### Ajustar Densidade Inicial
```python
self.create_random_pattern(density=0.3)  # 30% de células vivas
```

---

## 🔧 Parâmetros Configuráveis

| Parâmetro | Tipo | Padrão | Descrição |
|-----------|------|--------|-----------|
| `cell_size` | int | 10 | Tamanho de cada célula em pixels |
| `density` | float | 0.3 | Densidade inicial (0.0 a 1.0) |
| `after_delay` | int | 100 | Intervalo entre gerações (ms) |

---

## Otimizações Implementadas

- **`__slots__`**: Reduz uso de memória nas células
- **Renderização Diferencial**: Atualiza apenas células modificadas
- **Dicionário Esparso**: Armazena apenas células vivas
- **Matriz 2D**: Cálculo eficiente de vizinhos
- **Canvas Otimizado**: Sem bordas ou highlights desnecessários

---

## Estrutura do Código
```
├── Cell
│   └── Representa uma célula individual
│       ├── row: int
│       ├── col: int
│       └── alive: bool
│
└── FullScreenGrid
    └── Gerencia grid, lógica e renderização
        ├── __init__()
        ├── draw_grid_lines()
        ├── create_random_pattern()
        ├── load_pattern()
        ├── count_neighbors()
        ├── next_generation()
        ├── loop()
        └── run()
```

---

## Aplicações Educacionais

- Estudo de **autômatos celulares**
- Compreensão de **sistemas complexos emergentes**
- Teoria de **jogos combinatórios**
- Conceitos de **computação universal**
- Análise de **padrões auto-organizados**

---

## Próximas Expansões

- [ ] Interação via mouse (desenhar células)
- [ ] Pause/Resume da simulação
- [ ] Contador de gerações e população
- [ ] Estatísticas em tempo real
- [ ] Exportar/Importar padrões (.rle, .cells)
- [ ] Diferentes regras (Seeds, HighLife, Day & Night)
- [ ] Histórico de estados (voltar gerações)
- [ ] Modo tela cheia
- [ ] Cores personalizáveis

---

## 🎓 Referências

- [Conway's Game of Life - Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)
- [LifeWiki - Enciclopédia de Padrões](https://conwaylife.com/wiki/)
- [The Game of Life - Documentário](https://www.youtube.com/watch?v=C2vgICfQawE)

---

## Autor

**Levi Maycon**

- Data: 02/07/2026
- LinkedIn: [LeviMaycon](https://www.linkedin.com/in/levimaycon/)
- GitHub: [@LeviMaycon](https://github.com/LeviMaycon)

---

## Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer um Fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/NovaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/NovaFeature`)
5. Abrir um Pull Request

---

## Mostre seu Apoio

Se este projeto te ajudou, considere dar uma ⭐!

---

<div align="center">
  <sub>Desenvolvido com ❤️ por Levi Maycon</sub>
</div>
