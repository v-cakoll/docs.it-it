---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758700"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Funzioni di aggregazione (SqlClient per Entity Framework)
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione che eseguono calcoli su un set di valori di input e restituiscono un valore. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.  
  
 Di seguito sono le funzioni di aggregazione di SqlClient.  

## <a name="avgexpression"></a>AVG(Expression)

Restituisce la media dei valori di una raccolta. I valori Null vengono ignorati.

**Argomenti**

Un' `Int32`, `Int64`, `Double`, e `Decimal`.

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a>CHECKSUM_AGG(Collection)
 
 Restituisce il checksum dei valori in una raccolta. I valori Null vengono ignorati.
 
 **Argomenti**
 
 A Collection(`Int32`).
 
 **Valore restituito**
 
 Oggetto `Int32`.
 
 **Esempio**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>Count(Expression)

Restituisce il numero di elementi in una raccolta come un valore `Int32`.

**Argomenti**

Una raccolta\<T >, dove T è uno dei tipi seguenti:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (non restituito in SQL Server 2000)|

**Valore restituito**

Oggetto `Int32`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="countbigexpression"></a>COUNT_BIG(expression)
 
 Restituisce il numero di elementi in una raccolta come un valore `bigint`.
 
 **Argomenti**
 
 Collection(T), dove T è uno dei tipi seguenti:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (non restituito in SQL Server 2000)|

**Valore restituito**

Oggetto `Int64`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX(Expression)

Restituisce il valore massimo nella raccolta.

**Argomenti**

Collection(T), dove T è uno dei tipi seguenti: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>Min(Expression)

Restituisce il valore minimo in una raccolta.

**Argomenti**

Collection(T), dove T è uno dei tipi seguenti: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV(Expression)

Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.

**Argomenti**

A Collection(`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>StDevP(Expression)

Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.

**Argomenti**

A Collection(`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM(Expression)

Restituisce la somma di tutti i valori della raccolta.

**Argomenti**

Un Collection(T) dove T è uno dei tipi seguenti: `Int32`, `Int64`, `Double`, `Decimal`.

**Valore restituito**

Tipo di `expression`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR(expression)

Restituisce la varianza statistica di tutti i valori nell'espressione specificata.

**Argomenti**

A Collection(`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VarP(Expression)

Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.

**Argomenti**

A Collection(`Double`).

**Valore restituito**

Oggetto `Double`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>Vedere anche

Per altre informazioni sulle funzioni di aggregazione supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:

- **SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))
- **SQL Server 2008 e versioni successive:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)

- [Linguaggio Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Funzioni di aggregazione canoniche](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
