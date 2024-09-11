---
sidebar_position: 1
---

# IAM

Um dos componentes mais importantes quando estudamos segurança em nuvem é o gerenciamento de políticas e identidades, IAM (_Identity and Access Management_). Este componente é o responsável por definir e garantir que determinados recursos sejam acessados somente pelos usuários (ou serviços) apropriados. Para isso, a AWS possui um serviço com o mesmo nome que provê toda a infraestrutura necessária para configurar quem pode acessar determinados recursos de uma conta. A partir de agora, quando eu me referir à IAM, estarei me referenciando ao serviço da AWS e não necessariamente ao conceito mais amplo.

Ao criar uma conta da AWS, você inicia uma **conta root** que tem acesso à todos os recursos e serviços da sua conta. Isso é ótimo para facilitar uma configuração inicial da sua conta, mas acaba sendo um problema quando precisamos compartilhar o acesso de sua conta com terceiros pois – geralmente – você não vai querer compartilhar este nível de acesso da sua conta. Um usuário ou serviço poderia apagar todo um produto importante de uma empresa por acidente – ou com más intenções – em um piscar de olhos ou <a href="https://x.com/kmcquade3/status/1291801858676228098" target="_blank">ter acesso à dados sigilosos</a>, por exemplo. O IAM está ai justamente para resolver este problema, te permitindo **compartilhar acesso à determinados recursos de sua conta à terceiros de forma granular**. 

Usuários, serviços, grupos ou qualquer entidade que realiza alguma ação são chamados de **[identidades](#identidades-identities)** (_identities_, em inglês) e essas identidades podem ser associadas à uma ou mais **política(s)** (_policy(ies)_, em inglês) que determina quais ações esta identidade pode realizar.

## Notas rápidas sobre o IAM
- É um serviço gratuito
- É global e portanto não está limitado à uma região ou ponto de presença específico.
- Tem consistência eventual. Isto é, para conseguir obter uma alta disponibilidade, os dados são replicados a partir de um nó e as alterações feitas no serviço podem demorar algum tempo para ser replicado em outras regiões.
- Novos usuários, inicialmente, possuem nenhuma permissão ao serem criados.


## Identidades (Identities)

Como dito logo acima, uma identidade é uma entidade que realiza alguma ação na AWS. É importante notar que existem 4 tipos de identidades na AWS:

1. Usuário raiz (root user)
2. Usuário (user)
3. Grupos de usuários (group users)
4. Roles

### Usuário raiz (root user)

Como dito na [primeira seção](#), o usuário root é criado junto com a sua conta da AWS. Você acessa pelo e-mail e senha utilizados durante a criação da conta. Ela possui acesso à todos os recursos da sua AWS e **não** é recomendado que você a utilize no dia-a-dia. Além disso, é recomendado que você configure alguma autenticação de multi-fatores (MFA) para protegê-la de possíveis tentativas de invasão.

No mais, existem algumas <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html#root-user-tasks" target="_blank">poucas ações</a> que somente o usuário raiz consegue realizar mas não entrarei em detalhes pois são casos muito específicos e que geralmente não caem nos exames oficias da AWS. O importante a ser lembrado é que esta é a **primeira identidade a ser criada**, que **não é recomendado que a utilize no dia-a-dia** e que é **recomendado configurar algum método de MFA**.

### Usuários (user)

Os usuários são entidades que são criadas e representam, ou um humano que irá usar o sistema, ou alguma carga de trabalho (_workload_) que usa o IAM para interagir com a AWS. Todo usuário possue seu nome, suas credenciais e seus <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html">identificadores</a> e podem participar de um ou mais [grupos de usuários](#grupos-de-usuários-group-users).

[[WIP...]]

### Grupos de usuários (group users)

[[WIP...]]

### Roles

[[WIP...]]
- Podem fazer parte de um ou mais grupos
- Grupos não são aninhados.

### Usuários vs Roles

[[WIP...]]

