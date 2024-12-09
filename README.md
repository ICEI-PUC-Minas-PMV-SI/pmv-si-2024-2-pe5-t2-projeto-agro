# Projeto Agro

`CURSO: Sistemas de Informação`

`DISCIPLINA: Projeto - Projeto de Infraestrutura`

`Eixo: 5`

Neste trabalho, abordaremos o desenvolvimento de um projeto de infraestrutura de rede, essencial para a conectividade e o funcionamento eficiente de organizações modernas. O objetivo é criar uma estrutura de rede robusta, segura e escalável que atenda às necessidades específicas da empresa em questão, com foco na integração de unidades dispersas geograficamente e na otimização do fluxo de dados. A importância de uma infraestrutura bem planejada será destacada, considerando aspectos como confiabilidade, desempenho e segurança da informação. 

O projeto de infraestrutura de rede será dividido em duas partes principais: a sede e as filiais. A sede, localizada na capital, contará com 10 computadores distribuídos entre os setores Administrativo e Financeiro, Marketing e Vendas, Jurídico, Pesquisa e Logística. Cada uma das 3 filiais situadas no interior do estado terá 5 computadores. A estrutura de rede deverá garantir uma comunicação eficiente e segura entre a sede e as filiais, suportando as operações e facilitando o compartilhamento de informações.

## Integrantes

* Astor Franco de Sena Neto
* Carlos Eduardo Gonçalves dos Santos
* Fellipe Rodrigues dos Santos
* Jussara Ribeiro de Souza
* Laura Luana Bastos Rocha
* Paolla Alves Soares
* Samuel Marques Pereira

## Orientador

* Alexandre Teixeira

## ETAPA 1 - ANÁLISE, PLANEJAMENTO E PROTOTIPAÇÃO DA SOLUÇÃO

O projeto de infraestrutura de rede será dividido em duas partes principais: a sede e as filiais. A sede, localizada na capital, contará com 10 computadores distribuídos entre os setores Administrativo e Financeiro, Marketing e Vendas, Jurídico, Pesquisa e Logística. Cada uma das 3 filiais situadas no interior do estado terá 5 computadores. A estrutura de rede deverá garantir uma comunicação eficiente e segura entre a sede e as filiais, suportando as operações e facilitando o compartilhamento de informações. 

