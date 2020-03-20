---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149765"
---
# <a name="mathematical-functions"></a>Funzioni matematiche

Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Nella tabella seguente vengono descritte le funzioni matematiche SqlClient.  
  
## <a name="absexpression"></a>ABS(espressione)

Esegue la funzione relativa al valore assoluto.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Valore assoluto dell'espressione specificata.

**Esempio**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ARCCOS(espressione)

Restituisce il valore dell'arcocoseno dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(espressione)

Restituisce il valore dell'arcoseno dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(espressione)

Restituisce il valore dell'arcotangente dell'espressione numerica specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(espressione; espressione)

Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a>ARROTONDA.

Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(espressione)

Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(espressione)

Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>GRADI(radianti)

Restituisce l'angolo corrispondente in gradi.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .

**Esempio**

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(espressione)

Calcola il valore esponenziale dell'espressione numerica specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**`SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR(espressione)

Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(espressione)

Calcola il logaritmo naturale dell'espressione `float` specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(espressione)

Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI()

Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a>POWER(numeric_expression, power_expression)

Calcola il valore dell'espressione specificata elevato alla potenza indicata.

**Argomenti**

|  |  |
|--|--|
|`numeric_expression`| Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .|
|`power_expression`| Oggetto `Double` che rappresenta la potenza `numeric_expression`a cui elevare il file .|

**Valore restituito**

Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.

**Esempio**

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANTI(espressione)

Converte i gradi in radianti.

**Argomenti**

`expression`: `Int32`,`Int64`, `Double` o `Decimal`.

**Valore restituito**

Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .

**Esempio**

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([seme])

Restituisce un valore casuale compreso tra 0 e 1.

**Argomenti**

Valore del valore `Int32`di seme come oggetto . Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale. Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.

**Valore restituito**

Valore `Double` casuale compreso tra 0 e 1.

**Esempio**

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>ARROTONDA(numeric_expression, lunghezza[,funzione])

Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.

**Argomenti**

|  |  |
|--|--|
|`numeric_expression`| Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .
|`length`| Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`. Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`. Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.|
|`function` | Facoltativa. Oggetto `Int32` che rappresenta il tipo di operazione da eseguire. Quando la funzione viene omessa o ha `numeric_expression` un valore pari a 0 (impostazione predefinita), viene arrotondata. Quando viene specificato un valore `numeric_expression` diverso da 0, viene troncato. |

**Valore restituito**

Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.

**Esempio**

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>SEGNO(espressione)

Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.

**Argomenti**

`expression`: `Int32`, `Int64`, `Double` o `Decimal`

**Valore restituito**

Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .

**Esempio**

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(espressione)

Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>RADQ(espressione)

Restituisce la radice quadrata dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>SQUARE(espressione)

Restituisce la radice dell'espressione specificata.

**Argomenti**

`expression`: valore `Double`.

**Valore restituito**

`Double`.

**Esempio**

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(espressione)

Calcola la tangente di un'espressione specificata.

**Argomenti**

`expression`: `Double`

**Valore restituito**

`Double`

**Esempio**

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Vedere anche

- [Funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [SqlClient per funzioni Entity Framework](sqlclient-for-ef-functions.md)
