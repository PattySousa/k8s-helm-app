FROM nginx:alpine
LABEL maintainer="Patrícia Sousa"

# Copiar a página HTML para o diretório padrão do NGINX
COPY ./app /usr/share/nginx/html

# Rodar o NGINX com um usuário não-root
USER nginx
