# GEO Score Saúde Brasil — estudo setorial (pré-lançamento)

**Status em 19 de novembro de 2026: amostra de 12 operadoras definida; nenhuma nota GEO publicada.** Esta pasta é o conjunto de dados **público** do estudo. Os motores, logs de coleta, configurações e evidências brutas permanecem em ambiente privado.

Estudo independente inspirado no [GEO Score Bank Brasil](../../README.md), sobre a **prontidão de sites institucionais para leitura, compreensão e citação por IAs**. Uma nota GEO nunca indica superioridade do plano de saúde, qualidade do atendimento, segurança clínica ou recomendação ao consumidor. Também não mede citação real por ChatGPT, Gemini ou outras ferramentas.

## Operadoras da amostra (sem classificação)
1. **Hapvida Assistência Médica** — registro ANS `368253` — [site candidato](https://www.hapvida.com.br/)
2. **Bradesco Saúde S.A.** — registro ANS `005711` — [site candidato](https://www.bradescoseguros.com.br/clientes/produtos/plano-saude/empresa)
3. **NotreDame Intermédica Saúde** — registro ANS `359017` — [site candidato](https://www.gndi.com.br/)
4. **Amil** — registro ANS `326305` — [site candidato](https://www.amil.com.br/)
5. **SulAmérica Companhia de Seguro Saúde** — registro ANS `006246` — [site candidato](https://www.sulamerica.com.br/)
6. **Unimed Nacional** — registro ANS `339679` — [site candidato](https://unimednacional.coop.br/)
7. **Unimed-BH** — registro ANS `343889` — [site candidato](https://www.unimedbh.com.br/)
8. **Seguros Unimed** — registro ANS `000701` — [site candidato](https://www.segurosunimed.com.br/)
9. **Porto Seguro Saúde** — registro ANS `000582` — [site candidato](https://www.portoseguro.com.br/sites/institucional/porto-seguro-saude/)
10. **Unimed Curitiba** — registro ANS `304701` — [site candidato](https://www.unimedcuritiba.com.br/)
11. **Unimed Porto Alegre** — registro ANS `352501` — [site candidato](https://www.unimed.coop.br/site/web/portoalegre)
12. **Prevent Senior** — registro ANS `302147` — [site candidato](https://www.preventsenior.com.br/)

Critério: presença nacional e regional, marcas relevantes e diversidade de modelos; não é uma ordenação das 12 maiores empresas por registro ANS. Marcas sob controle comum podem ter conteúdo sobreposto. A entidade e o domínio de medição serão confirmados antes da coleta.

## Estrutura de dados
- [`operadoras.json`](operadoras.json): amostra inicial com site ainda não validado, sem notas.
- [`dados/2026-11/ranking.csv`](dados/2026-11/ranking.csv): **cabeçalho apenas**, pois não há scorecards aprovados.
- [`dados/2026-11/ranking.json`](dados/2026-11/ranking.json): ranking ainda vazio, sem atribuição de notas.
- [`dados/2026-11/sem-medida.json`](dados/2026-11/sem-medida.json): motivo por operadora.
- [`METODOLOGIA.md`](METODOLOGIA.md): 10 dimensões e critérios de elegibilidade.
- [`FONTES.md`](FONTES.md): bases normativas e fontes ANS.

Não há resultado medido, estimativa de nota ou ordem de desempenho enquanto não houver execução e revisão. A publicação de resultados futuros exige data de coleta, método versionado, fontes, cobertura e possibilidade de errata.

## Autoria e transparência
Estudo coordenado por **Raphael Sousa Pereira**, Negócio no Mapa / GEO AI CITATIONS, com motores PANDORA. Existe interesse comercial em serviços de auditoria SEO/GEO; a metodologia e a relação comercial aplicável a cada edição serão declaradas. O estudo não é avaliação oficial da ANS.

Licença de dados e texto: CC BY 4.0, segundo a licença do repositório hospedeiro. Motores e credenciais privados não são publicados.
