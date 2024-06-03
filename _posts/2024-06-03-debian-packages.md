### Workshop pacotes Debian

Para o workshop de pacotes debian, tivemos o auxílio de Joenio Marques da Costa para conseguirmos criar um pacote Debian para bibliotecas Perl. Para isso, deveríamos seguir uma série de passos, onde fomos guiados pelo Joenio, para poder selecionar uma biblioteca para o empacotamento, desenvolver e configurar um pacote para a biblioteca escolhida, buildar o pacote e executar seus testes automatizados, e por final, submeter o pacote pro Debian Perl Group.

Eu e Roberto Bolgheroni trabalhamos juntos e escolhemos a biblioteca DateTime::Format::Atom para o nosso projeto. Como não tínhamos o Debian instalado em nossos sistemas, tivemos que encontrar soluções alternativas para construir e testar o pacote em um ambiente Debian.

Nossa primeira abordagem foi usar contêineres Docker. Este método parecia ideal devido à facilidade de configuração e à capacidade de aproveitar a configuração da máquina host enquanto realizávamos tarefas específicas do Debian dentro do contêiner. No entanto, tivemos alguns problemas com isso, principalmente com permissões do docker e do container, e quando achavamos que tinhamos resolvido uma coisa, aparecia outra. Dado todos os problemas, pensamos em criar e utilizar uma VM Debian por virtualbox.

Nossa configuração inicial de VM funcionou bem até chegarmos à etapa de construção do pacote. Havíamos alocado apenas 6 GB de espaço em disco para a VM, com ainda menos para a partição `/boot`. Como as dependências necessárias precisavam ser instaladas na partição `/boot`, e redimensioná-la não era simples, tivemos que começar tudo de novo.

Para a proxima tentativa decidimos alocar 20 GB de espaço em disco, o que permitiu construir o pacote com sucesso. Porém, tivemos problemas ao executar os testes automatizados do pacote. Conversamos com outros colegas, e vimos que eles também enfrentaram problemas semelhantes, e sem uma solução fácil à vista, decidimos direcionar nossos esforços para outras contribuições do curso.

Os arquivos nos quais trabalhamos durante esse processo estão disponíveis [aqui](https://drive.google.com/file/d/1TW8oGSmIOW6DuhfoYtpxRay4vZvdxxfO/view?usp=drive_link)