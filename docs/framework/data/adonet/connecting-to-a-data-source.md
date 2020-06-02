---
title: Connessione a un'origine dei dati
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: a14fe179cf2fc8714a54e52252c53bd71346cad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287077"
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
