# Projeto-Spring-Boot-Java

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/neliocursos/exemplo-readme/blob/main/LICENSE) 

Projeto utilizando o framework Spring para o gerenciamento de usuários de um sistema. Se tratará de um 
projeto backend baseado em Rest API.

## Projeto base com a estrutura Spring
- Maven
- Java, versão 17
- Versão do Spring: 3.2.4
- JAR packaging
- Add dependencies: Spring Web

## Passos do projeto
- Criar o projeto
- Implementar o modelo de domínio
- Mapeamento objeto-relacional com JPA
- Configurar o banco de dados H2
- Criar os endpoints da API REST

## Desenvolvimento moderno: relacional -> objeto -> json
![imagem](https://github.com/Ribeirosk8/Projeto-Spring-Boot-Java/blob/main/Objeto.png)

#### Configuração do Maven Resources Plugin

```xml
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>3.1.0</version>
</plugin>
```
####  Adicione as seguintes dependências no arquivo pom.xml

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>
```
#### Configurações do banco de dados
```
# Dados de conexão com o banco H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=

# Configuração do cliente web do banco H2
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Configuração para mostrar o SQL no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```
#### Implemente o método run, adicionando as seguintes linhas:
```sql
User u1 = new User(null, "Maria Brown", "maria@gmail.com", "988888888", "123456");
User u2 = new User(null, "Alex Green", "alex@gmail.com", "977777777", "123456");
userRepository.saveAll(Arrays.asList(u1, u2));
```




