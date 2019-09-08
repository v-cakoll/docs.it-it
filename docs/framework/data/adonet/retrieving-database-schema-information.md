---
title: Recupero di informazioni dello schema del database
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782733"
---
# <a name="retrieving-database-schema-information"></a>Recupero di informazioni dello schema del database
Il recupero di informazioni sullo schema da un database viene eseguito tramite il processo di individuazione dello schema. L'individuazione dello schema consente alle applicazioni di richiedere che i provider gestiti trovino e restituiscano informazioni sullo schema del database, noto anche come *metadati*, di un determinato database. Nella raccolta di schemi vengono esposti vari elementi dello schema del database, quali tabelle, colonne e stored procedure. Ogni raccolta di schemi contiene una varietà di informazioni sullo schema specifiche del provider usato.  
  
 Ognuno dei provider .NET Framework gestiti implementa il metodo **GetSchema** nella classe **Connection** e le informazioni sullo schema restituite dal metodo **GetSchema** sono nel formato di un oggetto <xref:System.Data.DataTable>. Il metodo **GetSchema** è un metodo di overload che fornisce parametri facoltativi per specificare la raccolta di schemi da restituire e per limitare la quantità di informazioni restituite.  
  
 I provider di dati .NET Framework per OLE DB, ODBC, Oracle e SqlClient forniscono un metodo **GetSchemaTable** che restituisce un oggetto DataTable che descrive i metadati della colonna del **DataReader**.  
  
 Il provider di dati .NET Framework per OLE DB presenta le informazioni sullo schema usando anche il metodo <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> dell'oggetto <xref:System.Data.OleDb.OleDbConnection>. Come argomenti, **il metodo GetOleDbSchemaTable** accetta un <xref:System.Data.OleDb.OleDbSchemaGuid> oggetto che identifica le informazioni sullo schema da restituire e una matrice di restrizioni sulle colonne restituite. **Il metodo GetOleDbSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con le informazioni sullo schema richieste.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Raccolte di schemi e GetSchema](getschema-and-schema-collections.md)  
 Descrive il metodo **GetSchema** e il modo in cui può essere utilizzato per recuperare e limitare le informazioni dello schema da un database.  
  
 Restrizione dello schema  
 Descrive le restrizioni dello schema che possono essere usate con **GetSchema**.  
  
 [Raccolte di schemi comuni](common-schema-collections.md)  
 Vengono descritte tutte le raccolte di schemi comuni supportate dai provider .NET Framework gestiti.  
  
 [Raccolte di schemi SQL Server](sql-server-schema-collections.md)  
 Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per SQL Server.  
  
 [Raccolte di schemi Oracle](oracle-schema-collections.md)  
 Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per Oracle.  
  
 [Raccolte di schemi ODBC](odbc-schema-collections.md)  
 Vengono illustrate le raccolte di schemi per i driver ODBC.  
  
 [Raccolte di schemi OLE DB](ole-db-schema-collections.md)  
 Vengono illustrate le raccolte di schemi per i provider OLE DB.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Viene descritto il metodo **GetSchema** della <xref:System.Data.Common.DbConnection> classe.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Viene descritto il metodo **GetSchema** della <xref:System.Data.Odbc.OdbcConnection> classe.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Viene descritto il metodo **GetSchema** della <xref:System.Data.OleDb.OleDbConnection> classe.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Viene descritto il metodo **GetSchema** della <xref:System.Data.OracleClient.OracleConnection> classe.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Viene descritto il metodo **GetSchema** della <xref:System.Data.SqlClient.SqlConnection> classe.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Descrive il metodo **GetSchemaTable** della <xref:System.Data.Common.DbDataReader> classe.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Descrive il metodo **GetSchemaTable** della <xref:System.Data.Odbc.OdbcDataReader> classe.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Descrive il metodo **GetSchemaTable** della <xref:System.Data.OleDb.OleDbDataReader> classe.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Descrive il metodo **GetSchemaTable** della <xref:System.Data.OracleClient.OracleDataReader> classe.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Descrive il metodo **GetSchemaTable** della <xref:System.Data.SqlClient.SqlDataReader> classe.  
  
## <a name="see-also"></a>Vedere anche

- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
