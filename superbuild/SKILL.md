---
name: superbuild
description: Gerar um prompt mestre, específico e executável para o Codex conduzir projetos com rigor excepcional, validação independente e evidências de qualidade. Usar quando o usuário invocar superbuild ou pedir um prompt de execução, briefing de orquestração, protocolo de qualidade extrema, comparação rigorosa com referências, múltiplos revisores/subagentes ou ciclos de construção e auditoria para software, jogos, interfaces, dados, pesquisa, documentos, automações, mídia ou outro entregável complexo. Não usar apenas porque o usuário pediu uma implementação bem-feita; esta skill produz o prompt que comandará o trabalho, em vez de executar o projeto, salvo se o usuário pedir explicitamente as duas etapas.
---

# Superbuild

Gerar um prompt pronto para colar no Codex. Converter ambição subjetiva — como
“perfeito”, “AAA” ou “igual ao melhor do mercado” — em escopo explícito,
critérios mensuráveis, revisões independentes e evidências reproduzíveis.

## 1. Entender o pedido

Extrair, quando existirem:

- resultado e entregáveis;
- estado inicial, repositório e materiais fornecidos;
- referências de qualidade e quais atributos delas importam;
- stack, engine, plataforma, formato e ambiente-alvo;
- política de assets e fontes: fornecidos, externos, pagos, open source ou
  gerados;
- restrições de prazo, custo, licenças, compatibilidade e escopo;
- requisitos obrigatórios e exclusões explícitas.

Não presumir Three.js, JavaScript, Unity ou qualquer stack. Preservar a escolha
do usuário. Se a escolha estiver aberta, mandar o Codex inspecionar o contexto,
comparar opções e selecionar a alternativa mais adequada, registrando a
justificativa e o custo de troca.

Tratar uma referência como barra de qualidade por atributos, não como licença
para copiar código, arte, texto, marcas ou conteúdo protegido. Distinguir
“qualidade comparável” de “mesmo escopo”. Em pedidos de escala AAA ou similar,
esclarecer se a referência vale para uma fatia vertical, um MVP ou o produto
inteiro quando isso alterar materialmente a viabilidade.

## 2. Perguntar somente o que muda o prompt

Fazer no máximo três perguntas curtas quando uma decisão ausente mudar
materialmente a arquitetura, o acesso necessário ou o critério de sucesso.
Priorizar, nesta ordem:

1. entregável e fronteira de escopo;
2. stack/plataforma e restrições inegociáveis;
3. referência de qualidade e política de assets/fontes.

Usar opções selecionáveis quando a interface oferecer esse recurso. Continuar
com hipóteses declaradas quando a resposta for útil, mas não bloqueante. Não
perguntar novamente por informação já fornecida.

Se o usuário mencionar assets autenticados ou pagos, como Unity Asset Store,
não presumir acesso ou propriedade. Fazer o prompt mandar inventariar apenas os
assets realmente disponíveis no projeto ou fornecidos pelo usuário, respeitar
licenças e parar somente se uma aquisição, autenticação ou importação depender
do usuário.

## 3. Dimensionar o rigor

Aplicar rigor alto por padrão, mas manter o processo proporcional ao risco e ao
tamanho. Não inflar um trabalho pequeno com agentes e checklists sem benefício.
Para cada dimensão relevante, criar uma linha de contrato de qualidade com:

| Campo | Conteúdo |
| --- | --- |
| Dimensão | Aspecto a avaliar |
| Critério de aprovação | Condição observável ou limiar |
| Método | Teste, inspeção, benchmark ou comparação |
| Evidência | Artefato que comprova o resultado |
| Severidade | Bloqueante, importante ou melhoria |

Selecionar somente dimensões aplicáveis. Consultar
[quality-domains.md](references/quality-domains.md) para escolher gates de
software, UI, jogos, dados/ML, pesquisa, documentos, infraestrutura,
automações e mídia. Combinar se o pedido atravessar domínios.

Não transformar métricas substitutas em objetivo cego. Por exemplo: cobertura
não prova correção, FPS médio não prova fluidez e quantidade de fontes não prova
qualidade da pesquisa.

