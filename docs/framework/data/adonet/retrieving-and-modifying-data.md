---
title: Recupero e modifica di dati
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980054"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Recupero e modifica di dati in ADO.NET
La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database. I provider di dati .NET Framework di ADO.NET servono come bridge tra un'applicazione e un'origine dati, consentendo di eseguire i comandi e di recuperare i dati usando un **DataReader** o un **DataAdapter**. Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database. In ADO.NET l'aggiornamento dei dati comporta l'utilizzo degli oggetti **DataAdapter** e <xref:System.Data.DataSet>e **Command** ; Inoltre, può comportare l'utilizzo delle transazioni.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Connessione a un'origine dati](connecting-to-a-data-source.md)  
 Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.  
  
 [Stringhe di connessione](connection-strings.md)  
 Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.  
  
 [Pool di connessioni](connection-pooling.md)  
 Vengono descritti i pool di connessioni per i provider di dati .NET Framework.  
  
 [Comandi e parametri](commands-and-parameters.md)  
 Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.  
  
 [DataAdapter e DataReader](dataadapters-and-datareaders.md)  
 Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.  
  
 [Transazioni e concorrenza](transactions-and-concurrency.md)  
 Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.  
  
 [Recupero di identità o di valori numerati automaticamente](retrieving-identity-or-autonumber-values.md)  
 Viene fornito un esempio di mapping dei valori generati per una colonna **Identity** in una tabella SQL Server o per un campo **Autonumber** in una tabella di Microsoft Access a una colonna di una riga inserita in una tabella. Viene descritta l'unione di valori Identity in un oggetto `DataTable`.  
  
 [Recupero di dati binari](retrieving-binary-data.md)  
 Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior`.`SequentialAccess` per modificare il comportamento predefinito di un `DataReader`.  
  
 [Modifica di dati con stored procedure](modifying-data-with-stored-procedures.md)  
 Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.  
  
 [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)  
 Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.  
  
 [DbProviderFactories](dbproviderfactories.md)  
 Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.  
  
 [Traccia dati in ADO.NET](data-tracing.md)  
 Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.  
  
 [Performance Counters](performance-counters.md)  
 Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.  
  
 [Programmazione asincrona](asynchronous-programming.md)  
 Viene descritto il supporto ADO.NET per la programmazione asincrona.  
  
 [Supporto per flusso SqlClient](sqlclient-streaming-support.md)  
 Viene illustrato come scrivere applicazioni in grado di trasmettere dati da SQL Server senza che siano completamente caricate in memoria.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping dei tipi di dati in ADO.NET](data-type-mappings-in-ado-net.md)
- [Oggetti DataSet, DataTable e DataView](./dataset-datatable-dataview/index.md)
- [Protezione delle applicazioni ADO.NET](securing-ado-net-applications.md)
- [SQL Server e ADO.NET](./sql/index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
