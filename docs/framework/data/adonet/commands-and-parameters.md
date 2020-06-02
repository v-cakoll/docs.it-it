---
title: Comandi e parametri
description: Informazioni su come usare gli oggetti Command per ogni provider di dati .NET Framework per eseguire comandi e restituire risultati da un'origine dati.
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: c0baec4d6c3984cb50178c3aa7f9ed3878055bb6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287142"
---
# <a name="commands-and-parameters"></a>Comandi e parametri
Una volta stabilita una connessione a un'origine dati, è possibile eseguire i comandi e restituire i risultati dell'origine dati usando un oggetto <xref:System.Data.Common.DbCommand>. È possibile creare un comando usando uno dei costruttori di comando del provider di dati .NET Framework usato. I costruttori possono accettare argomenti facoltativi, ad esempio un'istruzione SQL da eseguire nell'origine dati, un oggetto <xref:System.Data.Common.DbConnection> o un oggetto <xref:System.Data.Common.DbTransaction>. È inoltre possibile configurare tali oggetti come proprietà del comando, nonché creare un comando per una particolare connessione usando il metodo <xref:System.Data.Common.DbConnection.CreateCommand%2A> di un oggetto `DbConnection`. È possibile configurare l'istruzione SQL eseguita dal comando tramite la proprietà <xref:System.Data.Common.DbCommand.CommandText%2A>.  
  
 In ogni provider di dati .NET Framework fornito con .NET Framework è incluso un oggetto `Command`. Nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbCommand>, in quello per SQL Server un oggetto <xref:System.Data.SqlClient.SqlCommand>, in quello per ODBC un oggetto <xref:System.Data.Odbc.OdbcCommand> e in quello per Oracle un oggetto <xref:System.Data.OracleClient.OracleCommand>.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Esecuzione di un comando](executing-a-command.md)  
 Viene descritto l'oggetto `Command` di ADO.NET e viene illustrato come usarlo per eseguire query e comandi su un'origine dati.  
  
 [Configurazione di parametri e tipi di dati dei parametri](configuring-parameters-and-parameter-data-types.md)  
 Viene descritto l'uso dei parametri di `Command`, inclusa la direzione, i tipi di dati e la sintassi.  
  
 [Generazione di comandi tramite CommandBuilders](generating-commands-with-commandbuilders.md)  
 Viene descritto come usare compilatori di comandi per generare automaticamente i comandi INSERT, UPDATE e DELETE per un `DataAdapter` in cui è presente il comando SELECT di una singola tabella.  
  
 [Recupero di un valore singolo da un database](obtaining-a-single-value-from-a-database.md)  
 Viene descritto come usare il metodo `ExecuteScalar` di un oggetto `Command` per restituire un singolo valore in una query sul database.  
  
 [Uso di comandi per modificare i dati](using-commands-to-modify-data.md)  
 Viene descritto come usare un provider di dati per eseguire stored procedure o istruzioni DDL (Data Definition Language).  
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Oggetti DataSet, DataTable e DataView](./dataset-datatable-dataview/index.md)
- [Connessione a un'origine dati](connecting-to-a-data-source.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
