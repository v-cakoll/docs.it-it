---
title: Funzioni di sistema
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 9b5455d63dca40834515b14bae2f35d3b54d2aee
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452435"
---
# <a name="system-functions"></a>Funzioni di sistema
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce le funzioni di sistema seguenti:  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Restituisce il valore checksum. `CHECKSUM` viene usata per la compilazione di indici hash.<br /><br /> **Argomenti**<br /><br /> `value`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`o `Guid`. È possibile specificare uno, due o tre valori.<br /><br /> **Valore restituito**<br /><br /> Valore assoluto dell'espressione specificata.<br /><br /> **Esempio**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Produce la data e l'ora correnti nel formato interno di SQL Server per i valori `DateTime` con precisione pari a 7 e a 3 rispettivamente in SQL Server 2008 e SQL Server 2005.<br /><br /> **Valore restituito**<br /><br /> Data e ora di sistema correnti come valore `DateTime`.<br /><br /> **Esempio**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Restituisce il nome dell'utente corrente.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` ASCII.<br /><br /> **Esempio**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Restituisce il numero di byte utilizzati per rappresentare un'espressione.<br /><br /> **Argomenti**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Dimensione delle proprietà, come valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Restituisce il nome della workstation.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` Unicode.<br /><br /> **Esempio**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Determina se un'espressione di input è una data valida.<br /><br /> **Argomenti**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Uno `Int32`. Uno (1) se l'espressione di input è una data valida; in caso contrario, zero (0).<br /><br /> **Esempio**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Determina se un'espressione restituisce un tipo numerico valido.<br /><br /> **Argomenti**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Uno `Int32`. Uno (1) se l'espressione di input è una data valida; in caso contrario, zero (0).<br /><br /> **Esempio**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Crea un valore univoco di tipo Guid.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Guid`.<br /><br /> **Esempio**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Restituisce un nome utente del database corrispondente al numero di identificazione specificato.<br /><br /> **Argomenti**<br /><br /> `expression`: numero di identificazione `Int32` associato a un utente del database.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` Unicode.<br /><br /> **Esempio**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Per ulteriori informazioni sulle funzioni di `String` supportate da SqlClient, vedere [funzioni di stringa (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).
  
## <a name="see-also"></a>Vedere anche

- [Linguaggio Entity SQL](./language-reference/entity-sql-language.md)
- [SqlClient per funzioni Entity Framework](sqlclient-for-ef-functions.md)
