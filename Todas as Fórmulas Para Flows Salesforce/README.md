# Lista de todas as fórmulas disponíveis para o Salesforce Flow

```sql
SELECT Function.Name, Function.Label, Function.Description, Function.ExampleString
FROM FormulaFunctionAllowedType where Type='Flow'
```

| Função | Descrição | Exemplo | 
| --- | --- | --- |
| ABS | Retorna o valor absoluto de um número, ou seja, um número sem o seu sinal | ABS(number)| 
| ACOS | Retorna o arco cosseno do número em radianos, se o número informado estiver entre -1 e 1. Caso contrário, NULL. | ACOS(number)| 
| ADDMONTHS | Adiciona o número de meses à data, usando a última data do mês se a data for o último dia do mês ou os meses adicionados tiverem menos dias. | ADDMONTHS(date,num)| 
| AND | Verifica se todos os argumentos são verdadeiros e retorna TRUE (se todos os argumentos forem verdadeiros) | AND(logical1,logical2,...)| 
| ASCII | Retorna o primeiro ponto de código de caractere da string informada como um número. | ASCII(text)| 
| ASIN | Retorna o arco seno do número em radianos, se o número informado estiver entre -1 e 1. Caso contrário, NULL. | ASIN(number)| 
| ATAN | Retorna o arco tangente do número em radianos. | ATAN(number)| 
| ATAN2 | Retorna o arco tangente do cociente de y e x em radianos. | ATAN2(y, x)| 
| BEGINS | Verifica se o texto começa com os caracteres especificados e retorna TRUE se isso acontecer. Caso contrário, retorna FALSE. | BEGINS(text, compare_text)| 
| BLANKVALUE | Verifica se a expressão está em branco e retorna substitute_expression se estiver em branco. Se a expressão não estiver em branco, retornará o valor da expressão original. | BLANKVALUE(expression, substitute_expression)| 
| BR | Insere uma marca de quebra HTML nas fórmulas de string | BR()| 
| CASE | Verifica uma expressão em relação a uma série de valores. Se a expressão for igual a qualquer valor, retornará o resultado correspondente. Se ela não for igual a nenhum dos valores, retornará outro resultado | CASE(expression, value1, result1, value2, result2,...,else_result)| 
| CASESAFEID | Converte um ID de 15 caracteres em um ID de 18 caracteres que diferencia maiúsculas de minúsculas | CASESAFEID(id)| 
| CEILING | Arredonda um número para o número inteiro imediatamente superior, na direção oposta ao zero se for negativo | CEILING(number)| 
| CHR | Retorna uma string com o primeiro ponto de código de caractere como o número informado. | CHR(number)| 
| CONTAINS | Verifica se o texto contém os caracteres especificados e retorna TRUE se isso acontecer.  Caso contrário, retorna FALSO. | CONTAINS(text, compare_text)| 
| COS | Retorna o cosseno do número, em que o número é dado em radianos | COS(number)| 
| CURRENCYRATE | Retorna a taxa de conversão do CurrencyIsoCode fornecido para a moeda corporativa, ou 1,0 se a moeda for inválida. | CURRENCYRATE(IsoCode)| 
| DATE | Cria uma data a partir de um ano, mês e dia | DATE(year,month,day)| 
| DATETIMEVALUE | Retorna um valor de ano, mês, dia e horário GMT | DATETIMEVALUE(expression)| 
| DATEVALUE | Cria uma data a partir de sua data/hora ou representação textual | DATEVALUE(expression)| 
| DAY | Retorna o dia do mês, um número entre 1 e 31 | DAY(date)| 
| DAYOFYEAR | Retorna o dia do ano do calendário (de 1-366). | DAYOFYEAR(date)| 
| DISTANCE | Retorna a distância entre dois locais usando a unidade fornecida. | DISTANCE(location, location, unit)| 
| EXP | Retorna e elevado à potência de determinado número | EXP(number)| 
| FIND | Retorna a posição da string search_text no texto | FIND(search_text, text [, start_num])| 
| FLOOR | Arredonda um número para o menor número inteiro mais próximo, aproximando-se de zero | FLOOR(number)| 
| FORMATDURATION | Formata o número de segundos com dias opcionais ou a diferença entre horas ou dateTimes como HH:MM:SS. | FORMATDURATION(numSeconds[, includeDays] | dateTime/time, dateTime/time)| 
| FROMUNIXTIME | Retorna a data e hora que representa o número informado como os segundos decorridos desde 1º de janeiro de 1970. | FROMUNIXTIME(number)| 
| GEOLOCATION | Retorna um local com base na latitude e longitude fornecidas. | GEOLOCATION(latitude, longitude)| 
| GETSESSIONID | Retorna o ID da sessão atual. Isso pode ser útil nos hiperlinks para outros aplicativos que usam as credenciais da salesforce.com para autenticação | GETSESSIONID()| 
| HTMLENCODE | Codifica o texto e mescla os valores do campo para uso em HTML | HTMLENCODE(text)| 
| HYPERLINK | Cria um hiperlink | HYPERLINK(url, friendly_name [, target])| 
| IF | Verifica se uma condição é verdadeira e retornará um valor se for TRUE e outro valor se for FALSE. | IF(logical_test, value_if_true, value_if_false)| 
| INCLUDES | Determina se qualquer valor selecionado em um campo de lista de seleção múltipla seja igual a um texto literal que você especificar. | INCLUDES(multiselect_picklist_field, text_literal)| 
| INITCAP | Retorna o texto como minúscula com o primeiro caractere de cada palavra maiúsculo. | INITCAP(text)| 
| ISBLANK | Verifica se uma expressão está em branco e retorna TRUE ou FALSE | ISBLANK(expression)| 
| ISNULL | Verifica se uma expressão é nula e retorna TRUE ou FALSE | ISNULL(expression)| 
| ISNUMBER | Retorna TRUE se o valor do texto for numérico. Caso contrário, retorna FALSE. | ISNUMBER(Text)| 
| ISOWEEK | Retorna o número da semana ISO 8601 para a data informada (de 1-53) de modo que a primeira semana comece na segunda-feira. | ISOWEEK(date)| 
| ISOYEAR | Retorna a numeração de semana ISO 8601 com ano de quatro dígitos para a data informada de modo que o primeiro dia seja uma segunda-feira. | ISOYEAR(date)| 
| ISPICKVAL | Verifica se o valor de um campo de lista de opções é igual a um literal de string | ISPICKVAL(picklist_field, text_literal)| 
| JSENCODE | Codifica o texto e mescla os valores do campo para uso em JavaScript | JSENCODE(text)| 
| JSINHTMLENCODE | Codifica o texto e mescla os valores do campo para uso em JavaScript em marcas HTML | JSINHTMLENCODE(text)| 
| LEFT | Retorna o número especificado de caracteres do início de uma string de texto | LEFT(text, num_chars)| 
| LEN | Retorna o número de caracteres de uma string de texto | LEN(text)| 
| LINKTO | Retorna o HTML do elemento de link do destino selecionado com entradas opcionais expressas como parâmetros de consulta | LINKTO(label, target, id, [inputs], [no override])| 
| LN | Retorna o logaritmo natural de um número | LN(number)| 
| LOG | Retorna o logaritmo de base 10 de n | LOG(number)| 
| LOWER | Converte em minúsculas todas as letras do valor | LOWER(text)| 
| LPAD | Preencha o lado esquerdo do valor com espaços ou com a string de preenchimento opcional, de modo que o tamanho fique como padded_length | LPAD(text, padded_length [, pad_string])| 
| MAX | Retorna o maior de todos os argumentos | MAX(number,number,...)| 
| MCEILING | Arredonda um número para o número inteiro imediatamente superior, na direção de zero se for negativo | MCEILING(number)| 
| MFLOOR | Arredonda um número para o número inteiro imediatamente inferior, na direção oposta ao zero se for negativo | MFLOOR(number)| 
| MID | Retorna caracteres do meio de uma string de texto, dada uma posição inicial e um comprimento | MID(text, start_num, num_chars)| 
| MIN | Retorna o menor de todos os argumentos | MIN(number,number,...)| 
| MOD | Retorna o restante após um número ter sido dividido por um divisor | MOD(number,divisor)| 
| MONTH | Retorna o mês, um número entre 1 (janeiro) e 12 (dezembro) | MONTH(date)| 
| NOT | Altera FALSE para TRUE ou TRUE para FALSE | NOT(logical)| 
| NOW | Retorna uma data/hora representando o momento atual | NOW()| 
| NULLVALUE | Verifica se a expressão é nula e retorna substitute_expression se for nula. Se a expressão não for nula, retornará o valor da expressão original. | NULLVALUE(expression, substitute_expression)| 
| OR | Verifica se algum dos argumentos é verdadeiro e retorna TRUE ou FALSE.  Retornará FALSE somente se todos os argumentos forem falsos | OR(logical1,logical2,...)| 
| PI | PI de devoluções | PI()| 
| PICKLISTCOUNT | Retorna o número de valores selecionados em uma lista de opções de seleção múltipla. | PICKLISTCOUNT(multiselect_picklist_field)| 
| PREDICT | Retorna uma previsão do Einstein Discovery com base no ID do registro ou em uma lista de campos e seus valores. | PREDICT(PredDefId, [recordId] | [field, value, ...])| 
| REGEX | Retorna TRUE se o texto corresponder à expressão regular RegEx_Text. Caso contrário, retorna FALSE. | REGEX(Text, RegEx_Text)| 
| REVERSE | Retorna a string de texto na ordem reversa | REVERSE(text)| 
| RIGHT | Retorna o número especificado de caracteres do fim de uma string de texto | RIGHT(text, num_chars)| 
| ROUND | Arredonda um número para um número de dígitos especificado | ROUND(number,num_digits)| 
| RPAD | Preencha o lado direito do valor com espaços ou com a string de preenchimento opcional, de modo que o tamanho fique como padded_length | RPAD(text, padded_length [, pad_string])| 
| SIN | Retorna o seno do número, em que o número é dado em radianos | SIN(number)| 
| SQRT | Retorna a raiz quadrada positiva de um número | SQRT(number)| 
| SUBSTITUTE | Substitui new_text por old_text em uma string de texto. Use SUBSTITUTE quando quiser substituir um texto específico em uma string de texto | SUBSTITUTE(text, old_text, new_text)| 
| TAN | Retorna a tangente do número, em que o número é dado em radianos | TAN(number)| 
| TEXT | Converte um valor em texto usando o formato de exibição padrão | TEXT(value)| 
| TODAY | Retorna a data atual | TODAY()| 
| TRIM | Remove todos os espaços de uma string de texto, com exceção dos espaços simples entre palavras | TRIM(text)| 
| TRUNC | Trunca um número para um número de dígitos especificado | TRUNC(number,num_digits)| 
| UNIXTIMESTAMP | Retorna o número de segundos desde 1º de janeiro de 1970 para a data fornecida ou o número de segundos no dia para uma hora. | UNIXTIMESTAMP(date/time)| 
| UPPER | Converte em maiúsculas todas as letras do valor | UPPER(text)| 
| URLENCODE | Codifica o texto e mescla os valores do campo para uso em URLs | URLENCODE(text)| 
| URLFOR | Retorna o URL do destino selecionado com entradas opcionais expressas como parâmetros de consulta | URLFOR(target, id, [inputs], [no override])| 
| VALUE | Converte em um número uma string de texto que representa um número | VALUE(text)| 
| WEEKDAY | Retorna o dia da semana correspondente à data fornecida, usando 1 para domingo, 2 para segunda-feira e assim por diante, até 7 para sábado. | DIA ÚTIL (data)| 
| YEAR | Retorna o ano de uma data, um número entre 1900 e 9999 | YEAR(date) |


## Fórmulas



Se você está procurando uma explicação sobre como usar a fórmula, confira [este artigo](https://help.salesforce.com/s/articleView?id=sf.customize_functions_parent.htm&type=5).
