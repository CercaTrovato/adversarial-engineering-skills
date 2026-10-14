# Adversarial Engineering Skills

**Questione o plano. Revise as alterações. Comprove o resultado.**

[English](../README.md) · Português (Brasil) · [Todos os idiomas](../README.md)

Uma habilidade de gestão de engenharia para agentes de programação, com três etapas de revisão baseadas em evidências. Quem revisa deve apontar um caminho concreto de falha; o agente principal deve corrigir o problema ou justificar sua rejeição com evidências.

## Três etapas

1. **Plano**: antes de uma implementação significativa, verificar restrições, contratos de API e dados, permissões, transições de estado, consumidores esquecidos e complexidade desnecessária.
2. **Alteração**: após cada lote coerente e antes do merge, revisar o diff real e os comportamentos afetados. Acrescentar uma revisão de segurança quando necessário.
3. **Aceitação**: antes de declarar a conclusão, sustentar as afirmações com resultados atuais de execução ou inspeção dos artefatos e explicitar o que não foi verificado.

Mudanças pequenas recebem verificações pequenas; mudanças de alto risco recebem perspectivas independentes e lotes verificáveis. A autorrevisão deve ser identificada e não substitui uma revisão independente exigida pelo projeto. Pendências bloqueantes impedem a aprovação da etapa. A habilidade não concede autorização para implantar ou publicar.

## Instalação

Com Git e Node.js/npm disponíveis, execute no projeto de destino:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Escolha os agentes de forma interativa ou acrescente `-a claude-code`, `-a codex` ou `-a cursor`. Use `--copy` para evitar links simbólicos e `-g` para instalar no escopo do usuário. Consulte o [guia de instalação](INSTALL.md) para outros agentes, instalação manual e remoção. A compatibilidade segue a lista atual da Skills CLI e não significa que todos os agentes foram testados de ponta a ponta.

## Uso

> Use adversarial-engineering nesta alteração. Questione o plano antes de implementar, revise o diff e verifique os critérios de aceitação antes de concluir. Informe o tratamento de cada achado, as evidências e os limites da verificação.

Para uma revisão sem alterações, acrescente “Não modifique arquivos”. Reavalie os achados afetados pelas correções; não repita verificações cujas evidências continuem válidas. Novas rodadas exigem novas evidências ou uma correção substancial.

O [SKILL.md em inglês](../skills/adversarial-engineering/SKILL.md) é a referência normativa. Esta página apresenta o conceito e a instalação. A habilidade não garante ausência de defeitos nem impõe controles automáticos de CI. Veja [validação](VALIDATION.md), [contribuições](../CONTRIBUTING.md) e [licença MIT](../LICENSE). Revisões de falantes nativos são bem-vindas.
