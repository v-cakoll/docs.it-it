---
title: DataAdapter e DataReader
description: Informazioni sul DataReader ADO.NET, che recupera i dati da un database e DataAdapter, che recupera i dati da un'origine dati e popola un set di dati.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 17463d65266baa53521bed9603c8abd96923277b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286973"
---
# <a name="dataadapters-and-datareaders"></a>DataAdapter e DataReader
È possibile utilizzare il **DataReader** ADO.NET per recuperare un flusso di dati di sola lettura e di sola trasmissione da un database. I risultati vengono restituiti quando la query viene eseguita e vengono archiviati nel buffer di rete nel client fino a quando non vengono richiesti tramite il metodo **Read** di **DataReader**. L'utilizzo di **DataReader** può migliorare le prestazioni dell'applicazione recuperando i dati non appena sono disponibili e (per impostazione predefinita) archiviando solo una riga alla volta in memoria, riducendo l'overhead del sistema.  
  
 Un oggetto <xref:System.Data.Common.DataAdapter> viene usato per recuperare i dati da un'origine dati e compilare le tabelle all'interno di un oggetto <xref:System.Data.DataSet>. Il `DataAdapter` risolve inoltre le modifiche apportate al `DataSet` nell'origine dati. Il `DataAdapter` usa l'oggetto `Connection` del provider di dati .NET Framework per effettuare la connessione a un'origine dati e gli oggetti `Command` per recuperare i dati e risolvere le modifiche apportate all'origine dati.  
  
 Per ogni provider di dati .NET Framework incluso in .NET Framework sono disponibili un oggetto <xref:System.Data.Common.DbDataReader> e un oggetto <xref:System.Data.Common.DbDataAdapter>: nel provider di dati .NET Framework per OLE DB sono inclusi <xref:System.Data.OleDb.OleDbDataReader> e <xref:System.Data.OleDb.OleDbDataAdapter>, in quello per SQL Server sono inclusi <xref:System.Data.SqlClient.SqlDataReader> e <xref:System.Data.SqlClient.SqlDataAdapter>, in quello per ODBC sono inclusi <xref:System.Data.Odbc.OdbcDataReader> e <xref:System.Data.Odbc.OdbcDataAdapter> e in quello per Oracle sono inclusi <xref:System.Data.OracleClient.OracleDataReader> e <xref:System.Data.OracleClient.OracleDataAdapter>.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Recupero di dati tramite un oggetto DataReader](retrieving-data-using-a-datareader.md)  
 Descrive l'oggetto **DataReader** ADO.NET e come usarlo per restituire un flusso di risultati da un'origine dati.  
  
 [Popolamento di un set di dati da un oggetto DataAdapter](populating-a-dataset-from-a-dataadapter.md)  
 Viene descritto come compilare un `DataSet` con tabelle, colonne e righe usando un `DataAdapter`.  
  
 [Parametri DataAdapter](dataadapter-parameters.md)  
 Viene descritto come usare i parametri con le proprietà dei comandi di un `DataAdapter` e vengono fornite informazioni su come eseguire il mapping del contenuto di una colonna in un `DataSet` sul parametro di un comando.  
  
 [Aggiunta di vincoli esistenti a un dataset](adding-existing-constraints-to-a-dataset.md)  
 Viene descritto come aggiungere i vincoli esistenti a un `DataSet`.  
  
 [Mapping di DataAdapter, DataTable e DataColumn](dataadapter-datatable-and-datacolumn-mappings.md)  
 Viene descritto come impostare `DataTableMappings` e `ColumnMappings` per un `DataAdapter`.  
  
 [Spostarsi tra il risultato delle query](paging-through-a-query-result.md)  
 Viene fornito un esempio di visualizzazione dei risultati di una query sotto forma di pagine di dati.  
  
 [Aggiornamento di origini dati con DataAdapter](updating-data-sources-with-dataadapters.md)  
 Viene descritto come usare un `DataAdapter` per applicare le modifiche apportate a un `DataSet` fino a risalire al database.  
  
 [Gestione di eventi DataAdapter](handling-dataadapter-events.md)  
 Vengono descritti gli eventi del `DataAdapter` e il relativo uso.  
  
 [Esecuzione di operazioni batch tramite oggetti DataAdapter](performing-batch-operations-using-dataadapters.md)  
 Viene descritto il miglioramento delle prestazioni delle applicazioni mediante la riduzione del numero dei round trip a SQL Server quando si applicano gli aggiornamenti dal `DataSet`.  
  
## <a name="see-also"></a>Vedere anche

- [Connessione a un'origine dati](connecting-to-a-data-source.md)
- [Comandi e parametri](commands-and-parameters.md)
- [Transazioni e concorrenza](transactions-and-concurrency.md)
- [Oggetti DataSet, DataTable e DataView](./dataset-datatable-dataview/index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
