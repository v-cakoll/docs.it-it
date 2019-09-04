---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251699"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funzioni di aggregazione (SqlClient per Entity Framework)
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione che eseguono calcoli su un set di valori di input e restituiscono un valore. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.  
  
 Di seguito sono riportate le funzioni di aggregazione SqlClient.  

## <a name="avgexpression"></a>AVG (espressione)

Restituisce la media dei valori di una raccolta. I valori Null vengono ignorati.

**Argomenti**

`Int32` ,`Int64`, E .`Decimal` `Double`

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (raccolta)
 
 Restituisce il checksum dei valori in una raccolta. I valori Null vengono ignorati.
 
 **Argomenti**
 
 Raccolta (`Int32`).
 
 **Valore restituito**
 
 Oggetto `Int32`.
 
 **Esempio**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>CONTEGGIO (espressione)

Restituisce il numero di elementi in una raccolta come un valore `Int32`.

**Argomenti**

Una raccolta\<t >, dove t è uno dei tipi seguenti:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(non restituito nel SQL Server 2000)|

**Valore restituito**

Oggetto `Int32`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="count_bigexpression"></a>COUNT_BIG (espressione)
 
 Restituisce il numero di elementi in una raccolta come un valore `bigint`.
 
 **Argomenti**
 
 Raccolta (T), dove T è uno dei tipi seguenti:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(non restituito nel SQL Server 2000)|

**Valore restituito**

Oggetto `Int64`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
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

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
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

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV (espressione)

Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP (espressione)

Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM (espressione)

Restituisce la somma di tutti i valori della raccolta.

**Argomenti**

`Int32`Raccolta (t) `Int64` `Decimal`, dove t è uno dei tipi seguenti:,, ,.`Double`

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR (espressione)

Restituisce la varianza statistica di tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP (espressione)

Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.

**Argomenti**

Raccolta (`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>Vedere anche

Per altre informazioni sulle funzioni di aggregazione supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:

- **SQL Server 2005:** [Funzioni di aggregazione (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))
- **SQL Server 2008 e versioni successive:** [Funzioni di aggregazione (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)

- [Linguaggio Entity SQL](./language-reference/entity-sql-language.md)
- [Funzioni di aggregazione canoniche](./language-reference/aggregate-canonical-functions.md)
