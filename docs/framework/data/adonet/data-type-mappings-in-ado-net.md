---
title: Mapping dei tipi di dati
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 610cdc1a679b0c51125075076120e12db97da421
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980197"
---
# <a name="data-type-mappings-in-adonet"></a>Mapping dei tipi di dati in ADO.NET
.NET Framework è basato su Common Type System, che definisce come vengono dichiarati, usati e gestiti i tipi nel runtime. È costituito sia da tipi di valore che da tipi di riferimento, che derivano tutti dal tipo di base <xref:System.Object>. Quando si usa un'origine dati, il tipo di dati viene dedotto dal provider di dati, se non è specificato in modo esplicito. Un oggetto <xref:System.Data.DataSet> è ad esempio indipendente da qualsiasi origine dati specifica. I dati in un oggetto `DataSet` vengono recuperati da un'origine dati e le modifiche vengono applicate nell'origine dati usando un oggetto `DataAdapter`. Ciò significa che quando un `DataAdapter` compila un <xref:System.Data.DataTable> in un `DataSet` con i valori di un'origine dati, i tipi di dati risultanti delle colonne nel `DataTable` sono tipi di .NET Framework, anziché tipi specifici del provider di dati .NET Framework usato per la connessione all'origine dati.  
  
 Analogamente, quando un `DataReader` restituisce un valore da un'origine dati, il valore risultante viene archiviato in una variabile locale con un tipo di .NET Framework. Per entrambe le operazioni di `Fill` del `DataAdapter` e dei metodi di `Get` del `DataReader`, il tipo di .NET Framework viene dedotto dal valore restituito dal provider di dati .NET Framework.  
  
 Anziché basarsi sul tipo di dati dedotto, quando si conosce il tipo specifico del valore che viene restituito è consigliabile usare i metodi delle funzioni di accesso tipizzate di `DataReader` . I metodi delle funzioni di accesso tipizzate offrono prestazioni migliori restituendo un valore come tipo di .NET Framework specifico, eliminando la necessità di una conversione di tipi aggiuntiva.  
  
> [!NOTE]
> I valori null per .NET Framework tipi di dati del provider di dati sono rappresentati da `DBNull.Value`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping dei tipi di dati SQL Server](sql-server-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.SqlClient>.  
  
 [Mapping dei tipi di dati OLE DB](ole-db-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.OleDb>.  
  
 [Mapping dei tipi di dati ODBC](odbc-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.Odbc>.  
  
 [Mapping dei tipi di dati Oracle](oracle-data-type-mappings.md)  
 Vengono elencati i mapping dei tipi di dati dedotti e i metodi delle funzioni di accesso ai dati per <xref:System.Data.OracleClient>.  
  
 [Numeri a virgola mobile](floating-point-numbers.md)  
 Vengono descritti i problemi rilevati di frequente dagli sviluppatori con l'uso di numeri a virgola mobile.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati SQL Server e ADO.NET](./sql/sql-server-data-types.md)
- [Configurazione di parametri e tipi di dati dei parametri](configuring-parameters-and-parameter-data-types.md)
- [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)
- [Common Type System](../../../standard/base-types/common-type-system.md)
- [Conversione di tipi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Panoramica di ADO.NET](ado-net-overview.md)