## 4. Gerar o prompt operacional

Produzir um único prompt autocontido, preenchido com os dados conhecidos e no
idioma do usuário. Evitar placeholders genéricos quando for possível inferir ou
registrar uma hipótese segura. Incluir as seções abaixo na ordem indicada,
omitindo apenas as comprovadamente irrelevantes.

### Missão e resultado

Definir o objetivo, entregáveis, público, ambiente-alvo, fronteira de escopo e
o significado concreto da referência de qualidade.

### Verdade inicial e restrições

Mandar inspecionar o repositório, arquivos, instruções aplicáveis, estado do Git,
dependências e materiais existentes antes de alterar qualquer coisa. Preservar
mudanças do usuário e não substituir componentes funcionais sem justificativa.
Listar stack fixa, decisões abertas, restrições, permissões e hipóteses.

### Contrato de qualidade

Inserir a matriz específica de critérios, métodos, evidências e severidades.
Fazer todo gate bloqueante ser binário o suficiente para impedir uma conclusão
baseada apenas em opinião.

### Planejamento e arquitetura

Mandar usar o mecanismo de planejamento disponível no Codex, manter o plano
atualizado e registrar decisões relevantes. Exigir uma fatia vertical ou prova
de ponta a ponta cedo quando isso reduzir risco. Planejar rollback ou
recuperação para alterações arriscadas.

### Estratégia de stack, fontes e assets

Definir uma destas políticas conforme o pedido:

- usar somente materiais fornecidos;
- selecionar materiais externos com proveniência e licença verificadas;
- gerar materiais novos com as ferramentas apropriadas;
- combinar as opções e registrar a origem de cada item.

Não mandar uma ferramenta de imagem raster criar diagramas exatos, vetores
precisos, modelos 3D editáveis ou código quando houver ferramenta nativa melhor.
Para jogos, permitir Unity, Unreal, Godot, Three.js, Babylon.js ou outra engine
compatível com o contexto, sem favorecer uma por padrão.

### Orquestração de agentes

Pedir subagentes explicitamente, pois o Codex não deve depender de delegação
implícita. Dimensionar pelo orçamento disponível e agrupar preocupações
relacionadas; não criar um agente por item trivial. Reservar o agente principal
para decisões, integração e alterações conflitantes.

Usar subagentes principalmente para trabalhos independentes, como:

- reconhecimento de contexto e riscos;
- pesquisa ou benchmark de referência;
- auditoria funcional e de testes;
- auditoria visual/UX/acessibilidade;
- segurança, desempenho, dados ou domínio especializado.

Separar autoria de aprovação: quem implementa um aspecto não deve ser seu único
revisor. Preferir revisores em modo somente leitura, retornando achados com
severidade, evidência e ação sugerida. Executar agentes em paralelo apenas
quando seus trabalhos forem independentes. Evitar edições simultâneas nos
mesmos arquivos; usar lotes ou worktrees quando apropriado. Esperar os revisores
necessários antes do gate integrado. Se subagentes não estiverem disponíveis,
executar passes distintos com rubricas explícitas e declarar a limitação; nunca
inventar resultados de agentes.

### Ciclo de execução e correção

Substituir qualquer `/loop` fictício por este ciclo real:

1. estabelecer baseline e reproduzir o estado atual;
2. implementar a menor fatia verificável;
3. executar verificações automatizadas e inspeções aplicáveis;
4. coletar evidências;
5. submeter a revisão independente;
6. classificar e corrigir causas, não apenas sintomas;
7. repetir os gates afetados e depois a regressão integrada.

Não parar no primeiro resultado aceitável. Continuar até todos os gates
bloqueantes passarem ou existir um bloqueio real de autorização, material,
ambiente ou viabilidade. Se o mesmo defeito persistir por três ciclos, mudar a
abordagem e diagnosticar a causa-raiz em vez de repetir mecanicamente. Nunca
usar um número arbitrário de iterações como prova de qualidade.

### Comparação e avaliação cega

