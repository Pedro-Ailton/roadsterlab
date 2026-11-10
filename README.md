# Roadster Lab — Simulador Físico do Tesla Roadster
 
Projeto em equipe que apresenta o Tesla Roadster e inclui um **simulador 3D no navegador**, em que a física do carro (arrasto, empuxo, tração, rotação e loop) é calculada em tempo real.
 
**Demo online:** https://pedro-ailton.github.io/roadsterlab/
 
<!-- Adicione aqui um print ou GIF do simulador, por exemplo:
![Simulador](imagens/simulador.png) -->
 
## O que tem no projeto
 
| Arquivo | O que é |
|---|---|
| `index.html` | Página de apresentação do projeto, desenvolvida por Paulo Santos. LinkedIn: linkedin.com/in/paulo-santos-1a76863b5/ |
| `simulador.html` | Simulador 3D interativo do carro, desenvolvido por Pedro Ailton Feitosa, integrado à página de apresentação. |
 
## Simulador
 
O simulador desenha o carro em 3D e calcula a física a cada quadro. Ele exibe um gráfico de velocidade × tempo e inclui um tutorial inicial.
 
**Controles:** botões de acelerar e frear na tela; teclas ↑ para decolar, ↓ para pousar e Tab para avançar.
**Pistas:** reta, com obstáculos e rampa.
**Painel:** velocidade, altitude, gás restante, estado da sucção e dos propulsores.
**Objetivo:** simular de forma lúdica o conceito do Tesla Roadster apresentado em 2026, em que o carro usa propulsores de gás frio para decolar e pousar. No simulador, você acelera, decola, administra o gás disponível e supera obstáculos e rampas, vendo em tempo real como a física (arrasto, empuxo e tração) afeta o carro.

> Projeto educacional e independente, sem vínculo com a Tesla. Os valores usados são simplificados e servem para ilustrar os conceitos, não para reproduzir medidas oficiais.

 
### Física implementada
 
- **Pressão dinâmica e arrasto:** q = ½·ρ·A·v² (ρ = 1,225 kg/m³) e F_arrasto = C_d·q.
- **Força descendente (downforce):** proporcional à pressão dinâmica, aplicada com o carro no solo.
- **Empuxo (gás frio):** F = ṁ·Isp·g₀, com g₀ = 9,80665 m/s².
- **Tração do motor:** limitada pelo atrito, min(F_motor·(1 − v/V_máx), μ·N).
- **Resistência ao rolamento:** 0,015·N.
- **Rotação:** torque τ = r·F, com momento de inércia I = m(L² + H²)/12.
- **Loop (R = 9 m):** velocidade mínima de entrada √(5·g·R) e força normal N = v²/R + g·cos θ.
- **Obstáculos:** velocidade vertical necessária √(2·g·h).
## Tecnologias
 
- **HTML, CSS e JavaScript** puros, com layout responsivo.
- **[Three.js](https://threejs.org/) 0.169** (via CDN) para renderização 3D com WebGL, sombras, reflexos de ambiente e materiais físicos.
- **Canvas 2D** para gerar as texturas da pista, do terreno e do céu e para desenhar o gráfico de velocidade.
- **Google Fonts** (Space Grotesk e JetBrains Mono).
- **GitHub Pages** para publicação.
## Como rodar
 
O projeto não precisa de instalação. Há duas opções:
 
1. Acesse a [demo online](https://pedro-ailton.github.io/roadsterlab/).
2. Ou clone o repositório e abra o `index.html` no navegador. Para o simulador carregar o Three.js, é necessário estar conectado à internet.
```bash
git clone https://github.com/Pedro-Ailton/roadsterlab.git
cd roadsterlab
```
 
## Equipe
 
- Pedro Ailton Feitosa — simulador (`simulador.html`) e integração das páginas.
- Paulo Santos — página de apresentação (`index.html`).
## Aprendizados e próximos passos
 
- Aplicar fórmulas de física em código e ajustar parâmetros até o comportamento ficar realista.
- Possíveis melhorias: separar o código em arquivos de CSS e JS, adicionar mais fases e carregar o Three.js localmente para funcionar sem internet.
