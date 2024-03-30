# firewall_iptables
Lista de exercício 

Objetivo

O objetivo deste firewall é garantir a segurança e o controle do tráfego de rede, permitindo apenas comunicações autorizadas e bloqueando acessos indesejados.

Configurações Principais

    Liberando tráfego para interface de loopback:
        Para permitir comunicação local, o tráfego na interface de loopback é permitido tanto na entrada quanto na saída.

    Política de Restrição:
        A política padrão para as chains INPUT e FORWARD da tabela filter é definida como DROP, o que implica que o tráfego não permitido será bloqueado por padrão.

    Permitindo Acesso ao Serviço WWW:
        Usuários da rede interna podem acessar serviços WWW (HTTP e HTTPS) nas portas 80 e 443.

    NAT (Network Address Translation):
        O firewall é configurado para realizar a tradução de endereços de origem (SNAT) para os dispositivos da rede interna que se conectam à Internet.

    Filtragem de Conteúdo:
        Acesso a sites com a palavra "games" é bloqueado, e tentativas de acesso a esses sites são registradas.

    Restrição de Acesso a Sites Específicos:
        O acesso ao site www.jogosonline.com.br é bloqueado para usuários da rede interna, exceto para o endereço IP específico do chefe.

    Limitação de Ping (ICMP echo-request):
        É permitido o recebimento de pacotes ICMP echo-request (ping), com uma limitação de 5 pacotes por segundo.

    Acesso ao DNS Externo:
        Tanto a rede interna quanto a DMZ podem realizar consultas ao DNS externo e receber os resultados das mesmas.

    Permitindo Tráfego para a DMZ:
        O tráfego TCP destinado à máquina na DMZ na porta 80 é permitido de qualquer rede (interna ou externa).

    Redirecionamento de Porta:
        Pacotes TCP destinados a um determinado IP e porta são redirecionados para outra máquina na DMZ.

    Permitindo Resposta na Porta 80:
        A máquina na DMZ pode responder aos pacotes TCP recebidos na porta 80 corretamente.

Como Utilizar

Para implementar estas regras de firewall, basta executar o script fornecido neste documento em um ambiente Linux que utilize iptables para o gerenciamento de firewall. Certifique-se de ter as permissões adequadas para executar o script, pois ele contém comandos que requerem privilégios de superusuário.

  $ sudo ./seu_script_firewall.sh
