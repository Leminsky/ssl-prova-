O comando mkdir -p /etc/ssl/certificates cria a estrutura de diretórios onde podem ficar armazenados certificados digitais usados por serviços TLS/SSL.
A opção -p faz com que o diretório seja criado mesmo que os diretórios “pais” ainda não existam e não gera erro se a pasta já existir, tornando o comando 
seguro de executar mais de uma vez.
Em seguida, cd /etc/ssl/certificates altera o diretório de trabalho atual para essa pasta, permitindo que os próximos comandos 
(como salvar, listar ou manipular arquivos .crt, .pem, etc.) sejam executados diretamente no local correto.
