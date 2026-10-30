Amazon EFS: Shared File Storage with EC2

Laboratório prático de armazenamento compartilhado na AWS, utilizando Amazon Elastic File System (EFS) integrado a duas instâncias Amazon EC2. O projeto demonstra como disponibilizar arquivos para múltiplos servidores por meio de um sistema de arquivos de rede.

Para validar o funcionamento, foi utilizada a aplicação web FileGator, permitindo realizar operações de upload e download de arquivos pelo navegador.

Objetivo

Implementar uma arquitetura de armazenamento compartilhado em que duas instâncias EC2 acessem os mesmos arquivos por meio de um sistema de arquivos Amazon EFS.

O laboratório também explora configurações de rede, controle de acesso, gerenciamento de instâncias e integração de uma aplicação web com armazenamento compartilhado.

Arquitetura

A solução utiliza duas instâncias EC2 conectadas ao mesmo sistema de arquivos Amazon EFS. Cada instância executa o Apache, o PHP e o FileGator, enquanto o EFS centraliza os arquivos enviados pela aplicação.

<img width="1672" height="941" alt="c7a36930-34f3-4762-95ad-f49706b8b4ba" src="https://github.com/user-attachments/assets/5c4b7206-7c9f-4a39-81a1-a4b47e90972f" />


Componentes da arquitetura

Amazon EC2: Executa as aplicações web.

Amazon EFS:  Disponibiliza o sistema de arquivos compartilhado entre as instâncias.

Mount Targets:  Permitem a conectividade de rede das instâncias com o EFS.

Amazon VPC:  Fornece o ambiente de rede para os recursos.

Security Groups:  Controlam o tráfego de rede permitido.

AWS IAM:  Gerencia as permissões associadas às instâncias.

AWS Systems Manager Session Manager:  Permite acessar o terminal das instâncias sem depender de chaves SSH.

Apache:  Disponibiliza a aplicação web por HTTP.

PHP:  Fornece o ambiente de execução necessário ao FileGator.

FileGator:  Interface web para gerenciamento de arquivos.

Serviços e tecnologias utilizados

Amazon Web Services (AWS)
Amazon EC2
Amazon Elastic File System (EFS)
Amazon VPC
AWS IAM
AWS Systems Manager Session Manager
Security Groups
Amazon Linux 2023
Linux
Apache HTTP Server
PHP
FileGator

Evidências

Destinos de montagem do EFS

<img width="1567" height="572" alt="Design sem nome (2)" src="https://github.com/user-attachments/assets/7022da9c-38e2-41e0-9097-2b744084072c" />



Instâncias EC2

<img width="1236" height="273" alt="Design sem nome (4)" src="https://github.com/user-attachments/assets/253792a2-b3bc-4c28-8109-274144cb3635" />


Teste de armazenamento compartilhado

<img width="1599" height="865" alt="Design sem nome (6)" src="https://github.com/user-attachments/assets/ad3fed10-24f4-45e1-831d-73b0e89c73d6" />

<img width="1600" height="867" alt="Design sem nome (7)" src="https://github.com/user-attachments/assets/682afdaa-a300-4d0e-aea6-4b8dcfda63d9" />


Segurança e boas práticas

Durante a implementação, foram explorados mecanismos de controle de acesso e conectividade da AWS.

Os principais pontos de atenção para uma implementação mais próxima de produção são:

  Restringir o tráfego NFS à origem autorizada.
  
  Aplicar o princípio do menor privilégio nas permissões IAM.
  
  Evitar permissões amplas como chmod 777.
  
  Proteger o acesso à aplicação web com HTTPS.
  
  Alterar as credenciais padrão do FileGator antes de disponibilizar a aplicação.
  
  Evitar a exposição pública desnecessária das instâncias.
  
  Avaliar o uso de políticas de acesso do EFS e criptografia em repouso e em trânsito.
  
  Revisar os custos de armazenamento, backups e recursos de rede.
  
  O laboratório utiliza HTTP e permissões simplificadas para fins educacionais. Essas configurações não devem ser consideradas uma arquitetura de produção pronta para uso.


Principais aprendizados

Configuração de um sistema de arquivos de rede com Amazon EFS.

Diferenças práticas entre armazenamento local da instância e armazenamento compartilhado.

Integração entre EC2 e EFS.

Configuração de destinos de montagem em diferentes zonas de disponibilidade.

Controle de tráfego NFS com Security Groups.

Acesso administrativo a instâncias com AWS Systems Manager Session Manager.

Configuração de serviços web no Amazon Linux 2023.

Utilização de links simbólicos no Linux.

Validação do compartilhamento de arquivos entre instâncias.

Conclusão

O laboratório explora o uso do Amazon EFS como camada de armazenamento compartilhado para aplicações executadas em múltiplas instâncias EC2.

A integração com o FileGator permite demonstrar, de forma prática, como dois servidores podem acessar o mesmo conjunto de arquivos sem depender de cópias independentes armazenadas localmente em cada instância.

A atividade contribui para a compreensão de armazenamento em rede, configuração de infraestrutura AWS, controle de acesso e integração entre serviços de nuvem.

Projeto educacional desenvolvido para fins de estudo e prática em Cloud Computing com AWS.
