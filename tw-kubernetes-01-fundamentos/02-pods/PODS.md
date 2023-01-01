## O que é um Pod?

Chamamos de Pod a menor estrutura dentro do nosso cluster Kubernetes. É aqui que executamos nossos containers.

Nós nunca vamos nos referenciar a um container diretamente dentro de uma arquitetura Kubernetes. Ao invés disso nos referenciar aos Pods. Eles são gerenciados por um replica set, que por sua vez é gerenciado por um deployment.

Quando falamos em escalabilidade dentro do Kubernetes estamos falando em replicação dos Pods por meio de um replica set.

Raramente você vai criar pods individuais diretamente no Kubernetes. Existem opções de utilizar recursos de cargas de trabalho como o replica set ou o deployment para criar vários pods de uma vez. Estes controladores possuem recursos para controle de replicação e também de falhas.

Quando acontece uma falha em um Pod, o controlador perceberá a falha e automaticamente criará um pod substituto.

Um Pod pode conter mais de um container. Neste caso eles vão ter recursos de rede compartilhados, já que utilizam o mesmo ip do pod, mesmo file manager e mesmo volume.

Já que é possível alocar vários containers dentro de um único pod, posso colocar toda minha aplicação dentro de um único pod? A resposta curta é sim. Isso é totalmente possível, porém não recomendado. Isso porque recursos como escalabilidade e automação de deploys não seriam bem aproveitados.

Imagine esse cenário, você identifica uma carga pesada numa determinada área de sua aplicação e precisa de mais desempenho nessa área. Vamos escalar nossa aplicação. Mas veja, escalar consiste em criar novos pods através do replica set. Dito isso, não temos como escalar uma área isolada sem escalar toda nossa aplicação.

O mesmo vai acontecer para a automação de deploys. Não vamos conseguir atualizar uma parte isolada sem atualizar todos os containers da nossa aplicação.

Na próxima aula vamos aprender como criar um pod individual.
