# 🍺 Brewteco — Planejamento Semanal de Produção

Dashboard web para planejamento semanal da cozinha central. Funciona 100% no navegador — sem servidor, sem banco de dados, sem custo.

## Como usar

### 1. Definir a semana
Selecione qualquer dia da semana desejada e clique em **Definir semana**. O sistema ajusta automaticamente para segunda-feira.

### 2. Carregar os CSVs
Para cada dia, exporte o CSV do dashboard de vendas:
> Dashboard Brewteco → **Busca de Produtos** → filtrar período (ex: somente segunda-feira) → **⬇ CSV**

Arraste ou clique no card do dia correspondente. Você pode carregar de 1 a 6 dias — o sistema calcula a projeção com os dados disponíveis.

### 3. Ajustar a margem de segurança
Use o slider para configurar a margem (padrão: **+30%**). Isso é aplicado sobre a média diária real para calcular as metas.

### 4. Ler os resultados
| Coluna | Significado |
|---|---|
| Real acum. | Total vendido nos dias com dados |
| Média/dia | Média real (apenas dias carregados) |
| Meta diária | Média × (1 + margem), arredondada para cima |
| Projeção semana | Meta diária × 6 dias úteis |
| **Meta sábado (×2)** | Meta diária × 2 — cobre sábado **e** domingo |

### Regra do domingo
A equipe de produção **folga no domingo**. A produção de **sábado cobre os dois dias** (sábado + domingo). Por isso a coluna "Meta sábado" é sempre o dobro da meta diária.

---

## Recursos

- ✅ Upload de 1 a 6 CSVs (um por dia útil)
- ✅ Projeção automática dos dias sem dados
- ✅ Margem de segurança ajustável (0% a 80%)
- ✅ Meta sábado = meta diária × 2 (cobre domingo)
- ✅ Classificação dinâmica por demanda (Alta / Média / Baixa / Pontual)
- ✅ Filtros por perfil de demanda
- ✅ Gráficos: Top 15 projeção + distribuição por perfil
- ✅ Exportar CSV Completo ou CSV Romaneio
- ✅ Imprimir romaneio (otimizado para impressão)
- ✅ Histórico das últimas 12 semanas (salvo no navegador)

---

## Hospedar no GitHub Pages (grátis)

1. Crie um repositório no GitHub (ex: `brewteco-producao`)
2. Faça upload do arquivo `index.html`
3. Vá em **Settings → Pages → Source → main / (root)**
4. Aguarde ~1 minuto
5. Acesse em: `https://SEU-USUARIO.github.io/brewteco-producao/`

---

## Estrutura dos arquivos

```
brewteco-producao/
├── index.html   ← o dashboard completo (único arquivo necessário)
└── README.md    ← este guia
```

O dashboard é um único arquivo HTML autocontido. Todas as bibliotecas (PapaParse, Chart.js) são carregadas via CDN.

---

## Dicas de uso

- **Fim de semana puxa mais**: sexta e sábado costumam ter 30–40% mais saída. Considere aumentar a margem para esses dias.
- **Acumule semanas**: o histórico (salvo no navegador) permite comparar semanas e identificar tendências.
- **CSV Romaneio**: versão enxuta para passar para a equipe de produção — só o essencial.
- O histórico é salvo no `localStorage` do navegador — limpar os dados do site apaga o histórico.

---

Desenvolvido para a cozinha central Brewteco Botafogo.
