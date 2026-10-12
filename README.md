# opencode-modo-estudos

Modo de estudos com foco ENEM para OpenCode: `mentor` (primary) + 3 coords + 8 workers, comandos `/estudar` e `/estudar-enem`, 5 skills com evidência e trilhas por área.

Exportado do [`opencode-orquestrador`](https://github.com/Gabsz17/opencode-orquestrador) (missão modo estudos ENEM + skills, `coord-qualidade: LIBERADO`).

## Conteúdo

```
agents/           mentor, coord-teoria, coord-pratica, coord-avaliacao + 8 workers
commands/         estudar.md (/estudar) + estudar-enem.md (/estudar-enem)
templates/        PLANO-ESTUDOS.md (com seção ENEM opcional)
docs/estudos/     README + enem/ (README + exemplo esqueleto) + exemplo-iniciante/
docs/pesquisa/    enem-fontes.md (matriz, edital, provas INEP, Marp, direitos) +
                  skills-orquestrador-estudos.md (evidências Dunlosky-2013 + mapeamento)
skills/           recall-ativo, repeticao-espacada, pratica-intercalada,
                  explicar-para-aprender, delegacao-verificada
evals/            estudos.md (7 evals comportamentais do modo)
```

## Instalação

```powershell
# na sua config ativa do OpenCode (faça backup antes)
Copy-Item -Recurse agents\, commands\, skills\, templates\, docs\, evals\ "$env:USERPROFILE\.config\opencode\"
```

> Dependência opcional: o `mentor` pode acionar `coord-pesquisa` (web-researcher) quando falta fonte oficial — esse coord vive no repo `opencode-orquestrador`. Sem ele, o modo funciona com a regra `não confirmado`.

## Uso

- `/estudar <tema> [nível]` — trilha geral (`iniciante|intermediario|avancado`).
- `/estudar-enem <area> <tema>` — ENEM por área (`linguagens|humanas|natureza|matematica|redacao`): teoria + `questoes.md` + `simulados.md` + `slides.md` (Marp) + quiz + `progresso.md`.

## Regras duras do modo

- Questões oficiais SÓ do INEP (ano + caderno/cor + nº + link); resto é `autoral — padrão ENEM`. Nunca banco pago, nunca questão falsa atribuída ao INEP.
- TRI só como conceito (sem cálculo de nota). Redação por competências, sem nota oficial.
- Sem fonte oficial = `não confirmado`. Nenhum segredo no repo.

## Licença

MIT — ver `LICENSE`.
