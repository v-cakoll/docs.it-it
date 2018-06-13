---
title: Connessione a un'origine dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757112"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Connessione a un'origine dati in ADO.NET
In ADO.NET viene utilizzato un **connessione** oggetto per la connessione a un'origine dati specifica fornendo informazioni di autenticazione necessarie in una stringa di connessione. Il **connessione** utilizzato dipende dal tipo di origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Stabilire una connessione](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Viene descritto come utilizzare un **connessione** oggetto per stabilire una connessione a un'origine dati.  
  
 [Eventi di connessione](../../../../docs/framework/data/adonet/connection-events.md)  
 Viene descritto come utilizzare un **InfoMessage** recuperare messaggi informativi da un'origine dati dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Pool di connessioni](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
