# AF (AVALIAÇÃO FINAL) - QUALIDADE E TESTE DE SOFTWARE
## OBJETIVO
Este repositorio tem como objetivo a demonstração das ferramentas de teste utilizadas atualmente, o BDD (Behavior-Driven Development). Para isso, foi utilizado o método de <a href="https://cucumber.io/docs/guides/api-automation/?lang=java">Cucumber</a>, cujo 
da suporte ao desenvolvimento do software orientado ao comportamento da aplicação.

## METODOLOGIA
### FERRAMENTAS UTILIZADAS
1. Eclipse IDE amplamente utilizada para desenvolvimento de software em Java e outras linguagens. Disponível em: https://www.eclipse.org/downloads/
2. Meaven Cucumber. Disponível em: https://mvnrepository.com/artifact/io.cucumber/cucumber-java
3. Meaven Cucumber JUnit. Disponível em: https://mvnrepository.com/artifact/info.cukes/cucumber-junit

### PASSOS
1. Primeiramente foi criado um projeto Meaven na IDE e instalado as depedências do Cucumber e Cucumber JUnit no `BDD/pom.xml`.
  1. Arquivo antes da configuração:
     ```
      <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>br.com.facens.qts</groupId>
      <artifactId>BDD</artifactId>
      <version>0.0.1-SNAPSHOT</version>
      </project>
     ```
  3. Arquivo após a configuração:
     ```
      <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>br.com.facens.qts</groupId>
      <artifactId>BDD</artifactId>
      <version>0.0.1-SNAPSHOT</version>
      <dependencies>
    	  <dependency>
    		    <groupId>info.cukes</groupId>
    		    <artifactId>cucumber-java</artifactId>
    		    <version>1.2.6</version>
    		</dependency>
    		<dependency>
    		    <groupId>info.cukes</groupId>
    		    <artifactId>cucumber-junit</artifactId>
    		    <version>1.2.6</version>
    		</dependency>
    	</dependencies>
      </project>
     ```

2. Especificação dos comportamentos, encontrado no arquivo `arquivo_teste.feature`:
   ```
    @tag
    Feature: Cliente faz saque de dinheiro Como um cliente,
      eu gostaria de sacar dinheiro em caixa eletronico,
      para que eu não tenha que esperar em uma fila do banco
    
    @tag1
    Scenario: Cliente especial com saldo negativo
        Given Um cliente especial com saldo atual de -200 reais
        When for solicitado um saque no valor de 100 reais
        Then deve efetuar o saque e atualizar o saldo da conta para -300 reais
        And check more outcomes
    
    @tag2
    Scenario Outline: Cliente comum com saldo negativo
        Given Um cliente comum com saldo atual de -200 reais
        When solicitado um saque de 200 reais
        Then não deve efetuar o saque e e deve retornar a mensagem Saldo insuficiente
   ```
3. Implementação dos teste: Neste processo foi executado pela IDE o arquivo executado e gerou os métodos necessários para efetuar a utilização, os quais foram implementados no arquivo `Conta.java` 
 <img src="https://github.com/flima21/AF_ContaBancaria/blob/main/ImagensBDD/Img3.png">
5. Para concluir como foi dado o retorno dos testes, foi criado uma nova classe chamada `Runner.java` , pois não era possível executar de maneira exclusíva e foi gerado o seguinte resultado com o JUNIT. <img src="https://github.com/flima21/AF_ContaBancaria/blob/main/ImagensBDD/Img1.png">
