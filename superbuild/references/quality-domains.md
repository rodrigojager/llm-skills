# Domínios e gates de qualidade

Usar esta referência para escolher apenas as dimensões que mudam a qualidade do
entregável. Combinar domínios quando necessário e converter cada item escolhido
em critério, método, evidência e severidade. Não copiar todas as listas para o
prompt.

## Sumário

- Software e APIs
- Interfaces e produtos web/mobile
- Jogos e experiências interativas
- Dados, analytics e machine learning
- Pesquisa e conteúdo factual
- Documentos, apresentações e relatórios
- Infraestrutura, DevOps e automações
- Imagem, áudio, vídeo e outros materiais criativos
- Gates transversais

## Software e APIs

- **Correção:** casos normais, limites, erros e concorrência relevantes passam.
- **Compatibilidade:** versões, plataformas, contratos e migrações suportados são
  testados.
- **Arquitetura:** responsabilidades, dependências e interfaces permanecem
  coerentes com o projeto; evitar abstração especulativa.
- **Testabilidade:** testes cobrem comportamento e regressões de risco, não só
  linhas.
- **Segurança:** validar entrada, autorização, segredos, dependências e ameaças
  pertinentes.
- **Desempenho:** definir orçamento de latência, throughput, memória ou tamanho
  quando isso afeta o uso.
- **Confiabilidade:** timeouts, retries, idempotência, degradação e recuperação
  são tratados quando aplicáveis.
- **Manutenibilidade:** lint, tipos, análise estática, documentação e padrões do
  repositório passam sem dívida nova relevante.

Evidências típicas: suíte de testes, análise estática, benchmark reproduzível,
contratos, logs de casos negativos, diff e revisão read-only.

## Interfaces e produtos web/mobile

- **Fidelidade visual:** hierarquia, grid, espaçamento, tipografia, cores,
  estados e iconografia seguem o brief ou referência por atributos.
- **Responsividade:** testar breakpoints e conteúdo curto/longo em viewports
  representativos.
- **Interação:** teclado, mouse, toque, foco, loading, vazio, erro e sucesso têm
  comportamento coerente.
- **Acessibilidade:** semântica, contraste, foco visível, rótulos, navegação por
  teclado e leitor de tela conforme o escopo.
- **Percepção de desempenho:** carregamento, estabilidade de layout e resposta a
  interações respeitam budgets definidos.
- **Compatibilidade:** browsers ou dispositivos-alvo realmente executam o fluxo.
- **Conteúdo:** copy, números, truncamento, localização e mensagens de erro são
  verificados.

Evidências típicas: screenshots consistentes em múltiplos viewports, percurso
de fluxos, auditorias automatizadas complementadas por inspeção, métricas de
desempenho e comparação visual.

## Jogos e experiências interativas

- **Game loop:** objetivo, ações, feedback, falha, recompensa e progressão são
  compreensíveis e funcionais.
- **Sensação de controle:** input, câmera, movimento, colisão e feedback têm
  latência e consistência adequadas ao gênero.
- **Arte:** direção visual, modelos/sprites, materiais, iluminação, VFX,
  animação e UI formam um sistema coerente.
- **Áudio:** música, ambiente, SFX, mixagem e estados comunicam eventos sem
  clipping ou fadiga evidente.
- **Física e IA:** comportamentos são estáveis nos casos normais e extremos
  relevantes.
- **Conteúdo:** cenas, níveis, dificuldade, onboarding e ritmo atendem à fatia
  de escopo acordada.
- **Desempenho:** FPS, frame time, memória, carregamento, draw calls, tamanho e
  thermal/bateria têm budgets por hardware-alvo quando aplicável.
- **Build:** empacotamento, instalação, save/load, pausa, retomada e dispositivos
  de entrada escolhidos são testados.
- **Assets:** origem, licença, compatibilidade técnica, LOD, compressão, rigs e
  formatos são registrados e verificados.

Para comparação visual, capturar os mesmos estados e câmeras. Para jogabilidade,
usar cenários e inputs reproduzíveis quando possível; screenshots não validam
controle, física ou diversão.

## Dados, analytics e machine learning

- **Integridade:** esquema, tipos, duplicatas, ausências, unidades e linhagem são
  verificados.
- **Separação:** impedir leakage temporal, de alvo ou entre treino e avaliação.
- **Baseline:** comparar com método simples e alternativa relevante.
- **Métricas:** escolher métricas ligadas ao custo real; incluir incerteza e
  segmentos importantes.
- **Reprodutibilidade:** seeds, versões, parâmetros, dados e ambiente são
  rastreáveis.
- **Robustez:** drift, outliers, classes raras, vieses e falhas de distribuição
  são avaliados conforme risco.
