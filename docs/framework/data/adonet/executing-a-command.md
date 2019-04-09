---
title: Esecuzione di un comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: c3ed424aff3cd485a78d26a7f27bc5b1eac66448
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119743"
---
# <a name="executing-a-command"></a>Esecuzione di un comando
In ogni provider di dati .NET Framework fornito con .NET Framework è incluso un oggetto comando che eredita da <xref:System.Data.Common.DbCommand>. Nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbCommand>, in quello per SQL Server un oggetto <xref:System.Data.SqlClient.SqlCommand>, in quello per ODBC un oggetto <xref:System.Data.Odbc.OdbcCommand> e in quello per Oracle un oggetto <xref:System.Data.OracleClient.OracleCommand>. Ognuno di questi oggetti espone metodi per l'esecuzione di comandi in base al tipo di comando e al valore restituito desiderato, come descritto nella tabella seguente.  
  
|Comando|Valore restituito|  
|-------------|------------------|  
|`ExecuteReader`|Restituisce un oggetto `DataReader`.|  
|`ExecuteScalar`|Restituisce un singolo valore scalare.|  
|`ExecuteNonQuery`|Esegue un comando che non restituisce righe.|  
|`ExecuteXMLReader`|Restituisce un oggetto <xref:System.Xml.XmlReader>. Disponibile solo per un oggetto `SqlCommand`.|  
  
 Ogni oggetto comando fortemente tipizzato supporta anche un'enumerazione <xref:System.Data.CommandType> che specifica la modalità di interpretazione di una stringa di comando, come descritto nella tabella seguente.  
  
|CommandType|Descrizione|  
|-----------------|-----------------|  
|`Text`|Comando SQL che definisce le istruzioni da eseguire nell'origine dati.|  
|`StoredProcedure`|Nome della stored procedure. È possibile usare la proprietà `Parameters` di un comando per accedere a parametri di input e output e a valori restituiti indipendentemente dal metodo `Execute` chiamato. Quando si usa `ExecuteReader`, non è possibile accedere ai valori restituiti e ai parametri di output fino a quando `DataReader` non viene chiuso.|  
|`TableDirect`|Nome di una tabella.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come creare un oggetto <xref:System.Data.SqlClient.SqlCommand> per eseguire una stored procedure impostando le relative proprietà. Per specificare il parametro di input per la stored procedure, viene usato un oggetto <xref:System.Data.SqlClient.SqlParameter>. Il comando viene eseguito usando il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> e l'output di <xref:System.Data.SqlClient.SqlDataReader> viene visualizzato nella finestra della console.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a>Risoluzione dei problemi dei comandi  
 Con il provider di dati .NET Framework per SQL Server vengono aggiunti contatori delle prestazioni che consentono l'individuazione dei problemi intermittenti relativi a comandi non eseguiti correttamente. Per altre informazioni, vedere [contatori delle prestazioni](../../../../docs/framework/data/adonet/performance-counters.md).  
  
## <a name="see-also"></a>Vedere anche

- [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Cenni preliminari su ADO.NET](ado-net-overview.md)
