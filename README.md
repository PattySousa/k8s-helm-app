k8s-helm-app

1- Preparando o Repositório Git

1a-Inicialmente, iniciei um repositósio no GitHub e GitLab e sincronizei com o VSCode. 

1b- Adicionei um diretório terminal do VSCode com nome k8s-helm-app, descrito abaixo: 

=> mkdir k8s-helm-app && cd k8s-helm-app
   git init

2-Crie a Aplicação Web Simples

2a- Criei uma página HTML simples (index.html) no diretório app do k8s-helm-app, com o seguinte comando no VSCode

=> mkdir app && cd app
   touch index.html



2b- Adicionei um script básico de html, no arquivo index.html, detalhado abaixo:   

  <!DOCTYPE html>
   <html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Aplicação</title>
</head>
<body>
    <h1>K8-Helm-App / Patricia Sousa</h1>
</body>
</html> 







2C- Instalei Helm e suas ferramentas, Kubernetes e Docker.


3-Crie o Dockerfile

3a-Criei no diretório principal k8s-helm-app um Dockerfile,
esta parte deu muito trabalho porque o VSCode não reconhecia
o Dockerfile baixado na máquina e tive que mexer várias vezes no caminho para adequar ao arquivo. Depois de muita pesquisa e leitura, utilizei estes comandos no terminal para criar o Dockerfile pelo VSCode. 

=> # Usando a imagem base do WordPress
   FROM wordpress:latest

   #Adicionando um grupo e um usuário não-root
   RUN addgroup --system appgroup && adduser --system --ingroup appgroup appuser

   #Definindo o diretório de trabalho
   WORKDIR /var/www/html

  #Copiando o arquivo index.html para o diretório de trabalho
   COPY ./dockerfile/app/index.html .

  #Alterando a propriedade dos arquivos para o usuário não-root
  RUN chown -R appuser:appgroup /var/www/html

  #Comando para iniciar o WordPress
  CMD ["apache2-foreground"]
  
  Enviei para o DockerHub




