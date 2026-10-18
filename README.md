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

## Modo História

Você enfrenta 10 personagens do bairro, de boteco em boteco, até a Grande Final contra o Mestre Sete Tacos. O adversário é controlado pelo computador: ele simula as tacadas antes de jogar e erra mais ou menos conforme a mira, a força, o efeito e os nervos de cada personagem.

| Local | Capítulos |
|---|---|
| Boteco do Zé | Seu Zé do Balcão (Bola 8), Tião Marreta (Bola 8) |
| Bar da Esquina | Dona Cida Tabelinha (Bola da Vez), Rafa Mão Leve (Bola 8) |
| Clube Recreativo | Marquinho Efeito (Garrafinha), Professora Lurdes (Bola da Vez) |
| Torneio do Bairro | Bia Relâmpago (Bola 8), Coronel Bigode (Bola 8) |
| Grande Final | Dona Neide, Rainha da Caçapa (Garrafinha), Mestre Sete Tacos (Bola 8) |

Cada capítulo tem 3 estrelas: vencer, não cometer falta e vencer dentro de um número de tacadas.

## Noite de Apostas

Modo roguelike: você começa com 100 fichas e enfrenta 7 mesas. Em cada mesa escolhe um entre 3 adversários sorteados, cada um com uma cotação (quanto mais forte, mais paga), e decide quanto apostar. Depois de cada vitória escolhe uma vantagem (Giz azul, Rodada por conta, Moeda viciada, Seguro do Zé, Caderninho ou Fiado). Ficou sem fichas, a noite acaba. A última mesa é a aposta final contra o Mestre Sete Tacos. As fichas são do jogo e não valem dinheiro.

## Álbum de figurinhas

Cada personagem vencido vira uma figurinha no álbum, com número, raridade (comum, rara ou lendária), atributos e frase. Com as 3 estrelas do capítulo, a figurinha fica brilhante. Dá para compartilhar a figurinha como imagem no WhatsApp.

## Torcida

A torcida não aparece na tela, mas comemora, faz "uuuh" e vaia as jogadas com sons gerados no próprio celular. O botão 📣 manda reações (👏 🔥 😱 😂 💪 🍺 🎉 😬) que aparecem na mesa. No online, todo mundo vê as reações, inclusive quem está esperando a vez. A torcida pode ser desligada no menu ☰.

## Músicas

O jogo tem 4 trilhas originais geradas no próprio celular, todas em domínio público (CC0 1.0):

| Faixa | Estilo |
|---|---|
| Samba do Taco | Samba |
| Bossa da Madrugada | Bossa nova |
| Forró da Caçapa | Baião |
| Lo-fi do Feltro | Lo-fi |

As faixas tocam em ordem aleatória. O botão ♪ na tela inicial (ou *Música* no menu ☰) troca a faixa, muda o volume e permite tocar uma música do próprio celular.

### Adicionar músicas Creative Commons

1. Crie a pasta `musicas/` no repositório e coloque o arquivo (`.mp3` ou `.ogg`).
2. No bloco de configuração do `index.html`, adicione a faixa em `musica.arquivos`, com os créditos que a licença pede:

```json
"arquivos": [
  { "id": "minha-faixa", "titulo": "Nome da música", "estilo": "Samba", "autor": "Nome do artista",
    "licenca": "CC BY 4.0", "link": "https://creativecommons.org/licenses/by/4.0/deed.pt_BR",
    "url": "musicas/minha-faixa.mp3" }
]
```

Os créditos aparecem na lista de músicas do jogo. Use só faixas cuja licença permita esse uso (CC0, CC BY ou CC BY-SA, por exemplo) e confira se ela permite uso comercial, caso o jogo um dia tenha anúncio ou venda.

## Outros recursos

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
| `sinuca-config.json` | Configuração do jogo: mesa, física, temas, modos, regras, personagens, história, torcida, músicas, cronômetro, online e WhatsApp. É a mesma que está dentro do `index.html` no bloco `<script id="cfg">`. |
| `peerjs.min.js` | Biblioteca [PeerJS](https://peerjs.com) para a conexão online entre celulares (WebRTC). |
| `sw.js`, `manifest.webmanifest`, `icon-*.png` | Arquivos que transformam o site em app instalável e permitem jogar sem internet. |

## Mudar regras ou aparência

Edite o bloco `<script type="application/json" id="cfg">` dentro do `index.html`. Exemplos:

- `modos[].opcoes.numerosPorJogador`: quantos números cada um sorteia na Garrafinha.
- `cronometro.tempoPorTacada.opcoes`: tempos disponíveis por tacada.
- `temas`: cores de cada tema.
- `online.servidor`: endereço de um servidor PeerJS próprio (deixe `null` para usar o público).
- `personagens`: nome, frase, falas, atributos e visual de cada personagem.
- `historia.capitulos`: adversário, modo de jogo, diálogos e meta de tacadas de cada capítulo.
- `cpu`: quanto o computador demora para pensar e o tamanho do erro dele.
- `torcida.gritos` e `torcida.reacoes`: o que a torcida grita e quais emojis aparecem.
- `musica`: volume inicial, faixas e arquivos Creative Commons.

Se mudar o `index.html`, troque também o `CACHE` em `sw.js` (por exemplo de `sinuca-v3` para `sinuca-v4`) para os celulares baixarem a versão nova.

## Como o online funciona

O celular de quem cria a sala (anfitrião) calcula a física e manda o estado da mesa para os outros pelo WebRTC. A conexão inicial usa o servidor público gratuito do PeerJS. O anfitrião precisa ficar com o jogo aberto durante a partida.

## Ambientes

A cada partida o jogo sorteia um ambiente em volta da mesa, com piso e luz central: carpete vinho, assoalho de madeira, piso quadriculado, cimento queimado, carpete azul, ladrilho hidráulico ou taco em espinha. As cores da mesa também mudam (fora do Modo História, que usa as cores de cada local). A lista fica em `ambientes` na configuração.

## Tela inicial e computador

A tela inicial mostra só as opções principais. Em *Mais opções* ficam todas, e o 📌 fixa qualquer uma na tela inicial. No computador, a partida usa uma coluna lateral com jogadores, status e controles, e a mesa ocupa o resto da tela.

## Meu rosto

Em *Meu rosto*, na tela inicial, você tira uma foto com a câmera, escolhe uma da galeria ou sorteia um rosto de pessoa que não existe. A foto fica só no aparelho e aparece no Modo História e nas apostas.

## Créditos

- Rostos dos personagens: imagens geradas pelo [This Person Does Not Exist](https://thispersondoesnotexist.com) (StyleGAN2), obtidas no repositório [gecid-aia/ai-faces](https://github.com/gecid-aia/ai-faces), licença [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/). Pasta `faces/` (personagens e `sorteio-*.jpg`), recortadas e reduzidas.
- Trilhas: originais do jogo, [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.pt_BR).
- Conexão online: [PeerJS](https://peerjs.com), licença MIT.
