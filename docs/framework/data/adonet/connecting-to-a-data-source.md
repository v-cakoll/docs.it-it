---
title: Connessione a un'origine dati in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0d21c571b659e9d7aef65893db18b034d614e2af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Connessione a un'origine dati in ADO.NET
In ADO.NET viene utilizzato un **connessione** oggetto per la connessione a un'origine dati specifica fornendo informazioni di autenticazione necessarie in una stringa di connessione. Il **connessione** utilizzato dipende dal tipo di origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Per stabilire la connessione](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Viene descritto come utilizzare un **connessione** oggetto per stabilire una connessione a un'origine dati.  
  
 [Eventi di connessione](../../../../docs/framework/data/adonet/connection-events.md)  
 Viene descritto come utilizzare un **InfoMessage** recuperare messaggi informativi da un'origine dati dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Il pool di connessioni](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