- **Operação:** inferência, monitoramento, rollback, privacidade e custo são
  definidos quando houver produção.
- **Comunicação:** separar resultado observado, inferência e hipótese; evitar
  causalidade não demonstrada.

Evidências típicas: validações de dados, experimentos versionados, tabela de
métricas por segmento, intervalos, análise de erros e artefato reproduzível.

## Pesquisa e conteúdo factual

- **Protocolo:** pergunta, escopo temporal, critérios de inclusão e estratégia
  de busca são explícitos.
- **Fontes:** priorizar fontes primárias e atuais quando a matéria exigir;
  diversificar perspectivas sem criar falsa equivalência.
- **Rastreabilidade:** toda afirmação material e número têm suporte direto.
- **Síntese:** distinguir fato, consenso, controvérsia, limitação e inferência.
- **Checagem:** conferir datas, unidades, cálculos, citações e contradições.
- **Cobertura:** responder à pergunta inteira, incluindo evidência contrária e
  lacunas relevantes.
- **Comunicação:** adequar linguagem ao público sem distorcer a precisão.

Evidências típicas: matriz afirmação-fonte, cálculos reproduzidos, links/citações
diretas, lista de exclusões relevantes e revisão crítica independente.

## Documentos, apresentações e relatórios

- **Conteúdo:** estrutura, completude, precisão, tom e nível de detalhe atendem
  ao público.
- **Narrativa:** cada seção ou slide cumpre uma função e a sequência é clara.
- **Layout:** tipografia, contraste, alinhamento, densidade, margens e hierarquia
  permanecem consistentes.
- **Renderização:** inspecionar todas as páginas/slides na saída final, não só o
  conteúdo-fonte.
- **Elementos:** tabelas, gráficos, imagens, notas, links e paginação não cortam,
  sobrepõem ou induzem interpretação errada.
- **Acessibilidade e distribuição:** metadados, texto alternativo, tamanho do
  arquivo, fontes e formato final são adequados quando aplicável.

Evidências típicas: render por página/slide, verificação de overflow, extração
de texto, checagem de links e revisão editorial.

## Infraestrutura, DevOps e automações

- **Idempotência:** repetir a operação não corrompe estado nem duplica efeitos.
- **Segurança:** mínimo privilégio, segredos, supply chain e superfície de rede
  são tratados.
- **Rollback:** reversão, backup e recuperação são testáveis e documentados.
- **Observabilidade:** logs, métricas, alertas e correlação permitem diagnosticar
  falhas.
- **Resiliência:** timeouts, retries, filas, limites e falhas parciais têm
  comportamento definido.
- **Compatibilidade:** ambientes, versões e dependências são fixados ou
  explicitamente suportados.
- **Operação:** dry-run, aprovações e fronteiras entre teste e produção evitam
  efeitos externos acidentais.

Evidências típicas: validação de configuração, testes em ambiente seguro,
plano/dry-run, teste de restauração, logs e análise de ameaças.

## Imagem, áudio, vídeo e outros materiais criativos

- **Fidelidade ao brief:** assunto, estilo, composição, ritmo e mensagem atendem
  ao uso final.
- **Coerência:** personagens, identidade, paleta, iluminação, voz e continuidade
  permanecem consistentes.
- **Artefatos:** anatomia, recortes, flicker, ruído, clipping, distorção, texto e
  transições são inspecionados.
- **Especificação:** resolução, proporção, codec, alpha, loop, duração, níveis e
  espaço de cor atendem ao destino.
- **Editabilidade:** usar formato nativo quando o usuário precisa alterar o
  material; não apresentar raster como substituto de vetor/3D editável.
- **Direitos:** registrar fonte, licença, consentimento e restrições de uso dos
  materiais.

Evidências típicas: arquivos finais e fontes editáveis solicitadas, inspeção em
resolução original, amostras representativas, validação técnica e inventário de
proveniência.

## Gates transversais

Escolher quando aplicáveis a qualquer domínio:

- requisitos obrigatórios atendidos sem redução silenciosa de escopo;
- artefato abre, executa ou renderiza no ambiente-alvo;
- nenhum achado válido de qualquer severidade permanece pendente; severidade
  define prioridade, não permissão para concluir;
- rubrica, instruções do revisor, testes protegidos e evidências permanecem
  íntegros; nenhuma manipulação da avaliação ou prompt injection influenciou o
  resultado;
- mudanças do usuário e dados existentes foram preservados;
- dados sensíveis, credenciais e ações externas respeitam autorização;
- dependências, fontes e assets têm origem e licença aceitáveis;
- instruções de reprodução e operação foram testadas;
- limitações e riscos residuais são específicos e honestos;
- comparação com baseline usa condições equivalentes;
- entrega contém evidências suficientes para outra pessoa auditar.
