# Usando a imagem base do WordPress
FROM wordpress:latest

# Adicionando um grupo e um usuário não-root
RUN addgroup --system appgroup && adduser --system --ingroup appgroup appuser

# Definindo o diretório de trabalho
WORKDIR /var/www/html

# Copiando o arquivo index.html para o diretório de trabalho
COPY ./dockerfile/app/index.html .

# Alterando a propriedade dos arquivos para o usuário não-root
RUN chown -R appuser:appgroup /var/www/html

# Comando para iniciar o WordPress
CMD ["apache2-foreground"]
