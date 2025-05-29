# Trabalho_2/documentação/p1

vamos colocar aqui, então, um roteador. Eu vou escolher um do tipo 2911, que vai servir para a nossa conexão de internet. Eu vou colocar um PC que vai simular aqui os usuários da nossa rede interna, e eu vou colocar o nosso servidor, que é aonde a empresa vai disponibilizar os serviços para internet e tudo o mais.

 Vamos fazer a conexão aqui desses elementos. Eu vou pegar esse PC e vou conectar a porta internet dele na Giga 1 do meu firewall. Eu vou conectar na Giga 2 do firewall o servidor, e vou conectar aqui na Giga 3 o roteador que vai servir como o nosso link de internet.

 Para que fique um pouco mais fácil da gente colocar os IPS aqui, para que a gente não se perca, eu vou anotar aqui no TXT e eu recomendo que vocês façam o mesmo aí. Então taí. Vamos colocar aqui que a Giga 1/1 do meu firewall vai ser a interface... Eu vou chamar de inside, e eu vou colocar o IP nela de 172.16.10.1. máscara “/24”. Giga 1/2 vai ser a minha interface de servidores.

 Normalmente a gente chama essa interface, onde conectam os servidores, onde tem algo que tem acesso à internet e não está na rede interna, a gente chama de DMZ, normalmente. Esse nome vocês vão ver bastante por aí. Então eu vou chamar de DMZ, vou colocar o IP aqui 189.100.100.1. A máscara pode ser “/24”, é uma máscara padrão aí.

 E na Giga 1/3 vai ser a minha outside. Também é comum que a gente chame de outside uma interface conectada ao mundo externo, uma interface externa à nossa rede. Não é obrigatório, mas são nomes, convenções de nomes que a gente costuma utilizar. Então eu vou colocar o IP nessa outside de 200.100.100.1. Pode ser a nossa “/24” aqui de máscara.

 Então lembrando, a nossa management 1/1 que a gente configurou no último vídeo, a nossa interface de gerenciamento em GMT. A gente colocou o IP nela de 172.16.20.1. Máscara “/24”. Está muito parecido o IP com a inside. Aqui a gente sabe que essa máscara “/24” vem até aqui. Então ela para aqui nesse número 10, é o endereço de rede, e o que tem para lá é endereço de host. Então a gente sabe que essas [XX-ininteligível-XX] são segmentos diferentes.

 Giga 1/1 inside. Vamos configurar aqui no nosso firewall. Então “configure terminal”, vou entrar na interface Giga 1/1. Name, quero dar um nome para ela. “Nin Nif inside”. Quero dar um IP para ela. O IP adress vai ser o nosso 172.16.10.1. Nossa máscara é “/24”. E vou habilitá-la, no shutdown.

 Vamos entrar agora na nossa interface Giga 1/2. Essa interface vai ter o IP de 189.100.100.1. Mesma máscara. O nome dela, o “Nin Nif” dela, vai ser DMZ, e eu vou dar um no shutdown.

 Vamos dar uma olhada no que falta para a gente configurar. Falta a nossa outside. Então, interface Giga 1/3 vai ter o IP adress de 200.100.100.1. Mesma máscara. “Nin Nif outside”. No shutdown. A interface até subiu aqui já.

 Eu posso dar o exit, saio do modo de configuração. E como que eu verifico essas configurações que a gente acabou de fazer aqui? Existem algumas formas. Eu posso dar um show running config, configuração que está rodando no meu equipamento. E aqui estão as configurações que a gente fez. O nome da interface, security level, a gente já entra nesse ponto aqui. E IP adress das três interfaces.

 Já fiz bastante configuração aqui. Vamos salvar isso? Como que eu salvo as configurações aqui no firewall? Eu posso usar o atalho write memory. Está salvo. Pode desligar, pode voltar, que eu não perco mais essas configurações.

 Coloquei o IP nas interfaces, eu preciso agora colocar o IP nos meus equipamentos para que tenham conectividade. Então eu venho aqui no PC e coloco o endereço IP na mesma rede. No caso da inside vai ser 172.16.10.2. Coloco a minha máscara. E o IP do gateway é o IP da interface do firewall. Então vai ser 172.16.10.1. Pronto.

 Vamos colocar o IP no servidor? Então eu venho aqui e coloco 189.100.100.2. Mesma máscara. E o endereço do gateway vai ser o IP da interface, no caso o DMZ do meu firewall. Pronto. Vamos deixar o roteador aqui um pouquinho mais para frente, vamos só testar essa conectividade. Eu já coloquei o IP nas interfaces, coloquei o IP nos equipamentos, então provavelmente eu já tenho conectividade entre esses elementos.

 Então, se eu vier aqui no meu firewall e disparar um ping para o IP do PC, por exemplo, 172.16.10.2. Provavelmente ele falhe no primeiro ping, e aí eu tenho sucesso a partir do momento que ele constrói aí a conexão, ele enxerga esse elemento e ele já consegue pingar, já tem a conectividade.

 Vamos fazer a mesma coisa para o nosso servidor. 189.100.100.2. Tenho conectividade. O que a gente fez, então? Colocamos IP nas interfaces, construímos aí a nossa rede interna. No casa eu coloquei um PC só, mas nessa rede interna a gente poderia ter vários dispositivos, impressoras, enfim. Aqui, para o nosso exemplo, vamos deixar um servidor só, um PC só na nossa rede interna.

 E o nosso servidor também já está pronto para receber as comunicações. Vamos dar uma olhadinha aqui nesse show running do firewall? Vocês viram aqui que entrou, meio que por padrão aí, meio que foi... A gente não configurou, mas isso entrou a partir do momento que a gente habilitou as interfaces, esse security level. Mas o que é isso? Para que isso serve aqui em cada interface?
