 
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
## Configurando o Kali 
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
