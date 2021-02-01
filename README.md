**Dicas para escrita de testes básicos com PHPUnit**

Um teste sempre segue um estrutura padrão, que tem três partes:

 - A inicialização do cenário (Arrange ou Given)
 - A execução da regra de negócio (Act ou When)
 - A verificação do resultado (Assert ou Then)


Documentação para o **"Arrange Act Assert"**
http://wiki.c2.com/?ArrangeActAssert


Documentaçao para o **"Given When Then"**
https://martinfowler.com/bliki/GivenWhenThen.html


_O PHPUnit pode ser utilizado com o comando `vendor/bin/phpunit`_


**Uma classe de teste segue algumas regras:**

 - Começa com o nome da classe que está sendo testada e usa o sufixo _Test_, por exemplo: _AvaliadorTest_, em geral _ClasseASerTestadaTest_
 - A classe de teste deve estender a classe _TestCase_
 - O método de teste deve começa com _test_
 - O método de teste deve ter um nome que diz o que estamos testando


**Data Providers**

 Os provedores de dados permitem que "alimentemos" os testes com cenários diversos, sem repetir o código e os asserts


**Método setUp**

 É um método que é chamado antes de cada teste


 - Os provedores de dados sempre são executados antes do método `setup`
 - Caso queiramos executar algum código antes dos provedores de dados, existe o método `setUpBeforeClass`
 - Análogo ao `setUp` e `setUpBeforeClass`, existem os métodos `tearDown` e `tearDownAfterClass`, para executar um código após os testes.


**Sobre TDD, o Test Driven Development**
_o TDD define um ciclo de desenvolvimento guiado pelo teste:_
 - Escrevemos um teste, que ainda não vai passar.
 - Implementamos a funcionalidade, que faz o teste passar.
 - Refatoramos (melhoramos, simplificamos) o código.


O TDD ajuda que tenhamos um teste para cada funcionalidade
Ele também documenta e simplifica a classe

Que devemos implementar a funcionalidade em pequenos passos, chamados de baby steps, sempre guiados pelos testes.


**Como verificar que o código lança as exceções esperadas**
 - Em geral, exceções também fazem parte das regras de negócio e precisam ser verificadas.
 - Para tal o PHPUnit oferece os métodos expectException e expectExceptionMessage da classe TestCase:
     - _expectException(\NomeDaExcecao::class)_
     - _expectExceptionMessage(mensagemDeExcecao)_


http://testwarequality.blogspot.com/p/tenicas-de-teste.html