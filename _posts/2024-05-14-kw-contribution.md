### Contribuição ao Kernel Workflow

Dentro do repositório GitHub do projeto, havia uma lista de problemas abertos para escolha. Olhamos pelas issues que tinham a label `good first issue`, optamos por resolver um problema na teoria simples, que solicitava renomear o comando para enviar patches de kw mail para kw send-patch. [#1027](https://github.com/kworkflow/kworkflow/issues/1027)

Acabou que a modificação não foi tão simples assim, pois não tinha bem claro onde deveríamos substituir as partes do `mail` para `send patch`. Tentamos rodar `ctrl` + `f` para procurar as ocorrências de `mail` mas isso também não ajudava muito, pois tem muitos lugares onde tem a palavra `mail` e que não são para serem substituidos.

Precisamos entender então todo fluxo do comando, para poder fazer as modificações. Para isso também, compareci a monitoria onde o David me ajudou bastante nessa parte.

Nosso [Pull Request](https://github.com/kworkflow/kworkflow/pull/1105) está atualmente aberto e aguardando revisão.