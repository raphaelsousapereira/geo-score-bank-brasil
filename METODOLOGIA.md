# Metodologia — GEO Score Bank Brasil

Motor: PANDORA BANK SCORE Ω v1.0.0 (Raphael Sousa Pereira). Sem chamada a LLM e sem API paga: a mesma página coletada
dá sempre a mesma nota.

## Fórmula

nota = 10 × Σ (peso × nota da dimensão) ÷ Σ (peso das dimensões medidas), de 0 a 1000

cobertura = Σ (peso das dimensões medidas) ÷ 100

Dimensão sem medição é N/A: sai do denominador e reduz a cobertura, nunca vira zero. Entra no ranking o banco com
cobertura de 70% ou mais.

## Dimensões e pesos

| Dimensão | Peso |
|---|---|
| Acesso e indexação por IA | 10 |
| Identidade da instituição | 12 |
| Conformidade regulatória | 12 |
| Transparência de produto e tarifas | 14 |
| Respostas citáveis | 12 |
| Perguntas do setor | 10 |
| Arquitetura de links | 8 |
| Prontidão para agentes | 8 |
| Padrão visual e acessibilidade | 6 |
| Maturidade institucional | 8 |

| Dimensão | O que mede | Instrumento |
|---|---|---|
| Acesso e indexação por IA | robots.txt por robô de IA (busca, usuário, treino), noindex nas páginas, llms.txt e sitemap | AI-DISCOVERABILITY, INDEXADOR |
| Identidade da instituição | nome canônico, NAP, tipo de dado estruturado, grafo `@id`, schema conferindo com o texto, perfis `sameAs`, CNPJ com dígito verificador | SCHEMA AUDIT, FOOTER |
| Conformidade regulatória | políticas exigidas para finanças e empresas de grande porte: ouvidoria e aviso de risco (obrigatórias), privacidade, termos, cookies, segurança, ética, canal de denúncia | POLÍTICAS |
| Transparência de produto e tarifas | 60%: taxa de juros com período no texto (25), CET (20), página de tarifas ligada da home e aberta (20), rendimento em % do CDI (15), produto financeiro marcado em JSON-LD (20); 40%: dados citáveis (estatística com fonte, frescor, tabelas) | verificações bancárias + DADOS |
| Respostas citáveis | trecho de resposta depois de cada título, perguntas que um usuário faria a um LLM, E-E-A-T | CAPSULE, PULSE |
| Perguntas do setor | das perguntas comuns do setor (respondidas por 3 ou mais outros bancos da edição), quantas o banco também responde; parcial vale metade | PAA |
| Arquitetura de links | PageRank interno por silo, links contextuais, coesão das âncoras, profundidade | LINKS SITE |
| Prontidão para agentes | HTTPS, HSTS, texto sem JavaScript, Open Graph (50%) e formulários e conversão legíveis por agentes (50%) | AGENTIC, CONVERTA 360 |
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
- Os pesos são hipótese de projeto, não pesos validados. O ranking sai também com pesos iguais e as inversões são
  publicadas.
- A coleta parte de um servidor fora do Brasil; firewalls podem tratar outras origens de outro jeito.
- A verificação de perfis externos (`sameAs`) depende de sites de terceiros e pode variar entre coletas.
- Amostra de páginas pequena frente ao tamanho dos sites de bancos.

## Edições

Uma edição por mês, com a mesma metodologia. Mudança de método gera nova versão e aviso de que as notas deixam de ser
comparáveis.
