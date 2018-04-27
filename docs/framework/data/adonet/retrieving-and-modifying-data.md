---
title: Recupero e modifica di dati in ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 05760e7295606f700f72e5a3af14e395bcc5d820
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Recupero e modifica di dati in ADO.NET
La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database. I provider di dati .NET Framework di ADO.NET fungono da ponte tra un'applicazione e un'origine dati, consentendo di eseguire comandi e di recuperare i dati utilizzando un **DataReader** o **DataAdapter** . Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database. In ADO.NET l'aggiornamento dei dati prevede l'uso di **DataAdapter** e <xref:System.Data.DataSet>, e **comando** degli oggetti può anche comprendere l'utilizzo delle transazioni.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Connessione a un'origine dati](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.  
  
 [Stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings.md)  
 Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.  
  
 [Pool di connessioni](../../../../docs/framework/data/adonet/connection-pooling.md)  
 Vengono descritti i pool di connessioni per i provider di dati .NET Framework.  
  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.  
  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.  
  
 [Transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.  
  
 [Recupero di identità o di valori numerati automaticamente](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Fornisce un esempio di mapping i valori generati per un **identità** colonna in una tabella di SQL Server o per un **contatore** campo in una tabella di Microsoft Access, a una colonna di una riga inserita in una tabella. Viene descritta l'unione di valori Identity in un oggetto `DataTable`.  
  
 [Recupero di dati binari](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior`.`SequentialAccess` Per modificare il comportamento predefinito di un `DataReader`.  
  
 [Modifica di dati con stored procedure](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.  
  
 [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.  
  
 [Traccia dati in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.  
  
 [Contatori delle prestazioni](../../../../docs/framework/data/adonet/performance-counters.md)  
 Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.  
  
 [Programmazione asincrona](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Viene descritto il supporto di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] per la programmazione asincrona.  
  
 [Supporto per flusso SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Viene illustrato come scrivere applicazioni che i dati del flusso da SQL Server senza che venga completamente caricata in memoria.  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping dei tipi di dati in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Protezione delle applicazioni ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server e ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
