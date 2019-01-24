---
title: DataAdapter e DataReader
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: f4588187aad910d0b50b0c804e6de20a477b567b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583509"
---
# <a name="dataadapters-and-datareaders"></a>DataAdapter e DataReader
È possibile usare ADO.NET **DataReader** per recuperare un flusso forward-only in sola lettura di dati da un database. I risultati vengono restituiti quando viene eseguita la query e vengono archiviati nel buffer di rete nel client fino a quando non vengono richiesti utilizzando il **lettura** metodo per il **DataReader**. Usando il **DataReader** può aumentare le prestazioni dell'applicazione recuperando i dati non appena è disponibile sia (per impostazione predefinita) archiviando solo una riga alla volta in memoria, riducendo l'overhead di sistema.  
  
 Un oggetto <xref:System.Data.Common.DataAdapter> viene usato per recuperare i dati da un'origine dati e compilare le tabelle all'interno di un oggetto <xref:System.Data.DataSet>. Il `DataAdapter` risolve inoltre le modifiche apportate al `DataSet` nell'origine dati. Il `DataAdapter` usa l'oggetto `Connection` del provider di dati .NET Framework per effettuare la connessione a un'origine dati e gli oggetti `Command` per recuperare i dati e risolvere le modifiche apportate all'origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework sono disponibili un oggetto <xref:System.Data.Common.DbDataReader> e un oggetto <xref:System.Data.Common.DbDataAdapter>: nel provider di dati .NET Framework per OLE DB sono inclusi <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.OleDb.OleDbDataAdapter>, in quello per SQL Server sono inclusi <xref:System.Data.SqlClient.SqlDataReader> e <xref:System.Data.SqlClient.SqlDataAdapter>, in quello per ODBC sono inclusi <xref:System.Data.Odbc.OdbcDataReader> e <xref:System.Data.Odbc.OdbcDataAdapter> e in quello per Oracle sono inclusi <xref:System.Data.OracleClient.OracleDataReader> e <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Recupero di dati tramite DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Viene descritto il ADO.NET **DataReader** oggetto e come usarlo per restituire un flusso di risultati da un'origine dati.  
  
 [Popolamento di un set di dati da un oggetto DataAdapter](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Viene descritto come compilare un `DataSet` con tabelle, colonne e righe usando un `DataAdapter`.  
  
 [Parametri DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Viene descritto come usare i parametri con le proprietà dei comandi di un `DataAdapter` e vengono fornite informazioni su come eseguire il mapping del contenuto di una colonna in un `DataSet` sul parametro di un comando.  
  
 [Aggiunta di vincoli esistenti a un set di dati](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Viene descritto come aggiungere i vincoli esistenti a un `DataSet`.  
  
 [Mapping di DataAdapter, DataTable e DataColumn](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Viene descritto come impostare `DataTableMappings` e `ColumnMappings` per un `DataAdapter`.  
  
 [Paging del risultato di query](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Viene fornito un esempio di visualizzazione dei risultati di una query sotto forma di pagine di dati.  
  
 [Aggiornamento di origini dati con DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Viene descritto come usare un `DataAdapter` per applicare le modifiche apportate a un `DataSet` fino a risalire al database.  
  
 [Gestione di eventi DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Vengono descritti gli eventi del `DataAdapter` e il relativo uso.  
  
 [Esecuzione di operazioni batch tramite DataAdapter](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Viene descritto il miglioramento delle prestazioni delle applicazioni mediante la riduzione del numero dei round trip a SQL Server quando si applicano gli aggiornamenti dal `DataSet`.  
  
## <a name="see-also"></a>Vedere anche
- [Connessione a un'origine dati](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
