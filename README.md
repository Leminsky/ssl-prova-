Nome: Guilherme Leme<br>
Ambiente: Oracle Virtual Box com Debian<br>
IP: 192.168.0.123 -VM<br>
    192.168.0.90 - Windows<br>
Dificuldades: A maior dificuldade encontrada foi no exercício 6, pois optei, por enviar o arquivo da minha máquina virtual para o windows, então precisei habilitar o ssl rodando essa sequência de comandos no windows :<br>

Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0<br>

Get-WindowsCapability -Online | ? Name -like 'OpenSSH.Server*'<br>

Get-Service sshd<br>

Start-Service sshd<br>

Set-Service sshd -StartupType Automatic<br>

New-NetFirewallRule -DisplayName "Allow ICMPv4 Echo" -Protocol ICMPv4 -IcmpType 8 -Direction Inbound -Action Allow<br>

New-NetFirewallRule -Name sshd -DisplayName "OpenSSH Server" -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22 <br>

Conclusão:Nesta atividade,configurei o ambiente com OpenSSL e executei o fluxo básico de uma infraestrutura TLS: criação de diretórios, geração de chave privada, emissão de CSR e criação de um certificado X.509 autoassinado, além de realizar a transferência do certificado via SCP. Também ficou claro, na prática, que HTTPS não é “apenas usar uma porta”: ao tentar acessar https://localhost:8443 com python3 -m http.server, ocorre erro porque o serviço entregue é HTTP puro e não realiza handshake TLS nem utiliza certificado. Por fim, a validação no navegador reforçou como verificar Subject, Issuer e validade e por que certificados autoassinados geram alertas de confiança. No geral, a atividade consolidou os conceitos essenciais de certificados digitais, cadeia de confiança e configuração correta de serviços para comunicação segura.




