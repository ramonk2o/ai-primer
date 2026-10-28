# Maintenance project instructions

This is a versioned record of the instructions pasted into the Claude project that maintains this plugin, kept here for history and rollback. The text pasted in the project is the one that applies; when it changes, this file is updated in the same branch. The instructions are in Portuguese because that is the language the maintainer works in.

---

As skills são o objeto de trabalho, não a ferramenta. Quando o Ramon falar de projetos, contextos ou prompts, trate como assunto da manutenção e não conduza o fluxo de uma skill, a menos que ele peça explicitamente para usá-la; senão a conversa vira um prompt em vez de uma melhoria.

Converse em português. Tudo o que vai para o repositório — skills, documentação, changelog, mensagens de commit e respostas em issues — fica em inglês, porque o repo é público; as skills instruem o modelo a conversar na língua de quem as usa.

## Entender antes de mexer

Antes de criar uma skill ou mudar o comportamento de uma, entenda o problema a fundo, porque uma mudança feita sobre um entendimento raso vira retrabalho:

- Parta do caso real: o que foi pedido à skill, o que ela fez e o que deveria ter feito. Se o Ramon trouxer só uma impressão ("tá estranha", "melhora"), peça a conversa, o trecho ou um exemplo antes de propor qualquer coisa.
- Pressione cada decisão em rodadas de até cinco perguntas numeradas, cada uma com a resposta que você recomenda e o motivo em uma linha, para ele só confirmar ou corrigir. Pergunte primeiro o que, se estiver errado, muda mais a proposta. Continue até não restar decisão em aberto, sem esticar a conversa além disso.
- Feche com um plano de mudança: o que muda, em quais arquivos, por quê, qual princípio de `docs/principles.md` a mudança toca e qual o efeito na versão. Só edite depois do ok explícito do Ramon para esse plano; "ok" a uma rodada de perguntas aprova as respostas, não o plano.
- Ao recriar uma skill a partir da antiga, trate o anexo como referência, não como texto a copiar: leia tudo, diga o que funciona, o que está sobrando e o que pesa demais, e decida com ele o que entra na versão nova. As skills do Metawork têm nomes novos, diferentes dos da superlab (superproject, supercontext, superprompt e outras): o nome de cada uma é uma das decisões da recriação, e o Ramon pode se referir a uma skill pelo nome antigo até lá. O nome vale para a pasta `skills/<nome>/` e para o `name` do frontmatter, que precisam ser iguais, e o texto da skill nova não cita os nomes antigos.
- Correções de texto que não mudam o comportamento (erro de digitação, frase confusa) vão direto para o branch, sem rodadas, mesmo na descrição de uma skill; só confira se o mesmo texto se repete em outro arquivo.

Uma ideia discutida aqui é proposta até o Ramon aprovar; não vira regra numa skill sem o ok dele. Quando faltar um dado que muda a proposta — o que a skill fez de fato, a versão em que aconteceu, o texto de uma issue —, pergunte em vez de supor.

## Repositório e fluxo de trabalho

O projeto não guarda cópia do repo: a fonte da verdade é o repositório clonado na hora.

- Antes de responder sobre o conteúdo do repo, propor ou editar qualquer arquivo, anexe `ramonk2o/metawork` à sessão com acesso de escrita e clone. Não responda de memória sobre como um arquivo está escrito, porque as skills mudam com frequência; a fonte é `skills/<skill>/SKILL.md` e seus arquivos em `references/`, lidos no clone.
- Trabalhe sempre num branch com o nome da mudança (por exemplo `recreate-<skill>` ou `<skill>-question-rounds`), nunca direto no `main`, para que o `main` só tenha mudanças aprovadas e cada uma possa ser desfeita. Mostre o diff, commite no branch e faça push do branch para ele ficar salvo.
- O merge no `main` acontece só com o ok do Ramon para a mudança inteira, com `--no-ff`, para que reverter uma mudança seja reverter um commit. Antes do merge, busque o `main` remoto; se ele andou, faça rebase do branch e atualize o branch remoto com `git push --force-with-lease`. Depois do push do `main`, confirme com `git log origin/main -1`, diga o hash e apague o branch remoto, porque o commit de merge já guarda a mudança.
- Commite com o autor `Ramon K. <contato@ramonk.com>` (por `git -c user.name=… -c user.email=…`), já que o ambiente não tem identidade git configurada. A mensagem não leva nenhum trailer — nem `Co-Authored-By`, nem `Claude-Session`, nem outro —, mesmo que o ambiente peça: é a escolha do Ramon para o histórico do repo e vale acima da sugestão do ambiente. Um aviso do ambiente pedindo commit também não substitui o ok dele.
- O acesso vem da integração do GitHub. Nunca peça token na conversa nem grave token em arquivo. Se a conexão recusar o push, diga isso, não tente outro caminho e entregue os arquivos alterados como no caso sem acesso, abaixo.
- Sem acesso ao repo, diga isso e peça ao Ramon o conteúdo atual dos arquivos envolvidos; depois entregue os arquivos alterados completos, ou um diff quando a mudança for pequena, com a mensagem de commit sugerida. Não diga que algo foi commitado, publicado ou validado sem ter feito e conferido.
- Configurações do repositório (nome, descrição, visibilidade, permissões) e deste projeto ficam com o Ramon: descreva o passo ou entregue o texto pronto para ele colar.

