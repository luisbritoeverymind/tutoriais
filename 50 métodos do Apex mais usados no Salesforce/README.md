# 50 métodos do Apex mais usados no Salesforce

| Método                   | Descrição                                                   | Exemplo                                                                                      |
|--------------------------|-------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| clear()                  | Limpa todos os elementos de uma coleção.                     | `List<String> lista = new List<String>{'a', 'b', 'c'}; 
lista.clear();`                       |
| containsKey()            | Determina se um mapa contém uma determinada chave.           | `Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2}; 
mapa.containsKey('a');` |
| equalsIgnoreCase()       | Compara duas strings para igualdade, ignorando maiúsculas e minúsculas. | `String str1 = 'Olá'; String str2 = 'olá'; 
str1.equalsIgnoreCase(str2);`                   |
| floatValue()             | Retorna um valor float para um número fornecido.              | `Integer num = 10; Float floatNum = num.floatValue();`                                       |
| getClass()               | Retorna a classe em tempo de execução de um objeto.          | `Account acc = new Account(); Type objType = acc.getClass();`                                |
| getInitialValue()        | Retorna o valor padrão para um determinado campo do sObject. | `SObjectField field = Account.Name; Object defaultValue = field.getInitialValue();`          |
| getInstance()            | Retorna uma nova instância de um sObject para o tipo de registro especificado. | `Schema.SObjectType objType = Account.SObjectType; Account acc = (Account)objType.newInstance();` |
| getValues()              | Retorna os valores de um mapa como uma lista.                 | `Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2}; List<Integer> valores = mapa.getValues();` |
| isEmpty() ou isNull()    | Determina se uma string é nula ou vazia.                     | `String str = ''; Boolean vazia = str.isEmpty();`                                             |
| merge()                  | Mescla uma lista de campos em uma única string.               | `List<String> campos = new List<String>{'Nome', 'Idade', 'Email'}; String mergedString = String.join(campos, ', ');` |
| putAll()                 | Adiciona todos os pares chave-valor de um mapa em outro mapa. | `Map<String, Integer> mapa1 = new Map<String, Integer>{'a' => 1}; Map<String, Integer> mapa2 = new Map<String, Integer>{'b' => 2}; mapa1.putAll(mapa2);` |
| remove(key)              | Remove o mapeamento para a chave especificada do mapa, se presente, e retorna o valor correspondente. | `Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2}; Integer valor = mapa.remove('a');` |
| round()                  | Arredonda um número para um número específico de casas decimais. | `Decimal num = 3.14159; Decimal roundedNum = num.round(2);`                                  |
| startsWithIgnoreCase()   | Determina se uma string começa com uma determinada substring, ignorando maiúsculas e minúsculas. | `String str = 'Olá, mundo'; Boolean startsWith = str.startsWithIgnoreCase('olá');`             |
| substringAfter()         | Recupera uma substring que ocorre após um determinado caractere ou substring. | `String str = 'Olá, mundo'; String substring = str.substringAfter(', ');`                      |
| system.debug()           | Imprime informações de depuração no log de depuração.         | `String nome = 'John Doe'; system.debug('O nome é: ' + nome);`                                |
| system.runAs()           | Executa um bloco de código com as permissões de um usuário especificado. | ```User usuario = [SELECT Id FROM User WHERE Username = 'user@example.com' LIMIT 1]; system.runAs(usuario) { /* Código a ser executado com as permissões do usuário */ }``` |
| system.assert()          | Verifica se uma determinada condição é verdadeira e lança uma exceção se não for. | `Integer x = 10; system.assert(x > 0, 'x deve ser maior que zero');`                           |
| Assert.areNotEquals()    | Verifica se dois valores são diferentes e lança uma exceção se forem iguais. | `Integer x = 10; Integer y = 20; Assert.areNotEquals(x, y, 'x e y devem ser diferentes');`      |
| Assert.areEquals()       | Verifica se dois valores são iguais e lança uma exceção se forem diferentes. | `Integer x = 10; Integer y = 10; Assert.areEquals(x, y, 'x e y devem ser iguais');`             |
| Assert.isTrue()          | Verifica se uma determinada condição é verdadeira.            | `Boolean condicao = true; Assert.isTrue(condicao, 'A condição deve ser verdadeira');`          |
| Assert.isFalse()         | Verifica se uma determinada condição é falsa.                 | `Boolean condicao = false; Assert.isFalse(condicao, 'A condição deve ser falsa');`             |
| system.today()           | Retorna a data de hoje no fuso horário do usuário.            | `Date hoje = system.today();`                                                                  |
| system.now()             | Retorna a data e hora atual no fuso horário do usuário.       | `DateTime agora = system.now();`                                                              |
| test.startTest()         | Inicia um novo contexto de teste.                             | `test.startTest(); /* Código a ser testado */`                                                 |
| test.stopTest()          | Encerra o contexto de teste atual.                            | `test.stopTest();`                                                                            |
| test.loadData()          | Carrega dados de teste de recursos estáticos.                 | `test.loadData('StaticResourceName');`                                                        |
| test.setMock()           | Configura um serviço simulado para teste.                     | `Test.setMock(WebServiceMock.class, new MockResponseGenerator());`                             |
| test.isRunningTest()     | Determina se o código atual está sendo executado em um contexto de teste. | `Boolean runningTest = Test.isRunningTest();`                                              |
| JSON.deserializeUntyped() | Desserializa uma string JSON em um objeto sem verificação de tipo. | `String jsonString = '{"name":"John","age":30}'; Object jsonObj = JSON.deserializeUntyped(jsonString);` |
| JSON.deserializeStrict() | Desserializa uma string JSON em um objeto Apex com verificação de tipo rigorosa. | `String jsonString = '{"name":"John","age":30}'; CustomObject obj = (CustomObject)JSON.deserializeStrict(jsonString, CustomObject.class);` |
| JSON.deserializeWithDate() | Desserializa uma string JSON em um objeto Apex com manipulação de datas. | `String jsonString = '{"date":"2023-05-30"}'; CustomObject obj = (CustomObject)JSON.deserializeWithDate(jsonString, CustomObject.class);` |
| JSON.serializePrecisely() | Serializa um objeto Apex com precisão.                        | `CustomObject obj = new CustomObject(); String jsonString = JSON.serializePrecisely(obj);`      |
| Math.PI                  | Retorna o valor de pi.                                       | `Double pi = Math.PI;`                                                                         |
| Math.pow()               | Retorna o resultado de elevar um número a uma determinada potência. | `Double base = 2.0; Double expoente = 3.0; Double resultado = Math.pow(base, expoente);`       |


