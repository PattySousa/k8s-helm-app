# Use a imagem base do NGINX
FROM nginx:alpine

# Crie um grupo e um usuário não-root
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Copie os arquivos da aplicação
COPY . /usr/share/nginx/html

# Mude a propriedade dos arquivos para o usuário não-root
RUN chown -R appuser:appgroup /usr/share/nginx/html

# Troque para o usuário não-root
USER appuser

# Exponha a porta da aplicação
EXPOSE 80

# Comando para rodar o servidor NGINX
CMD ["nginx", "-g", "daemon off;"]
