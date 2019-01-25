---
title: Connessione a un'origine dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 20cf22e1c9b9bf18dd3109cb9589c05a6c27d4d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701742"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Connessione a un'origine dati in ADO.NET
In ADO.NET si utilizza un **connessione** oggetto per la connessione a un'origine dati specifica, fornendo informazioni di autenticazione necessarie in una stringa di connessione. Il **connessione** oggetto da usare dipende dal tipo di origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Stabilire una connessione](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Viene descritto come utilizzare un **connessione** oggetto per stabilire una connessione a un'origine dati.  
  
 [Eventi di connessione](../../../../docs/framework/data/adonet/connection-events.md)  
 Viene descritto come utilizzare un **InfoMessage** recuperare messaggi informativi da un'origine dati dell'evento.  
  
## <a name="see-also"></a>Vedere anche
- [Stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings.md)
- [Pool di connessioni](../../../../docs/framework/data/adonet/connection-pooling.md)
- [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
