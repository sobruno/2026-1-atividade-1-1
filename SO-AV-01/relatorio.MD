#Relatório da Atividade 1.1 Avaliativa - Sistemas Operacionais#
##Nome Completo: Elton Bruno dos Santos Lima

##Introdução
Este relatório documenta o processo de execução da Atividade 1.1 Avaliativa referente ao 1º Bimestre da disciplina de Sistemas Operacionais, do curso de TADS no CNAT-IFRN, sob a orientação do professor Leonardo Minora. O objetivo central desta prática foi construir um ambiente de desenvolvimento isolado para uma aplicação web utilizando Docker e o framework Django. Durante o processo, apliquei conceitos práticos de containerização, como a criação de um Dockerfile, a montagem de volumes para espelhar diretórios entre o sistema hospedeiro e o container, e o mapeamento de portas de rede para permitir o acesso externo à aplicação.

##Relato das atividades
A execução da prática foi dividida em quatro etapas principais, seguindo o roteiro proposto.

Inicialmente, realizei a preparação do projeto fazendo o fork do repositório da disciplina para a minha conta pessoal no GitHub e, em seguida, clonei o repositório para o VS Code. Dentro do diretório clonado, criei a pasta app e o arquivo requirements.txt.

Na segunda etapa, foquei na criação da imagem Docker. Escrevi o arquivo Dockerfile.dev utilizando a imagem base do Fedora, configurando o diretório de trabalho e automatizando a instalação das dependências do sistema (como fish, python3 e sqlite) e do próprio Django.
Após salvar o arquivo, construí a imagem com o comando docker build e iniciei o container de desenvolvimento mapeando a porta 8000 e montando o volume da pasta atual para a pasta /app dentro do container, utilizando o modo interativo com o terminal Fish.

###Build:
![](criando-imagem.png)

###Run:
![](run-docker.png)

Com o container rodando, passei para a terceira etapa: a criação e configuração da aplicação Django. Iniciei o projeto raiz e criei o aplicativo chamado webapp. Em seguida, configurei o banco de dados padrão (SQLite3), adicionei o webapp na lista de aplicativos instalados no settings.py e ajustei a variável ALLOWED_HOSTS para permitir todas as conexões. Realizei as migrações do banco de dados e criei o superusuário administrador.

###Iniciação do servidor Django:
![](criando-django.png)

###Criando aplicação:
![](criando-webapp.png)

###Migração do Banco de Dados:
![](migrando-bd.png)

###Criando superuser:
![](criando-superuser.png)

Ainda na etapa de configuração, editei o arquivo views.py para criar uma visualização simples. Por fim, configurei o roteamento criando o arquivo urls.py do aplicativo e o incluindo no arquivo de rotas principal do projeto.

Na última etapa, iniciei o servidor de desenvolvimento interno do Django. Acessei a aplicação através do navegador no meu sistema hospedeiro para validar o funcionamento do mapeamento de portas e do servidor.

###Página inicial:
![](tela-home.png)


###Página admin:
![](tela-admin.png)

###Página admin pós Logar:
![](tela-admin-log.png)

##Considerações finais
A experiência de configurar todo esse ecossistema com Docker foi muito enriquecedora. Como tenho bastante interesse e atuo com desenvolvimento web, entender a fundo a containerização e o mapeamento de volumes me dá uma base técnica muito mais sólida para gerenciar projetos futuros e lidar com infraestrutura. Isolar o ambiente de desenvolvimento não apenas previne conflitos na máquina hospedeira, mas também ajuda a manter uma organização rigorosa, algo que valorizo bastante tanto na construção de interfaces quanto na estruturação lógica e teste dos meus algoritmos.
A principal dificuldade durante a prática foi inicialmente ter de realizar a mudança de diretório para o "app/" pois acabou passando despercebido, mas que foi superada ao revisar os comandos propostos, a construção do relatório também trouxe dificuldades consigo, visto que não é uma tarefa habitual.
