# 50 métodos do Apex mais usados no Salesforce

| Método                   | Descrição                                                   | Exemplo                                                                                      |
|--------------------------|-------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| clear()                  | Limpa todos os elementos de uma coleção.                     | `List<String> lista = new List<String>{'a', 'b', 'c'}; lista.clear();`                       |
| containsKey()            | Determina se um mapa contém uma determinada chave.           | `Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2}; mapa.containsKey('a');` |
| equalsIgnoreCase()       | Compara duas strings para igualdade, ignorando maiúsculas e minúsculas. | `String str1 = 'Olá'; String str2 = 'olá'; str1.equalsIgnoreCase(str2);`                   |
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

1. clear(): Limpa todos os elementos de uma coleção.
```apex
List<String> lista = new List<String>{'a', 'b', 'c'};
lista.clear();
system.debug(lista);
```

2. containsKey(): Determina se um mapa contém uma determinada chave.
```apex
Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2};
Boolean contemChave = mapa.containsKey('a');
system.debug(contemChave);
```

3. equalsIgnoreCase(): Compara duas strings para igualdade, ignorando maiúsculas e minúsculas.
```apex
String str1 = 'Olá';
String str2 = 'olá';
Boolean saoIguais = str1.equalsIgnoreCase(str2);
system.debug(saoIguais);
```

4. floatValue(): Retorna um valor float para um número fornecido.
```apex
Integer num = 10;
Float floatNum = num.floatValue();
system.debug(floatNum);
```

5. getClass(): Retorna a classe em tempo de execução de um objeto.
```apex
Account acc = new Account();
Type objType = acc.getClass();
system.debug(objType);
```

6. getInitialValue(): Retorna o valor padrão para um determinado campo de sObject.
```apex
SObjectField field = Account.Name;
Object defaultValue = field.getInitialValue();
system.debug(defaultValue);
```

7. getInstance(): Retorna uma nova instância de um sObject para o tipo de registro especificado.
```apex
Schema.SObjectType objType = Account.SObjectType;
Account acc = (Account)objType.newInstance();
system.debug(acc);
```

8. getValues(): Retorna os valores de um mapa como uma lista.
```apex
Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2};
List<Integer> valores = mapa.getValues();
system.debug(valores);
```

9. isEmpty() ou isNull(): Determina se uma string é nula ou vazia.
```apex
String str = '';
Boolean vazia = str.isEmpty();
system.debug(vazia);
```

10. merge(): Une uma lista de campos em uma única string.
```apex
List<String> campos = new List<String>{'Nome', 'Idade', 'Email'};
String mergedString = String.join(campos, ', ');
system.debug(mergedString);
```

11. putAll(): Adiciona todos os pares chave-valor de um mapa a outro mapa.
```apex
Map<String, Integer> mapa1 = new Map<String, Integer>{'a' => 1};
Map<String, Integer> mapa2 = new Map<String, Integer>{'b' => 2};
mapa1.putAll(mapa2);
system.debug(mapa1);
```

12. remove(key): Remove o mapeamento para a chave especificada do mapa, se presente, e retorna o valor correspondente.
```apex
Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2};
Integer valor = mapa.remove('a');
system.debug(valor);
```

13. round(): Arredonda um número para um número específico de casas decimais.
```apex
Decimal num = 3.14159;
Decimal roundedNum =

 num.round(2);
system.debug(roundedNum);
```

14. startsWithIgnoreCase(): Determina se uma string começa com uma determinada substring, ignorando maiúsculas e minúsculas.
```apex
String str = 'Olá, mundo';
Boolean startsWith = str.startsWithIgnoreCase('olá');
system.debug(startsWith);
```

15. substringAfter(): Retorna uma substring que ocorre após um determinado caractere ou substring.
```apex
String str = 'Olá, mundo';
String substring = str.substringAfter(', ');
system.debug(substring);
```

16. system.debug(): Imprime informações de depuração no log de depuração.
```apex
system.debug('Informações de depuração');
```

17. system.runAs(): Executa um bloco de código com as permissões de um usuário especificado.
```apex
User u = [SELECT Id FROM User WHERE Username = 'usuario@teste.com'];
System.runAs(u) {
    // Código a ser executado com as permissões do usuário especificado
    system.debug('Executando com as permissões do usuário: ' + UserInfo.getUserName());
}
```

18. system.assert(): Verifica se uma determinada condição é verdadeira e lança uma exceção se não for.
```apex
Integer a = 2;
Integer b = 3;
System.assert(a < b, 'A deve ser menor que B');
```

19. Assert.areNotEquals(): Verifica se dois valores não são iguais e lança uma exceção se forem.
```apex
Integer a = 2;
Integer b = 3;
System.assertEquals(a, b, 'A e B não devem ser iguais');
```

20. Assert.areEquals(): Verifica se dois valores são iguais e lança uma exceção se não forem.
```apex
Integer a = 2;
Integer b = 2;
System.assertEquals(a, b, 'A e B devem ser iguais');
```

21. Assert.isTrue(): Verifica se uma determinada condição é verdadeira e lança uma exceção se não for.
```apex
Boolean condition = true;
System.assertTrue(condition, 'A condição deve ser verdadeira');
```

22. Assert.isFalse(): Verifica se uma determinada condição é falsa e lança uma exceção se não for.
```apex
Boolean condition = false;
System.assertFalse(condition, 'A condição deve ser falsa');
```

23. system.today(): Retorna a data atual no fuso horário do usuário.
```apex
Date today = System.today();
system.debug(today);
```

