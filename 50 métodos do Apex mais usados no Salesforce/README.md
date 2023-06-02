# 30 métodos do Apex mais usados no Salesforce

| Método | Descrição | Exemplo |
| --- | --- | --- |
| `Database.query` | Executa uma consulta SOQL dinâmica | `List<Account> accounts = Database.query('SELECT Id FROM Account WHERE Name = :name');` |
| `System.debug` | Registra uma mensagem no log de depuração | `System.debug('Valor da variável: ' + variable);` |
| `System.assertEquals` | Verifica se dois valores são iguais em um teste de unidade | `System.assertEquals(expectedValue, actualValue);` |
| `System.assert` | Verifica se uma condição é verdadeira em um teste de unidade | `System.assert(condition);` |
| `System.runAs` | Executa um bloco de código como um usuário específico em um teste de unidade | `System.runAs(user) { // código aqui }` |
| `Test.startTest` | Marca o início de um bloco de teste em um teste de unidade | `Test.startTest(); // código aqui Test.stopTest();` |
| `Test.stopTest` | Marca o fim de um bloco de teste em um teste de unidade e executa todas as operações assíncronas pendentes | `Test.startTest(); // código aqui Test.stopTest();` |
| `ApexPages.currentPage` | Retorna a página atual do Visualforce | `PageReference pageRef = ApexPages.currentPage();` |
| `ApexPages.addMessage` | Adiciona uma mensagem à página atual do Visualforce | `ApexPages.addMessage(new ApexPages.Message(ApexPages.Severity.ERROR, 'Erro!'));` |
| `ApexPages.hasMessages` | Verifica se há mensagens na página atual do Visualforce | `Boolean hasMessages = ApexPages.hasMessages();` |
| `ApexPages.StandardController` | Controlador padrão do Visualforce para um objeto específico | `ApexPages.StandardController controller = new ApexPages.StandardController(account);` |
| `ApexPages.StandardSetController` | Controlador padrão do Visualforce para um conjunto de registros de um objeto específico | `ApexPages.StandardSetController controller = new ApexPages.StandardSetController(accounts);` |
| `PageReference.setRedirect` | Define se uma referência de página deve redirecionar ou não ao ser navegada | `pageRef.setRedirect(true);` |
| `PageReference.getParameters` | Retorna os parâmetros da URL de uma referência de página | `Map<String, String> params = pageRef.getParameters();` |
| `Schema.SObjectType.getDescribe` | Retorna informações sobre um tipo de objeto SObject específico | `Schema.DescribeSObjectResult describe = Account.SObjectType.getDescribe();` |
| `Schema.DescribeSObjectResult.fields.getMap` | Retorna um mapa de campos de um objeto SObject específico | `Map<String, Schema.SObjectField> fields = describe.fields.getMap();` |
| `Schema.SObjectField.getDescribe` | Retorna informações sobre um campo SObject específico | `Schema.DescribeFieldResult describe = field.getDescribe();` |
| `Schema.DescribeFieldResult.isAccessible` | Verifica se um campo SObject é acessível pelo usuário atual | `Boolean isAccessible = describe.isAccessible();` |
| `Schema.DescribeFieldResult.isUpdateable` | Verifica se um campo SObject é atualizável pelo usuário atual | `Boolean isUpdateable = describe.isUpdateable();` |
| `Schema.DescribeFieldResult.getPicklistValues` | Retorna os valores de lista de opções de um campo SObject específico | `List<Schema.PicklistEntry> picklistValues = describe.getPicklistValues();` |
| `String.valueOf` | Converte um valor para uma string | `String stringValue = String.valueOf(value);` |
| `String.format` | Formata uma string usando marcadores de posição e argumentos | `String formattedString = String.format('Olá, {0}!', new List<String>{name});` |
| `String.join` | Junta uma lista de strings usando um delimitador específico | `String joinedString = String.join(strings, ', ');` |
| `String.split` | Divide uma string em uma lista de strings usando um delimitador específico | `List<String> splitStrings = string.split(', ');` |
| `String.startsWith` | Verifica se uma string começa com um prefixo específico | `Boolean startsWithPrefix = string.startsWith(prefix);` |
| `String.endsWith` | Verifica se uma string termina com um sufixo específico | `Boolean endsWithSuffix = string.endsWith(suffix);` |
| `String.contains` | Verifica se uma string contém uma substring específica | `Boolean containsSubstring = string.contains(substring);` |
| `String.replace` | Substitui todas as ocorrências de uma substring por outra substring em uma string | `String replacedString = string.replace(oldSubstring, newSubstring);` |
| `String.replaceAll` | Substitui todas as ocorrências de uma expressão regular por outra substring em uma string | `String replacedString = string.replaceAll(regex, replacement);` |
| `String.substring` | Retorna uma substring de uma string a partir de um índice inicial até um índice final opcional | `String substring = string.substring(startIndex, endIndex);`


