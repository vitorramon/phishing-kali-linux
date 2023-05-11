# Phishing para captura de senhas do Facebook utilizando um página fake hospedada em um servidor no Sistema Operacional Kali Linux

Este conteúdo possui fins educativos e jamais deve ser usado para fins maliciosos. Utilize com sabedoria.
Ao acessar o Kali Linux em nossa VM, realizamos algumas configurações importantes para permitir a conexão externa. Primeiramente, definimos a placa de rede em modo bridge para receber um endereço IP que possa ser acessado externamente. Em seguida, acessamos o terminal e fizemos o login como usuário root utilizando o comando "sudo su" e inserindo a senha correspondente.
Após efetuar o login como root, acessamos a pasta raiz e utilizamos o comando "setoolkit", que nos forneceu um menu com diversas opções de ataques disponíveis para escolha.

1) Social-Engineering Attacks
2) Penetration Testing (Fast-Track)
3) Third Party Modules
4) Update the Social-Engineer Toolkit
5) Update SET configuration
6) Help, Credits, and About
99) Exit the Social-Engineer Toolkit

Nesta ocasião, optamos por utilizar a opção "1) Social-Engineering Attacks" que consiste em um método de ataque que visa explorar vulnerabilidades humanas para roubar dados sensíveis da vítima.

Em seguida, prosseguimos com a escolha do Vetor de Ataque, que oferece diversas opções para execução do ataque, tais como:

1) Spear-Phishing Attack Vectors
2) Website Attack Vectors
3) Infectious Media Generator
4) Create a Payload and Listener
5) Mass Mailer Attack
6) Arduino-Based Attack Vector
7) Wireless Access Point Attack Vector
8) QRCode Generator Attack Vector
9) Powershell Attack Vectors
10) Third Party Modules

Em seguida, vamos escolher o método do ataque, que tem como opções:

1) Java Applet Attack Method
2) Metasploit Browser Exploit Method
3) Credential Harvester Attack Method
4) Tabnabbing Attack Method
5) Web Jacking Attack Method
6) Multi-Attack Web Method
7) HTA Attack Method

O módulo de ataque Web é uma maneira única de utilizar vários ataques baseados na web para comprometer a vítima pretendida.
O método de ataque de Java Applet irá falsificar um Certificado Java e entregar um payload baseado em metasploit. Usa um applet Java personalizado criado por Thomas Werth para entregar o payload.
O método de exploração do navegador Metasploit utilizará seleções de exploits do navegador Metasploit através de um iframe e entregará um payload do Metasploit.
O método de coleta de credenciais utilizará clonagem da web de um site que possui um campo de nome de usuário e senha e coletará todas as informações postadas no site.
O método TabNabbing aguardará o usuário se mover para uma guia diferente e, em seguida, atualizará a página para algo diferente.
O método de ataque Web-Jacking foi introduzido por white_sheep, emgent. Este método utiliza substituições de iframes para fazer com que o URL destacado pareça legítimo. No entanto, quando clicado, uma janela aparece e é substituída pelo link malicioso. Você pode editar as configurações de substituição de links no set_config se estiver muito lento/rápido.
O método Multi-Attack adicionará uma combinação de ataques através do menu de ataque web. Por exemplo, você pode utilizar o Java Applet, o navegador Metasploit, o coletor de credenciais/Tabnabbing todos de uma só vez para ver qual é bem-sucedido.
O método de ataque HTA permitirá que você clone um site e execute a injeção de powershell por meio de arquivos HTA, que podem ser usados para exploração baseada em powershell do Windows através do navegador.

Dentre as opções para a captura de credenciais do usuário temos:

1) Web Templates
2) Site Cloner
3) Custom Import
 
O primeiro método permitirá que o SET importe uma lista de aplicativos web pré-definidos que ele pode utilizar dentro do ataque.
O segundo método clonará completamente um site de sua escolha e permitirá que você utilize os vetores de ataque dentro da mesma aplicação web que você estava tentando clonar.
O terceiro método permite que você importe seu próprio site, observe que você só deve ter um arquivo index.html ao usar a funcionalidade de importação de site.

Na situação de teste em que nos encontramos, optamos por hospedar o site clonado em nossa máquina virtual que contém o Kali Linux. Para isso, verificamos o endereço IP da VM por meio do comando "ifconfig" e utilizamos esse IP para o site clone escolhido.
Uma vez hospedado o site clone, é possível acessá-lo pelo navegador, onde a vítima será redirecionada para a página falsa e poderá fornecer suas credenciais. No terminal do Kali Linux, podemos observar a captura dessas informações, que serão exibidas em tempo real conforme são coletadas pelo ataque.