24. system.now(): Retorna a data e hora atual no fuso horário do usuário.
```apex
Datetime now = System.now();
system.debug(now);
```

25. test.startTest(): Inicia um novo contexto de teste.
```apex
Test.startTest();
// Código de teste aqui
```

26. test.stopTest(): Encerra o contexto de teste atual.
```apex
Test.stopTest();
// Código após o contexto de teste
```

27. test.loadData(): Carrega dados de teste de recursos estáticos.
```apex
Test.loadData(Account.sObjectType, 'TestAccounts');
// Carrega dados de teste do arquivo CSV 'TestAccounts' para objetos Account
```

28. test.setMock(): Configura um serviço simulado para testes.
```apex
Test.setMock(HttpCalloutMock.class, new MyMockClass());
// Configura um mock de chamada de HTTP usando a classe MyMockClass
```

29. test.isRunningTest(): Determina se o código atual está sendo executado em um contexto de teste.
```apex
Boolean isRunning = Test.isRunningTest();
system.debug(isRunning);
```

30. JSON.deserializeUntyped(): Desserializa uma string JSON em um objeto sem verificação de tipo.
```apex
String jsonString = '{"name":"John","age":30,"city":"New York"}';
Object jsonObj = JSON.deserializeUntyped(jsonString);
system.debug(jsonObj);
```

31. JSON.deserializeStrict(): Desserializa uma string JSON em um objeto Apex com verificação de tipo rigorosa.
```apex
String jsonString = '{"name":"John","age":30,"city":"New York"}';
MyClass obj = (MyClass)JSON.deserializeStrict(jsonString, MyClass.class);
system.debug(obj);
```

32. JSON.deserializeWithDate(): Desserializa uma string JSON

 em um objeto Apex com tratamento de datas.
```apex
String jsonString = '{"date":"2023-01-01"}';
MyClass obj = (MyClass)JSON.deserializeWithDate(jsonString, MyClass.class);
system.debug(obj);
```

33. JSON.serializePrecisely(): Serializa um objeto Apex com precisão.
```apex
MyClass obj = new MyClass('John', 30);
String jsonString = JSON.serializePrecisely(obj);
system.debug(jsonString);
```

34. Math.PI: Retorna o valor de pi.
```apex
Double pi = Math.PI;
system.debug(pi);
```

35. Math.pow(): Retorna o resultado de elevar um número a uma determinada potência.
```apex
Double base = 2;
Double exponent = 3;
Double result = Math.pow(base, exponent);
system.debug(result);
```

36. Date.today(): Retorna a data atual no fuso horário do usuário.
```apex
Date today = Date.today();
system.debug(today);
```

37. DateTime.now(): Retorna a data e hora atual no fuso horário do usuário.
```apex
Datetime now = Datetime.now();
system.debug(now);
```

38. String.valueOf(): Converte um valor em uma representação de string.
```apex
Integer num = 42;
String str = String.valueOf(num);
system.debug(str);
```

39. List.size(): Retorna o número de elementos em uma lista.
```apex
List<String> lista = new List<String>{'a', 'b', 'c'};
Integer size = lista.size();
system.debug(size);
```

40. Set.contains(): Determina se um conjunto contém um determinado elemento.
```apex
Set<String> conjunto = new Set<String>{'a', 'b', 'c'};
Boolean contemElemento = conjunto.contains('a');
system.debug(contemElemento);
```

41. Map.isEmpty(): Determina se um mapa está vazio.
```apex
Map<String, Integer> mapa = new Map<String, Integer>();
Boolean vazio = mapa.isEmpty();
system.debug(vazio);
```

42. Integer.valueOf(): Converte uma string em um valor inteiro.
```apex
String str = '42';
Integer num = Integer.valueOf(str);
system.debug(num);
```

43. Double.isNaN(): Determina se um valor é NaN (Not a Number).
```apex
Double value = Double.valueOf('NaN');
Boolean isNaN = Double.isNaN(value);
system.debug(isNaN);
```

44. Boolean.valueOf(): Converte uma string em um valor booleano.
```apex
String str = 'true';
Boolean boolValue = Boolean.valueOf(str);
system.debug(boolValue);
```

45. String.isBlank(): Determina se uma string é nula ou contém apenas espaços em branco.
```apex
String str = '  ';
Boolean isBlank = str.isBlank();
system.debug(isBlank);
```

46. List.contains(): Determina se uma lista contém um determinado elemento.
```apex
List<Integer> lista = new List<Integer>{1, 2, 3};
Boolean contemElemento = lista.contains(2);
system.debug(contemElemento);
```

47. Set.size(): Retorna o número de elementos em um conjunto.
```apex
Set<String> conjunto = new Set<String>{'a', 'b', 'c'};
Integer size = conjunto.size();
system.debug(size);
```

48. Map.keySet(): Retorna as chaves de um mapa como um conjunto.
```apex
Map<String, Integer> mapa = new Map<String, Integer>{'a' => 1, 'b' => 2};
Set<String> chaves = mapa.keySet();
system.debug(chaves);
```

49. String.toLowerCase(): Converte uma string em minúsculas.
```apex
String str = 'Olá, Mundo';
String lowerCaseStr = str.toLowerCase();
system.debug(lowerCaseStr);
```

50. List.add(): Adiciona um elemento ao final de uma lista.
```apex
List<String> lista = new List<String>{'a', 'b', 'c'};
lista.add('d');
system.debug(lista);
```