Quando houver referência ou baseline, exigir condições comparáveis. Para visuais,
usar o mesmo viewport, estado, câmera, iluminação e resolução quando aplicável;
para desempenho, o mesmo hardware/carga e metodologia; para resultados
informacionais, a mesma pergunta, conjunto de casos e rubrica.

Quando a avaliação for subjetiva e houver capacidade, pedir comparação A/B
com rótulos aleatórios a um revisor independente, preservando o mapeamento fora
da avaliação. Não declarar teste cego se ele não foi realmente executado ou se
a origem for evidente. Usar métricas objetivas como complemento, não como
substituto de inspeção humana quando a qualidade percebida importar.

### Regras de honestidade e autonomia

Mandar avançar autonomamente nas decisões reversíveis e dentro do escopo.
Perguntar somente diante de escolha material, credencial, compra, licença,
ação externa ou risco que exija autorização. Proibir alegações como “perfeito”,
“idêntico”, “AAA” ou “pronto para produção” sem evidências suficientes. Se a
paridade total não for viável, entregar o melhor resultado verificável e listar
o gap exato, seu impacto e o próximo passo.

### Gate final e entrega

Exigir, antes de concluir:

- execução de todos os gates bloqueantes e regressões relevantes;
- revisão integrada sem achados críticos ou altos não resolvidos;
- inspeção real do artefato final, não apenas do código-fonte;
- inventário de testes, medições, screenshots/renderizações, fontes ou logs;
- instruções de execução/reprodução;
- resumo de arquivos alterados, decisões, limitações e riscos residuais.

Permitir conclusão somente com gates aprovados ou com bloqueio descrito de modo
preciso. Proibir esconder falhas, reduzir silenciosamente o escopo ou afirmar
que uma ferramenta/comando foi usado sem evidência.

## 5. Tratar comandos do Codex corretamente

Não incluir `/loop`: ele não é um mecanismo portátil do Codex. Não mandar o
agente executar comandos de interface que pertencem ao usuário. Expressar no
prompt as capacidades desejadas: planejar, delegar, revisar, testar, navegar,
renderizar e inspecionar com as ferramentas disponíveis.

Se o usuário disser qual superfície usará e controles de sessão ajudarem,
acrescentar antes do prompt uma seção curta **Controles opcionais para você**.
Listar somente comandos oficialmente suportados nessa superfície e deixar claro
que o usuário os executa. Exemplos possíveis incluem seleção de modelo/nível de
raciocínio, permissões, modo de plano, inspeção de subagentes e revisão final.
Omitir essa seção quando a superfície ou o suporte atual forem incertos.

Não fixar nomes internos de ferramentas, quantidade de agentes ou modelos que
podem não existir na sessão-alvo. Mandar detectar capacidades disponíveis e
usar fallbacks honestos.

## 6. Formato da resposta

Entregar:

1. no máximo três hipóteses relevantes, apenas se necessárias;
2. controles opcionais do usuário, apenas se aplicáveis;
3. `Prompt pronto para o Codex:` seguido de um único bloco `text` copiável.

Manter toda instrução operacional dentro do bloco. Não acrescentar uma longa
explicação depois dele. O prompt deve ser detalhado o bastante para governar a
execução, mas específico e proporcional; remover cláusulas genéricas que não
mudam o comportamento naquele caso.

## Exemplos de adaptação

- **Unity + Asset Store:** preservar Unity e a render pipeline existentes,
  inventariar pacotes já importados, validar compatibilidade/licença e avaliar
  gameplay, arte, física, desempenho e build da plataforma-alvo.
- **Three.js com assets gerados:** definir pipeline de geração e otimização,
  formatos e budgets, validar carregamento, LOD, iluminação, interação,
  responsividade, FPS e memória em dispositivos-alvo.
- **Sistema corporativo:** trocar “qualidade visual AAA” por correção funcional,
  segurança, acessibilidade, observabilidade, desempenho, migração, rollback e
  evidência de testes.
- **Pesquisa ou relatório:** trocar build/lint por protocolo de busca, fontes
  primárias, rastreabilidade das afirmações, checagem numérica, revisão crítica
  e QA visual do documento final.
