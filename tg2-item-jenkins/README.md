# TG2 - Item + testes no Jenkins

Este projeto organiza `Item.java` e `ItemTest.java` no padrão Maven. A classe de testes contém cinco métodos `@Test`.

## Testar localmente

Requisitos: JDK 17 ou superior e Maven 3.6.3 ou superior.

No diretório que contém `pom.xml`, execute:

```bash
mvn clean test
```

O resultado dos testes fica em `target/surefire-reports/`.

## Executar no Jenkins

1. Coloque todo o conteúdo deste diretório na raiz de um repositório Git (ou integre estes arquivos ao repositório do grupo, ajustando o `pom.xml` existente se necessário).
2. No agente Linux do Jenkins, disponibilize JDK 17+ e Maven no PATH. O pipeline usa `sh`; em agente Windows, substitua `sh` por `bat` no `Jenkinsfile`.
3. Crie um job **Pipeline** com a definição **Pipeline script from SCM**, selecione Git e informe a URL do repositório e a branch. Use `Jenkinsfile` como caminho do script.
4. Execute **Build Now**. Confira o console e o resultado em **Test Result**. O Jenkins deve mostrar 5 testes executados, sem falhas.

Para disparar o job após um `push`, configure o webhook do GitHub conforme a aula. O disparo automático depende da URL acessível do Jenkins e da configuração do job.

A AWS não é necessária para testar o código. Na aula ela hospeda o Jenkins; também é possível usar um servidor local ou outro ambiente acessível.