```java
// Database.query
String name = 'Acme';
List<Account> accounts = Database.query('SELECT Id FROM Account WHERE Name = :name');
System.debug('Accounts: ' + accounts);

// System.debug
String variable = 'valor';
System.debug('Valor da variável: ' + variable);

// System.assertEquals
Integer expectedValue = 5;
Integer actualValue = 2 + 3;
System.assertEquals(expectedValue, actualValue);

// System.assert
Boolean condition = 2 + 2 == 4;
System.assert(condition);

// System.runAs
User user = new User(Id = '005xxxxxxxxxxxxxxx');
System.runAs(user) {
    // código aqui
}

// Test.startTest e Test.stopTest
Test.startTest();
// código aqui
Test.stopTest();

// ApexPages.currentPage
PageReference pageRef = ApexPages.currentPage();
System.debug('Página atual: ' + pageRef);

// ApexPages.addMessage
ApexPages.addMessage(new ApexPages.Message(ApexPages.Severity.ERROR, 'Erro!'));

// ApexPages.hasMessages
Boolean hasMessages = ApexPages.hasMessages();
System.debug('Tem mensagens: ' + hasMessages);

// ApexPages.StandardController
Account account = new Account(Id = '001xxxxxxxxxxxxxxx');
ApexPages.StandardController controller = new ApexPages.StandardController(account);
System.debug('Controlador: ' + controller);

// ApexPages.StandardSetController
List<Account> accounts = [SELECT Id FROM Account];
ApexPages.StandardSetController controller = new ApexPages.StandardSetController(accounts);
System.debug('Controlador: ' + controller);

// PageReference.setRedirect
pageRef.setRedirect(true);

// PageReference.getParameters
Map<String, String> params = pageRef.getParameters();
System.debug('Parâmetros: ' + params);

// Schema.SObjectType.getDescribe
Schema.DescribeSObjectResult describe = Account.SObjectType.getDescribe();
System.debug('Descrição do objeto: ' + describe);

// Schema.DescribeSObjectResult.fields.getMap
Map<String, Schema.SObjectField> fields = describe.fields.getMap();
System.debug('Campos do objeto: ' + fields);

// Schema.SObjectField.getDescribe
Schema.SObjectField field = fields.get('Name');
Schema.DescribeFieldResult describe = field.getDescribe();
System.debug('Descrição do campo: ' + describe);

// Schema.DescribeFieldResult.isAccessible
Boolean isAccessible = describe.isAccessible();
System.debug('Campo acessível: ' + isAccessible);

// Schema.DescribeFieldResult.isUpdateable
Boolean isUpdateable = describe.isUpdateable();
System.debug('Campo atualizável: ' + isUpdateable);

// Schema.DescribeFieldResult.getPicklistValues
List<Schema.PicklistEntry> picklistValues = describe.getPicklistValues();
System.debug('Valores da lista de opções: ' + picklistValues);

// String.valueOf
Integer value = 123;
String stringValue = String.valueOf(value);
System.debug('Valor da string: ' + stringValue);

// String.format
String name = 'João';
String formattedString = String.format('Olá, {0}!', new List<String>{name});
System.debug('String formatada: ' + formattedString);

// String.join
List<String> strings = new List<String>{'um', 'dois', 'três'};
String joinedString = String.join(strings, ', ');
System.debug('String unida: ' + joinedString);

// String.split
String string = 'um, dois, três';
List<String> splitStrings = string.split(', ');
System.debug('Strings divididas: ' + splitStrings);

// String.startsWith
String prefix = 'um';
Boolean startsWithPrefix = string.startsWith(prefix);
System.debug('Começa com prefixo: ' + startsWithPrefix);

// String.endsWith
String suffix = 'três';
Boolean endsWithSuffix = string.endsWith(suffix);
System.debug('Termina com sufixo: ' + endsWithSuffix);

// String.contains
String substring = 'dois';
Boolean containsSubstring = string.contains(substring);
System.debug('Contém substring: ' + containsSubstring);

// String.replace
String oldSubstring = ', ';
String newSubstring = '; ';
String replacedString = string.replace(oldSubstring, newSubstring);
System.debug('String substituída: ' + replacedString);

// String.replaceAll
String regex = '\\d+';
String replacement = '#';
replacedString = string.replaceAll(regex, replacement);
System.debug('String substituída: ' + replacedString);

// String.substring
Integer startIndex = 3;
Integer endIndex = 7;
String substring1= string.substring(startIndex, endIndex);
System.debug('Substring: '+substring1);
```
