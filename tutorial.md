 
Disciplina de Segurança e auditoria de sistemas

(Ciência da Computação - 9ª fase (Remoto) - Noturno - 2020/2) 

Profº. Dr. Emilio Wuerges
# Tutorial: Uso da ferramenta de Auditoria de Sistemas.
Acadêmicos: Maikon Douglas de Souza Pereira e Tatiane Arndt Barbosa.

![GitHub Logo](https://imagens.tiespecialistas.com.br/2016/05/seguranca_teclado_cadeado1-1280x720.jpg)


## INTRODUÇÃO

Todo o trabalho da auditoria de sistemas, ou seja, o uso das ferramentas de auditoria tem como objetivos,
de auxiliar o auditor, para que possam atingir suas metas, definidas no planejamento de auditoria, independente
do tipo de auditoria praticada. Riscos Tecnológicos é uma atividade independente que tem como missão o gerenciamento
de risco operacional envolvido e avaliar a adequação das tecnologias e sistemas de informação utilizados na organização através 
da revisão e avaliação dos controles, desenvolvimento de sistemas, procedimentos de TI, infraestrutura, operação, desempenho e 
Segurança da informação que envolve o processamento de informações críticas para a tomada de decisão. A auditoria de sistemas
é um processo realizado por profissionais capacitados e consiste em reunir, agrupar e avaliar evidências para determinar se um 
sistema de informação suporta adequadamente um ativo de negócio, mantendo a integridade dos dados, e realiza os objetivos esperados, 
utiliza eficientemente os recursos e cumpre com as regulamentações e leis estabelecidas. Ela contribui para a melhoria constante do 
negócio suportado pela Tecnologia, nos seguintes aspectos: 
**Desempenho; Confiabilidade; Integridade; Disponibilidade; Segurança; Confidencialidade; Privacidade.**

## APRENDENDO A USAR A FERRAMENTA
De acordo com Georgia Weidman ( 2014 - Pág. 09 - 14),  foi entendido como fazer os procedimentos e especificado abaixo, segundo o autor.
### Instalando VMware 
Como primeira etapa na configuração do seu laboratório virtual, baixe e instale um produto VMware de mesa.
O VMware Player está disponível gratuitamente para uso pessoal para Sistemas operacionais Microsoft Windows 
e Linux (http://www.vmware.com/produtos/jogador/). A VMware também oferece VMware Workstation (http://www.vmware.com/products/workstation/)
para Windows e Linux, que inclui 10 Capítulo 1 recursos adicionais, como a capacidade de tirar instantâneos do ambiente virtual máquina para 
a qual você pode reverter caso quebre algo. VMware Workstation está disponível gratuitamente por 30 dias, mas depois disso, você vai precisar 
comprá-lo ou voltar a usar o VMware Player. Os usuários de Mac podem executar uma versão de teste do VMware Fusion (http://www.vmware.com/products/fusion/)
grátis por 30 dias e custa apenas cerca de R $50 depois disso. 
### Configurando o Kali 
Linux Kali é uma distribuição Linux baseada em Debian que vem com uma ampla variedade de ferramentas de segurança pré-instaladas.
Para o Kali 1.0.6, a versão no momento testado. Você encontrará um link para um torrent contendo uma cópia do Kali 1.0.6 na página
deste livro site (http://nostarch.com/pentesting/). Com o passar do tempo, novas versões de Kali serão libertadas. Se desejar, sinta-se 
à vontade para baixar a versão mais recente do Kali Linux em http://www.kali.org/. Lembre-se, porém, que muitas das ferramentas que usaremos
neste texto estão em desenvolvimento ativo, portanto, se você usar uma versão mais recente de Kali. Se você preferir que tudo funcione como 
está escrito, recomendo usar a versão do Kali 1.0.6 fornecida no torrent (um arquivo chamado kali-linux-1.0.6-vm-i486.7z), que é uma imagem 
VMware pré-construída e compactada com 7-Zip. 

Você pode encontrar programas 7-Zip para plataformas Windows e Linux em http://www.7-zip.org/download.html. Para usuários de Mac, eu recomendo Ez7z 
de http://ez7z.en.softonic.com/mac/.
  
1. Assim que o arquivo 7-Zip for descompactado, em VMware vá para File -> Open e direcioná-lo para o arquivo Kali Linux 1.0.6 32 bit.vmx no descompactado Pasta Kali Linux 1.0.6 de 32 bits.
2. Assim que a máquina virtual abrir, clique no botão Play e, quando solicitado conforme mostrado na Figura 1-1, escolha Eu copiei.
3. Conforme o Kali Linux é inicializado, você será solicitado conforme mostrado na Figura Abaixo. Escolha a opção destacada superior (padrão).

![](https://user-images.githubusercontent.com/27319290/110725173-e5f5e480-81f5-11eb-8401-0d61eabb49ce.png)
 
 Abrindo a máquina virtual Kali Linux
 
 ![](https://user-images.githubusercontent.com/27319290/110725357-3ff6aa00-81f6-11eb-981c-3e1fd097d56f.png)
 
 Inicializando Kali Linux
  
4. Assim que o Kali Linux for inicializado, você verá uma tela de login como na figura abaixo.
![3](https://user-images.githubusercontent.com/27319290/110725532-85b37280-81f6-11eb-8840-d970d01dc093.png)

Tela de login Kali

5. Clique em Outro e insira as credenciais padrão para Kali Linux, root: toor, como na figura abaixo. Em seguida, clique no botão Login.

![4](https://user-images.githubusercontent.com/27319290/110725806-f9557f80-81f6-11eb-9178-84dba275347b.png)

Logando em Kali

6. Você verá uma tela como a mostrada na Figura abaixo.

![5](https://user-images.githubusercontent.com/27319290/110725879-19853e80-81f7-11eb-9d80-b3c4eb219181.png)

### A GUI do Kali Linux

#### Configurando a rede para sua máquina virtual
Como usaremos Kali Linux para atacar nossos sistemas de destino em uma rede, precisamos colocar todas as nossas máquinas virtuais na mesma rede virtual (veremos um exemplo de movimentação entre redes no Capítulo 13, que cobre a pós-exploração). VMware oferece três opções de rede virtual conexões: com ponte, NAT e host apenas. Você deve escolher a ponte opção, mas aqui estão algumas informações sobre cada um:

- A rede com ponte conecta a máquina virtual diretamente ao local da rede usando a mesma conexão do sistema host. Na medida em que a rede local está preocupada, nossa máquina virtual é apenas outro nó na rede com seu próprio endereço IP.
- NAT, abreviação de tradução de endereço de rede, configura uma rede privada no máquina host. A rede privada traduz o tráfego de saída da máquina virtual para a rede local. Na rede local, o tráfego de máquina virtual parece vir do IP da máquina host Morada.
- A rede somente de host limita a máquina virtual a uma rede privada local no host. A máquina virtual será capaz de se comunicar com outras máquinas virtuais na rede apenas do host, bem como o host máquina em si, mas não será capaz de enviar ou receber qualquer tráfego com a rede local ou a Internet.

### Burp Suite

![6](https://user-images.githubusercontent.com/27319290/110726107-9ca69480-81f7-11eb-96e9-7248f7ef876c.png)

O Burp Suite é uma ferramenta desenvolvida na linguagem Java pela organização PortsWigger com a finalidade de realizar testes de segurança em aplicações. Através desta ferramenta é possível interceptar requisições e respostas de aplicações Web, modificá-las, analisá-las ou coletá-las para outras finalidades. É uma plataforma integrada para a realização de testes de segurança em aplicações web. Suas diversas ferramentas funcionam perfeitamente em conjunto para apoiar todo o processo de testes, de mapeamento e análise de superfície de ataque de uma requisição inicial até encontrar e explorar vulnerabilidades de segurança.

Em testes de segurança em aplicações web, podemos usar um proxy para capturar pedidos e respostas entre o nosso navegador e a aplicação web para que possamos ver exatamente quais dados estão sendo transmitidos. Kali Linux vem com a versão gratuita do Burp Suite, uma plataforma de testes para aplicações web que inclui um recurso de proxy. O Burp inclui outros componentes úteis, tais como Burp Spider, que pode rastrear através da aplicação o conteúdo web e suas funcionalidades, e o Burp Repeater, que permite que você manipule e reenvie pedidos para o servidor. Por enquanto, vamos nos concentrar na Burp Proxy.

Além da função de Proxy, o Burp Suite tem outras funcionalidades:
- **Spider** – Faz o crawling na aplicação para descobrir o seu conteúdo e funcionalidades;
- **Scanner** – É usado para fazer scan de requisições HTTP automaticamente para achar vulnerabilidades de segurança;
- **Intruder** – Permite realizar ataques automatizados personalizados;
- **Repeater** – Usado para modificar manualmente e reenviar requisições HTTP específicas quantas vezes achar necessário;
- **Sequencer** – Usado para analisar a qualidade da aleatoriedade dos tokens de sessão de uma aplicação;
- **Decoder** – Permite transformar bits de dados de aplicativos usando codificação e decodificação de esquemas comuns.
- **Comparer** – Permite realizar uma comparação visual dos bits dos dados da aplicação para achar diferenças interessantes.
- **A ferramenta conta com uma versão gratuita (Community) que pode ser baixada através do link: https://portswigger.net/burp/communitydownload.**

De acordo com Diego Macêdo ( 2016),  foi entendido como fazer os procedimentos e especificado abaixo, segundo o autor.

1. Como usar: 


