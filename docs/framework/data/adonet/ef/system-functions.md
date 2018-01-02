---
title: Funzioni di sistema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dda704e70fc7927f382e851189073ffa5dececb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="system-functions"></a>Funzioni di sistema
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce le funzioni di sistema seguenti:  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Restituisce il valore checksum. `CHECKSUM` viene usata per la compilazione di indici hash.<br /><br /> **Argomenti**<br /><br /> `value`: Valore `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`, o `Guid`. È possibile specificare uno, due o tre valori.<br /><br /> **Valore restituito**<br /><br /> Valore assoluto dell'espressione specificata.<br /><br /> **Esempio**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Produce la data e l'ora correnti nel formato interno di SQL Server per i valori `DateTime` con precisione pari a 7 e a 3 rispettivamente in SQL Server 2008 e SQL Server 2005.<br /><br /> **Valore restituito**<br /><br /> Data e ora di sistema correnti come valore `DateTime`.<br /><br /> **Esempio**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Restituisce il nome dell'utente corrente.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` ASCII.<br /><br /> **Esempio**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Restituisce il numero di byte usato per rappresentare qualsiasi espressione.<br /><br /> **Argomenti**<br /><br /> `expression`: Valore `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Dimensione delle proprietà, come valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Restituisce il nome della workstation.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` Unicode.<br /><br /> **Esempio**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Determina se un'espressione di input è una data valida.<br /><br /> **Argomenti**<br /><br /> `expression`: Valore `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Int32`. Uno (1) se l'espressione di input è una data valida; in caso contrario, zero (0).<br /><br /> **Esempio**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Determina se un'espressione restituisce un tipo numerico valido.<br /><br /> **Argomenti**<br /><br /> `expression`: Valore `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, o `Guid`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Int32`. Uno (1) se l'espressione di input è una data valida; in caso contrario, zero (0).<br /><br /> **Esempio**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Crea un valore univoco di tipo Guid.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Guid`.<br /><br /> **Esempio**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Restituisce un nome utente del database corrispondente al numero di identificazione specificato.<br /><br /> **Argomenti**<br /><br /> `expression`: numero di identificazione `Int32` associato a un utente del database.<br /><br /> **Valore restituito**<br /><br /> Tipo `String` Unicode.<br /><br /> **Esempio**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Per altre informazioni sulle funzioni String supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Sistema funzioni Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115918)|[Sistema funzioni Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115917)|[Funzioni di sistema (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115919)|  
  
## <a name="see-also"></a>Vedere anche  
 [Linguaggio Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [SqlClient per funzioni Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
