---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700050"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funzioni di aggregazione (SqlClient per Entity Framework)
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione che eseguono calcoli su un set di valori di input e restituiscono un valore. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.  
  
 Di seguito sono riportate le funzioni di aggregazione SqlClient.  

## <a name="avgexpression"></a>AVG (espressione)

Restituisce la media dei valori di una raccolta. I valori Null vengono ignorati.

**Argomenti**

Un `Int32`, `Int64`, `Double` e `Decimal`.

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (raccolta)
 
 Restituisce il checksum dei valori in una raccolta. I valori Null vengono ignorati.
 
 **Argomenti**
 
 Raccolta (`Int32`).
 
 **Valore restituito**
 
 Oggetto `Int32`.
 
 **Esempio**
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>CONTEGGIO (espressione)

Restituisce il numero di elementi in una raccolta come un valore `Int32`.

**Argomenti**

Una raccolta @ no__t-0T >, dove T è uno dei tipi seguenti:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (non restituito in SQL Server 2000)|

**Valore restituito**

Oggetto `Int32`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a>COUNT_BIG (espressione)
 
Restituisce il numero di elementi in una raccolta come un valore `bigint`.
 
 **Argomenti**
 
 Raccolta (T), dove T è uno dei tipi seguenti:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (non restituito in SQL Server 2000)|

**Valore restituito**

Oggetto `Int64`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX (espressione)

Restituisce il valore massimo nella raccolta.

**Argomenti**

Raccolta (T), dove T è uno dei tipi seguenti: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN (espressione)

Restituisce il valore minimo in una raccolta.

**Argomenti**

Raccolta (T), dove T è uno dei tipi seguenti: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV (espressione)

Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP (espressione)

Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM (espressione)

Restituisce la somma di tutti i valori della raccolta.

**Argomenti**

Raccolta (T), dove T è uno dei tipi seguenti: `Int32`, `Int64`, `Double`, `Decimal`.

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR (espressione)

Restituisce la varianza statistica di tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP (espressione)

Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di aggregazione (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [Linguaggio Entity SQL](./language-reference/entity-sql-language.md)
- [Funzioni di aggregazione canoniche](./language-reference/aggregate-canonical-functions.md)