![links](https://github.com/user-attachments/assets/8be11c30-16bf-4ebf-8be8-3c9463df054c)
A imagem fornecida mostra uma planilha de links com a distribuição de largura de banda (LB) em kbps, necessária para diferentes aplicativos (APPs) em uma empresa com matriz e três filiais.

![cabeamento](https://github.com/user-attachments/assets/d2f0a0c0-6215-4b6a-a825-668e9c63b09a)
A planilha de cabeamento apresentada na imagem detalha todos os recursos necessários para montar a infraestrutura física de rede nas diferentes unidades da empresa, incluindo a Matriz e três filiais.

![projeto cisco pack](https://github.com/user-attachments/assets/744eb626-d8e4-4fc7-9006-2b4c32cab262)
A imagem acima ilustra o protótipo de rede desenvolvido no Cisco Packet Tracer, conectando a Matriz às três Filiais da empresa. O roteador central da Matriz (ISR4331) atua como ponto crítico de controle, gerenciando as conexões com as filiais. 

## ETAPA 2 - Preparação do Ambiente em Nuvem e Virtualização Local

![image](https://github.com/user-attachments/assets/d4284f1e-e8ff-490b-ae07-24f4ed3c5557)
No print acima vemos a página inicial do acesso remoto da AWS. 
O acesso remoto a uma instância EC2 na AWS é um processo crucial para administração e operação de servidores na nuvem. Ele permite que os usuários gerenciem suas instâncias de forma eficiente, independentemente da localização física. Ao se conectar a uma instância EC2, neste caso através de RDP (Remote Desktop Protocol, para servidores Windows), várias informações relevantes são apresentadas na tela inicial de acesso. 

![image](https://github.com/user-attachments/assets/2b253266-8fcb-44ac-a76b-363b3713b948)
No print acima vemos a criação de computadores dentro do Active Directory no ambiente de acesso remoto AWS que envolve o gerenciamento de identidades e recursos dentro de uma rede corporativa. Foram criados computadores dentro de cada filial e sede, a quantidade está de acordo a necessidade de cada local, 10 computadores para a sede e 5 computadores para cada filial. 

![image](https://github.com/user-attachments/assets/0dddced8-8861-410e-acce-bc5757c1112a)
No print acima vemos uma lista de usuários criados a partir do Active Directory (AD), os usuários são as identidades digitais que permitem o controle de acesso a recursos como servidores, aplicações e serviços de rede. Cada usuário possui um conjunto de permissões, políticas de segurança e credenciais, que podem ser personalizadas de acordo com as necessidades de sua função. 

Esses usuários serão designados para diferentes funções, e suas atribuições podem ser gerenciadas para garantir que tenham acesso apenas aos recursos que elegerem. 

![image](https://github.com/user-attachments/assets/56a470fc-f290-41a8-9088-97a1b38ca4e2)
Nos prints acima vemos o gerenciador de políticas de grupo, local onde dentre outras ações é possível configurar, editar, adicionar, habilitar as políticas de grupo do servidor. 

Políticas de grupo são um recurso que permite definir configurações centralizadas para implementação em todas as estações de trabalho e servidores de maneira propagada. Ou seja, através de uma máquina é possível configurar todas as outras que estiverem na rede. 

![image](https://github.com/user-attachments/assets/bbc93cd0-c081-461b-b53d-9c1afe73fa7a)
No print acima vemos o painel de instancias do AWS com a instância ProjetoAgroWebServer selecionada. Ao selecioná-la temos acesso a detalhes como ID, IP público e privado entre outros da mesma. 

![image](https://github.com/user-attachments/assets/cb007402-a6ad-4c3f-852e-031f65a28f14)
Criamos uma rede de nuvem privada virtual (VPC - Virtual Private Cloud) representando uma versão virtual de uma rede física, e 2 sub-redes públicas e 2 sub-redes privadas, que são recursos regionais e possuem intervalos de endereços IP associados a elas. 

Assim temos uma rede virtual semelhante a uma rede tradicional que seria operada em um data center próprio, com os benefícios de usar a infraestrutura escalonável da AWS. 

![image](https://github.com/user-attachments/assets/460f2738-0a31-4857-b43e-50c0441c0435)
Foram geradas regras para o controle do tráfego da entrada e saída dos recursos da instância. Sendo alocadas ao grupo de segurança duas regras de entrada e de saída: 

A regra de entrada para HTTP na porta 80, pertencente ao protocolo TCP, que tem como função permitir que os usuários possam acessar a aplicação web através de navegadores em qualquer endereço IP; 

A regra de entrada para RDP (Remote Desktop Protocol) na porta 3389, também pertencente ao protocolo TCP, é utilizada para permitir o acesso remoto a sistemas operacionais Windows na instância. 

## ETAPA 3 - Gerência e Monitoração de Ambientes de Redes

![image](https://github.com/user-attachments/assets/b35350d8-e771-40ec-b23d-4726b2cb1090)
Acrescentamos ao ambiente em nuvem novas portas de entrada e saída referentes ao protocolo Simple Network Management Protocol (SNMP), para comunicação de gerenciamento de rede. 

Sendo estas: 

Porta 161: Utilizada pelo SNMP (Simple Network Management Protocol) para comunicação entre o gerenciador SNMP e os agentes SNMP, permitindo a coleta e o monitoramento de dados de dispositivos de rede (como switches, roteadores, servidores etc.). 

Porta 162: Utilizada para SNMP Trap, que é a porta na qual o agente SNMP envia mensagens de alerta (trap messages) ao gerenciador SNMP, notificando sobre eventos ou mudanças no status de um dispositivo. 

![image](https://github.com/user-attachments/assets/4a34ec23-5126-43c1-9c62-c186ca13cd9b)
Como citado anteriormente, também habilitamos a função SNMP Server em nossa máquina virtual, permitindo o seu monitoramento, e de seu servidor, por outras máquinas (através de um sistema de gerenciamento de rede) que usam o protocolo SNMP para coletar informações e realizar ações de gerenciamento.  

Conseguindo assim monitorar e gerenciar o sistema operacional e seus recursos, permitindo que outras máquinas ou sistemas de gerenciamento consultem dados sobre o estado da máquina virtual. 


![image](https://github.com/user-attachments/assets/9b487d58-f0e7-42dc-80ff-79347d0dab6f)
Geramos um Network Map no Zabbix, usado para visualizar e monitorar a topologia da rede e a infraestrutura de TI de forma gráfica e intuitiva. Tendo uma representação visual da rede, o status de cada dispositivo presente nela em tempo real, a comunicação entre eles e identificação de possíveis falhas e alertas.  

O mapa pode exibir dispositivos, como servidores, switches, roteadores, firewalls e outros elementos da infraestrutura de TI. Cada um pode ser representado por ícones personalizados ou padrões, como caixas, círculos ou ícones de rede. Sendo possível a criação de links entre eles, além de mais informações sobre seus status clicando nos dispositivos. 

O que nos leva a visualização de uma aba com vários dados disponíveis, como o histórico de métricas, gráficos de performance ou logs de alertas. 

Essa visualização gráfica ajuda os administradores de sistemas a monitorarem o estado e a saúde dos dispositivos de rede de forma rápida e eficiente, facilitando a detecção de problemas e a solução rápida de falhas. 


![image](https://github.com/user-attachments/assets/fc5ca8af-5383-4777-adc5-3f05ab40bfe7)

![image](https://github.com/user-attachments/assets/b19a0d7a-d013-4a62-9a67-a29b34258a75)


![image](https://github.com/user-attachments/assets/30d2e53f-6063-4ff6-bdab-a698654d8aea)


## ETAPA 4 - Mecanismos de Segurança da Informação

![image](https://github.com/user-attachments/assets/1bb6f6af-d714-4c0e-99c6-00c23f78591b)

A cartilha de política da informação que é um documento que descreve de maneira clara e acessível as regras, diretrizes e práticas recomendadas para a segurança e o uso adequado das informações dentro de uma organização. 

Ela é uma versão simplificada e prática da política de segurança da informação, elaborada para ser compreendida por todos os membros da organização, desde a alta gestão até os funcionários de linha de frente. 

O objetivo de uma cartilha de política da informação é educar os colaboradores sobre como proteger as informações da empresa e como lidar com dados sensíveis, além de promover uma cultura de segurança da informação. Esse tipo de material geralmente inclui as normas e procedimentos essenciais, tornando as diretrizes mais fáceis de serem seguidas e lembradas no dia a dia. 
