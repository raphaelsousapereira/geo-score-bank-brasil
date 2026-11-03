# Metodologia — GEO Score Bank Brasil

Motor: PANDORA BANK SCORE Ω v1.0.0 (Raphael Sousa Pereira). Sem chamada a LLM e sem API paga: a mesma página coletada
dá sempre a mesma nota.

## Como a nota é formada

A nota (0 a 1000) é a **média ponderada** das notas das 10 dimensões medidas, reescalada para a faixa de 0 a 1000.
Uma dimensão sem medição é N/A: sai do cálculo e reduz a cobertura, nunca vira zero. Entra no ranking o banco com
**cobertura de 70% ou mais**.

**Os pesos de cada dimensão são próprios da metodologia e não são publicados.** Para transparência sem expor os pesos,
o ranking é calculado **também com pesos iguais**, e as inversões de ordem entre a versão ponderada e a de pesos
iguais são divulgadas (coluna de sensibilidade). As três primeiras posições, nesta edição, se mantêm nas duas versões.

## Dimensões

| Dimensão | O que mede | Instrumento |
|---|---|---|
| Acesso e indexação por IA | robots.txt por robô de IA (busca, usuário, treino), noindex nas páginas, llms.txt e sitemap | AI-DISCOVERABILITY, INDEXADOR |
| Identidade da instituição | nome canônico, NAP, tipo de dado estruturado, grafo `@id`, schema conferindo com o texto, perfis `sameAs`, CNPJ com dígito verificador | SCHEMA AUDIT, FOOTER |
| Conformidade regulatória | políticas exigidas para finanças e empresas de grande porte: ouvidoria e aviso de risco (obrigatórias), privacidade, termos, cookies, segurança, ética, canal de denúncia | POLÍTICAS |
| Transparência de produto e tarifas | taxa de juros com período no texto, CET, página de tarifas ligada da home e aberta, rendimento em % do CDI, produto financeiro marcado em JSON-LD, e dados citáveis (estatística com fonte, frescor, tabelas) | verificações bancárias + DADOS |
| Respostas citáveis | trecho de resposta depois de cada título, perguntas que um usuário faria a um LLM, E-E-A-T | CAPSULE, PULSE |
| Perguntas do setor | das perguntas comuns do setor (respondidas por 3 ou mais outros bancos da edição), quantas o banco também responde; parcial vale metade | PAA |
| Arquitetura de links | PageRank interno por silo, links contextuais, coesão das âncoras, profundidade | LINKS SITE |
| Prontidão para agentes | HTTPS, HSTS, texto sem JavaScript, Open Graph, e formulários e conversão legíveis por agentes | AGENTIC, CONVERTA 360 |
| Padrão visual e acessibilidade | contraste do texto (WCAG), estilos de botão, fundo, tipografia, botões no celular, medidos num navegador | PADRÃO |
| Maturidade institucional | presença, oferta, confiança, autoridade e referência (FAQ, imprensa, ESG, carreiras, acessibilidade) | SLUGS |

## Regras de coleta

- Robô identificado (`PANDORA-Audit/1.0`), robots.txt respeitado, sem disfarce de navegador e sem contornar firewall.
- A página medida é a home que o robô recebe. Quando a raiz redireciona para outro caminho (idioma, país, perfil),
  o resultado traz um alerta. Exceção documentada: Bradesco, medido a partir da home institucional que o próprio
  llms.txt do banco declara, porque a raiz não expõe páginas.
- Home que responde 403, desafio de firewall, redirecionamento em laço ou que tem menos de 150 palavras visíveis sem
  JavaScript: banco sem medida, com o motivo.
- Home e até 3 páginas internas para os motores de página; até 40 páginas para links; até 25 páginas por banco para
  perguntas do setor.

## Limites

- Mede prontidão do site, não a probabilidade de uma IA citar o banco.
- Os pesos são hipótese de projeto, próprios da metodologia e não publicados; por isso o ranking também sai com pesos
  iguais e as inversões são divulgadas.
- A coleta parte de um servidor fora do Brasil; firewalls podem tratar outras origens de outro jeito.
- A verificação de perfis externos (`sameAs`) depende de sites de terceiros e pode variar entre coletas.
- Amostra de páginas pequena frente ao tamanho dos sites de bancos.

## Edições

Uma edição por mês, com a mesma metodologia. Mudança de método gera nova versão e aviso de que as notas deixam de ser
comparáveis.
