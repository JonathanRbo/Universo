# 🌌 Universo Interativo — Simulação Gravitacional de Partículas

Uma experiência visual imersiva de simulação de partículas com física gravitacional em tempo real, construída inteiramente com HTML5 Canvas e JavaScript puro — sem dependências externas.

![Status](https://img.shields.io/badge/status-completo-brightgreen)
![Licença](https://img.shields.io/badge/licença-MIT-blue)
![Dependências](https://img.shields.io/badge/dependências-zero-orange)

---

## ✨ Visão Geral

O projeto simula um universo de partículas que reagem à posição e interação do mouse em tempo real. Cada partícula possui velocidade, cor, energia e tamanho próprios, criando composições visuais orgânicas e imprevisíveis. O sistema inclui nebulosas volumétricas, campo estelar cintilante, conexões dinâmicas e múltiplos modos de física.

---

## 🎮 Como Usar

1. Abra o arquivo `index.html` no navegador
2. Mova o mouse pela tela — as partículas reagem ao cursor
3. **Segure o clique** para triplicar a força gravitacional
4. Use os botões na barra inferior ou atalhos de teclado para trocar modos e ações

---

## 🕹️ Controles

### Mouse / Touch

| Ação | Efeito |
|------|--------|
| Mover o mouse | Aplica força gravitacional nas partículas próximas |
| Segurar clique | Multiplica a gravidade por 3x |
| Touch (mobile) | Mesma interação do mouse |

### Teclado

| Tecla | Ação |
|-------|------|
| `1` | Modo Atrair |
| `2` | Modo Repelir |
| `3` | Modo Orbitar |
| `4` | Modo Vórtex |
| `N` | Gerar Nebulosa |
| `B` | Big Bang |
| `C` | Abrir/fechar painel de configurações |

### Barra de Controles (UI)

- **Atrair** — partículas são puxadas em direção ao cursor
- **Repelir** — partículas fogem do cursor com força amplificada
- **Orbitar** — partículas entram em órbita circular ao redor do cursor
- **Vórtex** — cria um redemoinho espiral que puxa e gira simultaneamente
- **Nebulosa** — gera uma nuvem cósmica com camadas de cor + 100 novas partículas
- **Big Bang** — destrói e recria todas as partículas em explosão a partir do centro
- **Config** — abre o painel lateral de ajustes

---

## ⚙️ Configurações Ajustáveis

O painel lateral permite alterar em tempo real:

| Parâmetro | Faixa | Padrão | Descrição |
|-----------|-------|--------|-----------|
| Partículas | 500–8000 | 3000 | Quantidade total de partículas na simulação |
| Gravidade | 0.1–5.0 | 1.0 | Intensidade da força aplicada pelo cursor |
| Raio de Influência | 50–500px | 200 | Distância máxima de alcance da força |
| Fricção | 0.90–1.00 | 0.98 | Desaceleração das partículas (1.0 = sem fricção) |
| Conexões | 0–200px | 80 | Distância para desenhar linhas entre partículas próximas |
| Brilho Rastro | 0.01–0.30 | 0.06 | Opacidade do fade (menor = rastros mais longos) |
| Tamanho Base | 0.5–6.0 | 2.5 | Tamanho base de cada partícula |

---

## 🎨 Sistema Visual

### Partículas
- Cada partícula possui cor, velocidade, energia e transparência individuais
- Partículas energizadas ganham brilho (glow) radial proporcional à energia
- O tamanho aumenta dinamicamente com velocidade e energia

### Nebulosas
- Compostas por 5 camadas independentes com offset, rotação e cor próprios
- Expandem organicamente até o raio máximo e depois desvanecem lentamente
- Cada nebulosa injeta 100 novas partículas coloridas na simulação

### Campo Estelar
- 400 estrelas de fundo com brilho cintilante (twinkle) via senóide
- Velocidades de cintilação individuais para cada estrela

### Conexões
- Linhas semi-transparentes entre partículas próximas ao cursor
- Cor calculada pela média entre as duas partículas conectadas
- Otimizado: apenas partículas num raio de 200px do cursor são verificadas

### Paletas de Cores
| Paleta | Cores |
|--------|-------|
| Cyan/Blue | Azuis e cianos brilhantes |
| Pink/Magenta | Rosas e magentas |
| Gold/Orange | Dourados e laranjas |
| Green | Verdes e turquesas |
| Purple | Roxos e violetas |

---

## 📊 HUD (Heads-Up Display)

O canto superior direito exibe em tempo real:
- **Partículas** — total ativo na simulação
- **FPS** — frames por segundo
- **Modo** — modo de interação atual
- **Energia** — soma total de velocidades (indica "agitação" do sistema)

---

## 🏗️ Arquitetura

```
universo/
└── index.html      # Arquivo único com HTML + CSS + JS
```

### Classes Principais

- **`Particle`** — entidade com posição, velocidade, cor, energia e métodos `update()` / `draw()`
- **`Nebula`** — nuvem volumétrica com 5 camadas, expansão e fade orgânico

### Loop Principal (`animate()`)

```
1. Aplica trail fade (retângulo semi-transparente)
2. Desenha campo estelar
3. Atualiza e renderiza nebulosas
4. Atualiza física e renderiza partículas
5. Desenha conexões entre partículas próximas
6. Desenha visualização do campo do mouse
7. Atualiza contador de FPS e HUD
```

---

## 🖥️ Compatibilidade

- Chrome, Firefox, Edge, Safari (versões modernas)
- Suporte a dispositivos touch (mobile/tablet)
- Responsivo — adapta layout e fontes para telas menores
- Cursor personalizado com fallback em mobile

---

## 📄 Licença

MIT — use, modifique e distribua livremente.
