---
title: Connessione a un'origine dei dati
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 206a4f741b6bf711b51da794e23f779c2bea6fa0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094449"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Connessione a un'origine dati in ADO.NET

In ADO.NET si usa un oggetto **Connection** per connettersi a un'origine dati specifica fornendo le informazioni di autenticazione necessarie in una stringa di connessione. L'oggetto **connessione** utilizzato dipende dal tipo di origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Stabilire la connessione](establishing-the-connection.md)\
 Viene descritto come utilizzare un oggetto **Connection** per stabilire una connessione a un'origine dati.  
  
 [Eventi di connessione](connection-events.md)\
 Viene descritto come utilizzare un evento **InfoMessage** per recuperare messaggi informativi da un'origine dati.  
  
## <a name="see-also"></a>Vedere anche

- [Stringhe di connessione](connection-strings.md)
- [Pool di connessioni](connection-pooling.md)
- [Comandi e parametri](commands-and-parameters.md)
- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Transazioni e concorrenza](transactions-and-concurrency.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
