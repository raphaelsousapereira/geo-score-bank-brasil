# Metodologia — GEO Score Saúde Brasil (rascunho v0.1, pré-coleta)

**Objetivo:** medir sinais observáveis de prontidão de páginas públicas de operadoras de planos de saúde para leitura e eventual citação por ferramentas de IA. Não mede frequência real de citação, satisfação dos beneficiários, solidez financeira, conformidade jurídica definitiva nem qualidade médica.

## Dez dimensões (0–100)
| Dimensão | Evidência de auditoria |
|---|---|
| Acesso e indexação | robots.txt, respostas HTTP a coletores identificados, sitemap, noindex/canonical |
| Identidade da operadora | registro ANS, nome canônico, organização, vínculos entre marcas, dados estruturados |
| Conformidade e transparência | privacidade, ouvidoria, canais de atendimento, documentos institucionais aplicáveis |
| Transparência de planos | informações acessíveis de coberturas, rede, carências, reajustes, contratação e reembolso, com variações por produto |
| Respostas citáveis | texto autossuficiente, autoria, datas, fontes e contexto |
| Perguntas do setor | cobertura de dúvidas frequentes comparáveis e aplicáveis |
| Arquitetura de links | silos, links contextuais, profundidade e descoberta de páginas |
| Prontidão para agentes | legibilidade em HTML, ausência de etapas obrigatórias de escrita para consulta pública, sinais técnicos |
| UX e acessibilidade | home renderizada em 320/390/768/1440 px, semântica, contraste, navegação e estabilidade visual |
| Maturidade institucional | atualizações, documentação, imprensa, contato, esclarecimentos e responsabilidade editorial |

## Fórmula pública proposta
- Cada dimensão recebe nota de 0 a 100 **somente** se houver evidência verificável, URL de fonte e regra de pontuação documentada.
- Cobertura = número de dimensões medidas / 10. Dimensões não medidas são **N/A** e não contam como zero.
- Elegibilidade para o ranking: cobertura de **70% ou mais**.
- `nota_0_1000 = arredondar(10 × média aritmética das dimensões medidas)`.
- A metodologia é versionada e os resultados devem publicar cobertura e análises de sensibilidade. A fórmula é diferente da versão ponderada e proprietária do GEO Score Bank Brasil; **não comparar notas dos dois setores diretamente**.
- Ausência de site acessível, bloqueio ou erro de coleta implica **sem medida**, nunca zero automático.

## Motores usados como evidência
PANDORA GEO SCORE, PANDORA PORTEIRO, PANDORA POLÍTICAS (perfil ANS específico), PANDORA SPEED (PageSpeed/CrUX), PANDORA UX (home) e CONVERTA 360 (home). Notas de UX, velocidade e conversão são diagnósticos auxiliares e **não são somadas automaticamente** à nota setorial. O CONVERTA estima problemas de conversão, não mede vendas.

## Coleta e publicação
Robô identificado, respeito a robots.txt e limitações de acesso; não contornar 403/CAPTCHA/firewall nem enviar formulários. Guardar internamente URL solicitada/final, status, data, versão do motor, cobertura e hash da evidência. Publicar somente evidências públicas redigidas, sem código proprietário, chaves, dados de beneficiários ou logs brutos.

A edição de novembro de 2026 ainda não possui coleta homologada. Fontes e norma específica em [FONTES.md](FONTES.md). O diagnóstico de políticas verifica **visibilidade editorial** do conteúdo e não pode afirmar descumprimento legal com base apenas na ausência de links detectados.
