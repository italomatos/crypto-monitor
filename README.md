# Crypto Monitor 📈

Monitor de cotações de criptomoedas em tempo real usando a API CoinGecko.

## Funcionalidades

- ✅ Visualização de cotações em tempo real (BTC, ETH, SOL, ADA, BNB, XRP)
- ✅ Seleção de moeda (Real BRL ou Dólar USD)
- ✅ Seleção de período de variação (1D, 5D, 1 Semana, 1 Mês, 6 Meses, 1 Ano)
- ✅ Gráficos interativos com Chart.js
- ✅ Design responsivo com Bootstrap 5
- ✅ Atualização manual via botão de refresh
- ✅ Cache inteligente para evitar rate limiting

## Como Usar

1. Abra o arquivo `index.html` no navegador
2. Selecione a moeda desejada (Real ou Dólar)
3. Escolha o período de variação no header
4. Use o botão de refresh (canto inferior direito) para atualizar

## ⚠️ IMPORTANTE: Limitações da API Gratuita

A API gratuita do CoinGecko tem **limites muito restritos**:
- **10-50 requisições por minuto**
- **Bloqueio temporário (erro 429) ao exceder**

### Se você ver o erro "429 Too Many Requests":

1. **PARE de tentar atualizar imediatamente**
2. **Aguarde 2-3 minutos** sem fazer nada
3. **Feche e abra o navegador** novamente
4. Use o botão de refresh **com moderação**

⚠️ **Continuar tentando atualizar só piora o bloqueio!**

## Recursos Implementados

### Sistema de Cache
- Cache de 45 segundos entre requisições
- Previne requisições desnecessárias
- Respeita limites da API

### Retry Inteligente
- Até 3 tentativas com delay progressivo (5s, 10s, 15s)
- Tratamento específico para erro 429
- Mensagens de erro claras

### Atualização Manual
- Atualização automática **desabilitada** para evitar rate limiting
- Use o botão de refresh para atualizar manualmente
- Respeite o tempo de cache

## Tecnologias Utilizadas

- HTML5
- CSS3
- JavaScript (ES6+)
- Bootstrap 5
- Chart.js
- CoinGecko API

## Estrutura do Projeto

```
crypto-monitor/
├── index.html          # Arquivo principal (tudo em um arquivo)
├── README.md           # Este arquivo
└── LEIA-ME.txt        # Informações sobre erro 429
```

## Alternativas ao Erro 429

Se você está enfrentando muitos problemas com o limite da API:

### Opção 1: API Key Paga (Recomendado)
- https://www.coingecko.com/en/api/pricing
- Planos a partir de $129/mês
- Limites muito maiores

### Opção 2: Outras APIs de Criptomoedas
- CoinMarketCap API
- Binance API
- CryptoCompare API
- Messari API

### Opção 3: Aguardar e Usar com Moderação
- Use apenas quando necessário
- Não teste continuamente
- Respeite o cache de 45 segundos

## Desenvolvido por

Este projeto foi criado como uma demonstração de integração com API de criptomoedas usando tecnologias web modernas.

## Licença

Livre para uso pessoal e educacional.
