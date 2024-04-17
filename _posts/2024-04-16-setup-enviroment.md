Para poder começar a contribuir para o kernel do linux, primeiro tivemos que seguir alguns tutoriais para configurar o ambiente de desenvolvimento.

Nesse post, irei falar especificamente desses 3 tutoriais aqui:

1. [Use QEMU and libvirt to setup a Linux kernel test environment](https://flusp.ime.usp.br/kernel/qemu-libvirt-setup/)
2. [Build the Linux kernel for ARM](https://flusp.ime.usp.br/kernel/build-linux-for-arm/)
3. [Introduction to kernel build configuration and modules](https://flusp.ime.usp.br/kernel/modules-intro/)

### Setup do ambiente de teste com QEMU e libvirt

O primeiro tutorial foi sobre configurar um ambiente de teste para o kernel Linux. Aprendemos sobre máquinas virtuais (VMs) e bibliotecas como o QEMU e libvirt, essenciais para o desenvolvimento do kernel. Configuramos uma VM Debian, criamos um script para inicializá-la e configuramos o acesso SSH para facilitar a interação. Tive alguns problemas nos passo a passo do tutorial, a maioria deles foram problemas de permissões, onde alguns bastavam rodar o comando com `sudo`, outros tinham que mudar recursivamente a permissão de pastas e arquivos. 


### Compilação do kernel para arquitetura ARM

O segundo tutorial era focado na compilação de um kernel Linux específico para a arquitetura ARM. A primeira parte envolveu baixar o subsistema IIO usando o Git, o que foi simples e direto. Em seguida, ao configurar o ambiente de compilação com a arquitetura ARM64 e instalar o compilador cruzado, enfrentei algumas dificuldades, pois tinha comandos que não estavam muito bem especificados onde deveriam ser rodados. No entanto, as instruções fornecidas pelos monitores foram úteis para entender o processo básico de compilação do kernel. Na hora de instalar os módulos do kernel na VM, tive algum problema para subir a VM com a nova imagem gerada do Kernel. Minha máquina virtual apenas congelava, assim que eu tentava rodar o script. Fiquei horas e horas tentando debugar, acabei passando pela monitoria online que foi dada,
e a unica solução encontrada foi importar o arquivo `.config` gerado pela máquina do monitor. Após isso, consegui prosseguir com o tutorial novamente.

### Introdução aos modulos do kernel

O terceiro tutorial era sobre como criar um módulo simples, configurar símbolos de configuração e até mesmo testar a funcionalidade em um ambiente virtualizado. Para fazer isso, precisávamos criar o arquivo de módulo, e colocar suas configurações e entradas em seus respectivos `Kconfig` e `Makefile`. Após isso, era necessário selecionar o módulo na lista de opções para conseguir compilá-lo, com o `menuconfig`. A partir dai, tive problemas com comandos que não estavam bem descritos onde eram para serem rodados também (e passei um bom tempo tentando descobrir). Depois, consegui fluir com o tutorial normalmente, e vi o módulo que criei dentro da minha VM. O mesmo para a parte de criar um módulo com as dependências. 


Agora, a próxima etapa é partir para o aprendizado do subsistema IIO, e subsequente contribuição real e envio de patch para os maintainers do kernel!