---
marp: true
title: Titulo Ilustrativo
author: Ana Barbosa
keywords: marp, theme
theme: barbosa
paginate: true
_paginate: false
class: style_a
---
<!-- _class: title -->

# Exemplo de slides Marp — "Barbosa"
Autor: Ana Barbosa
Tema: barbosa

---

# Sumário
- Slides longos
- Blocos de código
- Dicas de apresentação
- Exemplos práticos

---
<!-- _class: style_b -->

# Slide longo: Visão geral
Este slide demonstra conteúdo extenso, ideal para quando precisa explicar conceitos com detalhes:
- Contexto e motivação
- Requisitos e restrições
- Abordagem proposta
- Exemplos práticos
- Comparações com alternativas
- Conclusões e próximos passos

Detalhamento:
1. Comece com o problema.
2. Mostre soluções conhecidas.
3. Aponte trade-offs.
4. Explique a solução escolhida passo a passo.
5. Mostre código e resultados.

---

# Slide longo: Uso em projeto real
- Cenário: aplicação web com backend em Node.js
- Requisitos: performance, escalabilidade, observabilidade
- Estratégia:
  - Microservices com filas para tarefas pesadas
  - Cache para respostas frequentes
  - Monitoramento via métricas e logs estruturados
- Resultado esperado: menor latência e maior resiliência

---
<!-- _class: style_b -->

# Código: Exemplo JavaScript (API)
```javascript
// handlers/user.js
const express = require('express');
const router = express.Router();

// Simulação de um handler assíncrono
router.get('/users/:id', async (req, res) => {
  try {
    const id = req.params.id;
    // chamada fictícia ao banco
    const user = await findUserById(id);
    if (!user) return res.status(404).json({ error: 'Usuário não encontrado' });
    res.json(user);
  } catch (err) {
    console.error(err);
    res.status(500).json({ error: 'Erro interno' });
  }
});

module.exports = router;
```

---

# Código: Pipeline CI/CD (exemplo YAML)
```yaml
# .github/workflows/ci.yml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm ci
      - run: npm test
      - run: npm run build
```

---

# Dicas rápidas para apresentações
- Tenha um slide "longo" para detalhar sem perder o público: use marcadores claros.
- Use blocos de código pequenos e legíveis; destaque apenas o essencial.
- Use imagens e diagramas quando necessário (evite sobrecarregar texto).
- Termine com um slide de "Próximos passos" e contatos.

---
<!-- _class: style_c -->

# Conclusão
- Slides longos são úteis para documentação e explicações detalhadas.
- Combine teoria, código e exemplos práticos.
- Perguntas?

<!-- Speaker notes:
- Preparar demonstração ao vivo do endpoint.
- Mostrar logs de exemplo e métrica de latência.
-->