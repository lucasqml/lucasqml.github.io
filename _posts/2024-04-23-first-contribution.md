### Introdução ao IIO 

Para poder ter um melhor dos modulos e iio segui esses três tutoriais disponiveis no flusp:

1. [Introduction to Linux kernel Character Device Drivers](https://flusp.ime.usp.br/kernel/char-drivers-intro/)
2. [https://flusp.ime.usp.br/iio/iio-dummy-anatomy/](https://flusp.ime.usp.br/iio/iio-dummy-anatomy/)
3. [IIO Dummy module Experiment One: Play with iio_dummy](https://flusp.ime.usp.br/iio/experiment-one-iio-dummy/)

Segui esses três tutoriais sem muitos problemas, pois já tinha setado o ambiente e feito a configuração anteriormente, então até que fluiu bem.

### Primeira contribuição para o kernel

Para nossa primeira contribuição para o kernel do linux, escolhemos conmtribuir ao subsistema IIO. 

Dentre as opções de patchs apresentadas, acabamos seguindo a opção 1, onde nosso foco foi melhorar o tratamento de erros em drivers que lidam com nós de firmware. 

Utilizamos uma função chamada `device_for_each_child_node_scoped()` para simplificar esse processo, garantindo a liberação correta de referências de nós mesmo em loops que terminam antes do previsto.

Em resumo, substituímos uma macro menos eficiente por outra mais recomendada, o que também simplificou o código e tornou o sistema mais robusto. Enviamos nosso patch para revisão e recebemos o feedback do monitor. Tinha alguns typos na descrição do nosso commit, que já arrumamos e enviamos aos mantenedores no linux.