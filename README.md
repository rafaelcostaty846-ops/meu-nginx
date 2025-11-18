Este projeto apresenta a criação e configuração de um ambiente Docker contendo um servidor NGINX personalizado, utilizando HTML próprio, volumes persistentes e integração com banco de dados MySQL através de rede personalizada.

1. Criação de uma imagem personalizada com NGINX

Foi desenvolvida uma imagem baseada em nginx:alpine, uma versão leve do NGINX.
O arquivo Dockerfile copia o conteúdo do diretório html/ para o local padrão do NGINX (/usr/share/nginx/html), permitindo exibir uma página HTML personalizada.

2. Página HTML personalizada

O arquivo index.html contém uma página simples com estilo visual moderno, exibindo a mensagem “Olá esse é Meu Nginx personalizado!”.
Essa página demonstra a personalização do servidor web.

3. Publicação via Docker Compose

O arquivo docker-compose.yml define os serviços e facilita a execução.
Ele foi configurado para:

Subir o servidor NGINX usando a imagem personalizada

Configurar portas externas para acesso pelo navegador

Usar volumes (quando configurado) para persistir arquivos, incluindo logs

4. Volume para persistência

O docker-compose utiliza volumes para garantir que arquivos importantes (como logs) não sejam perdidos quando o container é reiniciado.

5. Comunicação via rede personalizada

O ambiente Docker utiliza uma rede bridge personalizada, permitindo que o serviço NGINX se comunique com outros containers — como um futuro banco MySQL — de maneira segura e isolada.
