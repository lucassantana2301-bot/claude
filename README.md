# Corrente

**Rastreador de hábitos pelo método da corrente: marque cada dia em que cumpriu o hábito e tente não quebrar a sequência.**

![HTML](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Sem dependências](https://img.shields.io/badge/depend%C3%AAncias-0-10b981)

## O que faz

- **Hábitos ilimitados**, cada um com uma faixa dos últimos 60 dias para marcar e desmarcar.
- **Corrente atual e recorde** por hábito. Enquanto o dia de hoje não termina, a corrente de ontem continua valendo: não marcar logo cedo não zera a sequência.
- **Resumo do dia**: quantos hábitos existem, quantos foram feitos hoje e a maior corrente ativa.
- **Remoção com confirmação** em dois cliques, para não apagar um hábito por engano.
- **Armazenamento local**: os dados ficam no `localStorage` do navegador, sem conta e sem servidor. Quando roda dentro de um ambiente com armazenamento compartilhado disponível, usa esse armazenamento com sincronização em tempo real.

## Como usar

É um arquivo HTML único, sem build:

```bash
git clone https://github.com/lucassantana2301-bot/claude.git corrente
cd corrente
npx serve .        # ou abra o index.html direto no navegador
```

## Decisões técnicas

- **JavaScript puro**, sem framework nem bundler: abre em qualquer navegador e pode ser hospedado em qualquer CDN estática (GitHub Pages, Vercel, Netlify).
- **Datas como chave `AAAA-MM-DD` no fuso local**, para que "hoje" seja o dia do usuário, e diferença entre dias arredondada para não quebrar a corrente na troca do horário de verão.
- **Camada de armazenamento trocável** (`initLocalStore` / `initDbStore`): a interface não sabe onde os dados ficam.
- **Nomes de hábito inseridos como texto** (`textContent`), nunca como HTML, evitando injeção de script.

## Autor

Lucas Santana · [LinkedIn](https://www.linkedin.com/in/lucas-santana-45316232a/)