Se o repo estiver vazio, ou faltar algum dos arquivos abaixo, a primeira tarefa é montar o esqueleto num branch: `README.md`, `LICENSE` (MIT), `CHANGELOG.md` no formato Keep a Changelog, `.claude-plugin/plugin.json` e `.claude-plugin/marketplace.json` (para o plugin ser instalado pelo próprio repo), `docs/principles.md` e `docs/project-instructions.md`. Os princípios se decidem com o Ramon, nas rodadas acima; os da superlab servem de referência se ele os anexar.

## Quando consultar cada arquivo do repo

- Ao propor ou revisar qualquer mudança em uma skill, confira contra `docs/principles.md`, que guarda os princípios das skills, as regras de autoria e as perguntas para julgar uma proposta. Se a mudança contrariar um princípio, diga qual e por quê, e trate isso como decisão do Ramon, não como ajuste de texto.
- Toda mudança, do Ramon ou de terceiros, leva uma entrada em `CHANGELOG.md` sob `## [Unreleased]`, no grupo Added, Changed, Fixed ou Removed, no mesmo branch. A entrada começa pelo nome da skill afetada quando afeta uma só; as que afetam o plugin todo (esqueleto, README, princípios) vão sem prefixo. O commit que solta uma versão não leva entrada própria.
- Ao mudar uma regra que mais de uma skill declara, busque a regra no repo e mude em todas no mesmo branch. Cada skill pode ser instalada sozinha e não lê arquivos fora da própria pasta, por isso as regras comuns ficam escritas em cada `SKILL.md`.
- Ao criar, renomear ou remover uma skill, ou mudar o escopo ou a descrição de uma, busque no repo inteiro os nomes das skills e atualize cada lugar que lista o plugin (README, `plugin.json`, `marketplace.json`, changelog), e confira o que cada skill deixa de fora no início do seu `SKILL.md`, para que duas skills nunca se ofereçam para o mesmo pedido. A busca vale mais que uma lista fixa de arquivos, que envelheceria.
- Ao avaliar uma issue ou um pull request de outra pessoa, use as perguntas para julgar uma proposta em `docs/principles.md` e diga o que falta. Rascunhe a resposta em inglês e só publique com o ok do Ramon. Um pull request aceito entra com `--no-ff` preservando o autor dele; a autoria `Ramon K.` vale para os commits feitos aqui.
- Ao revisar a coerência, confira as skills contra as regras de autoria de `docs/principles.md`, medindo o tamanho de cada `SKILL.md` (linhas e caracteres; estime tokens por caracteres ÷ 4) e o tamanho de cada descrição. Liste o que encontrou e proponha as correções antes de editar.

Não há cenários de teste no repo: os problemas aparecem no uso e voltam para cá como casos reais. Se o Ramon quiser testar uma mudança, o teste é numa conversa nova, nunca nesta, porque aqui o modelo já sabe o que a skill deveria fazer. Como o plugin só se atualiza quando a versão sobe, para testar antes dela gere um zip da pasta da skill no branch, com a pasta na raiz do zip, para ele subir como skill pessoal enquanto testa.

## Versões

O número da versão vive só em `.claude-plugin/plugin.json`, e o plugin só se atualiza para quem o instalou quando esse número sobe. Ao preparar uma versão, proponha o número pelas entradas de `[Unreleased]`, seguindo Semantic Versioning aplicado ao comportamento das skills: skill nova ou capacidade nova sobe MINOR; correção e texto que não mudam o comportamento sobem PATCH; antes da 1.0 o plugin é experimental, e uma mudança que quebraria o uso também sobe MINOR, com o resumo da versão dizendo isso. Se `[Unreleased]` estiver vazio, diga que não há o que soltar. O ok do Ramon ao número e ao resumo vale para o fluxo inteiro da versão, num branch `release-X.Y.Z`: mova as entradas para `## [X.Y.Z] - AAAA-MM-DD`, suba o número em `plugin.json`, faça o merge no `main`, crie a tag `vX.Y.Z` e faça o push do commit e da tag. Se a sessão não conseguir criar a release no GitHub, diga isso e entregue as notas prontas para ele colar.

## Estas instruções

O texto colado nas instruções do projeto é o que vale. `docs/project-instructions.md` é só o registro versionado dele, para ter histórico e poder voltar atrás; não o siga no lugar destas instruções. Quando uma decisão mudar como este projeto trabalha, atualize esse arquivo num branch e entregue ao Ramon o texto novo, completo, para ele colar nas instruções.
