---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365644"
---
# <a name="mathematical-functions"></a>Funzioni matematiche

Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Nella tabella che segue sono illustrate le funzioni matematiche SqlClient.  
  
## <a name="absexpression"></a>Abs(Expression)

Esegue la funzione relativa al valore assoluto.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Valore assoluto dell'espressione specificata.

**Esempio**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(Expression)

Restituisce il valore dell'arcocoseno dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

Oggetto `Double`.

**Esempio**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(Expression)

Restituisce il valore dell'arcoseno dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

Oggetto `Double`.

**Esempio**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(Expression)

Restituisce il valore dell'arcotangente dell'espressione numerica specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

Oggetto `Double`.

**Esempio**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(Expression, Expression)

Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

Oggetto `Double`.

**Esempio**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>Ceiling(Expression)

Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Un' `Int32`, `Int64`, `Double`, o `Decimal`.

**Esempio** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(Expression)

Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(Expression)

Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES(RADIANS)

Restituisce l'angolo corrispondente in gradi. 

**Argomenti** 

`expression`: `Int32`,`Int64`, `Double` o `Decimal`. 

**Valore restituito** 

Un' `Int32`, `Int64`, `Double`, o `Decimal`. 

**Esempio** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(Expression)

Calcola il valore esponenziale dell'espressione numerica specificata. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** `SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR(Expression)

Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(Expression)

Calcola il logaritmo naturale dell'espressione `float` specificata. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(Expression)

Restituisce il logaritmo in base 10 dell'espressione `Double` specificata. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI

Restituisce il valore costante di pi greco sotto forma di oggetto `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a>POWER (numeric_expression, power_expression)

Calcola il valore dell'espressione specificata elevato alla potenza indicata.

**Argomenti** 

|  |  |
|--|--|
|`numeric_expression`| Un' `Int32`, `Int64`, `Double`, o `Decimal`.|
|`power_expression`| Oggetto `Double` che rappresenta la potenza a cui elevare il `numeric_expression`.| 

**Valore restituito** 

Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata. 

**Esempio** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(Expression)

Converte i gradi in radianti. 

**Argomenti** 

`expression`: `Int32`,`Int64`, `Double` o `Decimal`. 

**Valore restituito** 

Un' `Int32`, `Int64`, `Double`, o `Decimal`. 

**Esempio** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([SEED])

Restituisce un valore casuale compreso tra 0 e 1. 

**Argomenti** 

Il valore di inizializzazione come un `Int32`. Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale. Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.

**Valore restituito** 

Valore `Double` casuale compreso tra 0 e 1. 

**Esempio** 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a>Round(numeric_expression, Length[,Function])

Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata. 

**Argomenti** 

|  |  |
|--|--|
|`numeric_expression`| Un' `Int32`, `Int64`, `Double`, o `Decimal`. 
|`length`| Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`. Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`. Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.|
|`function` | Facoltativo. Un `Int32` che rappresenta il tipo di operazione da eseguire. Quando viene omesso oppure ha un valore pari a 0 (impostazione predefinita), `numeric_expression` viene arrotondato. Quando un valore diverso da è specificato 0, `numeric_expression` viene troncato. |

**Valore restituito** 

Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.

**Esempio** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>Sign(Expression) 

Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata. 

**Argomenti** 

`expression`: `Int32`, `Int64`, `Double` o `Decimal` 

**Valore restituito** 

Un' `Int32`, `Int64`, `Double`, o `Decimal`. 

**Esempio** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>Sin(Expression)

Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** `SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT(Expression)

Restituisce la radice quadrata dell'espressione specificata. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** `SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>Square(Expression)

Restituisce la radice dell'espressione specificata. 

**Argomenti** 

`expression`: valore `Double`. 

**Valore restituito** 

Oggetto `Double`. 

**Esempio** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(Expression)

Calcola la tangente di un'espressione specificata.

**Argomenti** 

`expression`: `Double` 

**Valore restituito** 

`Double` 

**Esempio** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Vedere anche

Per altre informazioni sulle funzioni matematiche supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:  
  
**SQL Server 2005:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))  
**SQL Server 2008:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))  
**SQL Server 2012 e versioni successive:** [funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)   

 [SqlClient per funzioni Entity Framework](sqlclient-for-ef-functions.md)
