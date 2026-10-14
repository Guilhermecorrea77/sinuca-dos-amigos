# 🎱 Sinuca dos Amigos

Jogo de sinuca para celular, feito para jogar com a turma, no mesmo aparelho ou online, cada um no seu celular.

**Jogar:** https://guilhermecorrea77.github.io/sinuca-dos-amigos/

## Modos de jogo

| Jogo | Jogadores | Como funciona |
|---|---|---|
| **Bola 8** | 2, 4 ou 6 | Lisas contra listradas. Com 4 ou 6, Equipe A contra Equipe B. |
| **Garrafinha** | 2 a 7 | Cada um sorteia números secretos. Derrube as bolas dos outros e proteja as suas. O último com bola na mesa vence. |
| **Bola da Vez** | 2 a 8 | Toque sempre primeiro na menor bola. Cada bola vale o próprio número. |
| **Treino** | 1 | Limpe a mesa com o menor número de tacadas. |

## Recursos

- **Online:** crie uma sala, mande o convite pelo WhatsApp e cada amigo joga no próprio celular.
- **Cara ou coroa** para decidir quem começa (sorteio com 3 ou mais jogadores).
- **Mapa da bola:** escolha onde bater na branca para ela correr mais, parar ou voltar.
- **Cronômetro** de partida e tempo por tacada (30, 45 ou 60 s).
- **Placar da turma** com vitórias, jogos e pontos, enviado pelo WhatsApp.
- 6 temas de mesa, mesa em pé ou deitada, funciona sem internet depois de instalado.

## Instalar no celular

Abra o link do jogo e:

- **Android (Chrome):** menu ⋮ → *Instalar app* ou *Adicionar à tela inicial*.
- **iPhone (Safari):** *Compartilhar* → *Adicionar à Tela de Início*.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | O jogo inteiro (HTML, CSS e JavaScript num arquivo só). |
| `sinuca-config.json` | Configuração do jogo: mesa, física, temas, modos, regras, cronômetro, online e WhatsApp. É a mesma que está dentro do `index.html` no bloco `<script id="cfg">`. |
| `peerjs.min.js` | Biblioteca [PeerJS](https://peerjs.com) para a conexão online entre celulares (WebRTC). |
| `sw.js`, `manifest.webmanifest`, `icon-*.png` | Arquivos que transformam o site em app instalável e permitem jogar sem internet. |

## Mudar regras ou aparência

Edite o bloco `<script type="application/json" id="cfg">` dentro do `index.html`. Exemplos:

- `modos[].opcoes.numerosPorJogador`: quantos números cada um sorteia na Garrafinha.
- `cronometro.tempoPorTacada.opcoes`: tempos disponíveis por tacada.
- `temas`: cores de cada tema.
- `online.servidor`: endereço de um servidor PeerJS próprio (deixe `null` para usar o público).

Se mudar o `index.html`, troque também o `CACHE` em `sw.js` (por exemplo de `sinuca-v2` para `sinuca-v3`) para os celulares baixarem a versão nova.

## Como o online funciona

O celular de quem cria a sala (anfitrião) calcula a física e manda o estado da mesa para os outros pelo WebRTC. A conexão inicial usa o servidor público gratuito do PeerJS. O anfitrião precisa ficar com o jogo aberto durante a partida.
