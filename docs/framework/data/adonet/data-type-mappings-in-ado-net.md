---
title: Mapping dei tipi di dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: ddb3c1c5551336ace66bab53af3beb83b6cd2d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950404"
---
# <a name="data-type-mappings-in-adonet"></a>Mapping dei tipi di dati in ADO.NET
.NET Framework è basato su Common Type System, che definisce come vengono dichiarati, usati e gestiti i tipi nel runtime. È costituito sia da tipi di valore che da tipi di riferimento, che derivano tutti dal tipo di base <xref:System.Object>. Quando si usa un'origine dati, il tipo di dati viene dedotto dal provider di dati, se non è specificato in modo esplicito. Un oggetto <xref:System.Data.DataSet> è ad esempio indipendente da qualsiasi origine dati specifica. I dati in un oggetto `DataSet` vengono recuperati da un'origine dati e le modifiche vengono applicate nell'origine dati usando un oggetto `DataAdapter`. Ciò significa che quando un `DataAdapter` oggetto compila un <xref:System.Data.DataTable> `DataSet` oggetto con i valori di un'origine dati, i tipi di dati `DataTable` risultanti delle colonne in sono .NET Framework tipi, anziché tipi specifici del provider di dati .NET Framework che viene utilizzato per la connessione all'origine dati.  
  
 Analogamente, quando `DataReader` un restituisce un valore da un'origine dati, il valore risultante viene archiviato in una variabile locale con un tipo di .NET Framework. Per entrambe le `Fill` operazioni `DataAdapter` `Get` di`DataReader`e i metodi di, il tipo di .NET Framework viene dedotto dal valore restituito dal provider di dati .NET Framework.  
  
 Anziché basarsi sul tipo di dati dedotto, quando si conosce il tipo specifico del valore che viene restituito è consigliabile usare i metodi delle funzioni di accesso tipizzate di `DataReader` . I metodi delle funzioni di accesso tipizzate offrono prestazioni migliori restituendo un valore come tipo di .NET Framework specifico, eliminando la necessità di una conversione di tipi aggiuntiva.  
  
> [!NOTE]
> I valori null per .NET Framework tipi di dati del provider di `DBNull.Value`dati sono rappresentati da.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping dei tipi di dati SQL Server](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.SqlClient>.  
  
 [Mapping dei tipi di dati OLE DB](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.OleDb>.  
  
 [Mapping dei tipi di dati ODBC](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.Odbc>.  
  
 [Mapping dei tipi di dati Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.OracleClient>.  
  
 [Numeri a virgola mobile](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Vengono descritti i problemi rilevati di frequente dagli sviluppatori con l'uso di numeri a virgola mobile.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati SQL Server e ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Configurazione di parametri e tipi di dati dei parametri](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Common Type System](../../../standard/base-types/common-type-system.md)
- [Conversione di tipi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
