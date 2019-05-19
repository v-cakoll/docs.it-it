---
title: Cenni preliminari su ADO.NET
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 0a47a2734e68b4c00aab077191d5257386cd6602
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877216"
---
# <a name="adonet-overview"></a>Cenni preliminari su ADO.NET
ADO.NET fornisce uniformità di accesso sia per origini dati quali SQL Server e XML, sia per origini dati esposte tramite OLE DB e ODBC. Le applicazioni consumer che supportano la condivisione dei dati sono in grado di usare ADO.NET per connettersi a tali origini dati e recuperare, gestire e aggiornare i dati contenuti.  
  
 ADO.NET consente di separare l'accesso ai dati dalla modifica dei dati in componenti discreti, utilizzabili separatamente o congiuntamente. In ADO.NET sono inclusi i provider di dati .NET Framework per la connessione a un database, l'esecuzione di comandi e il recupero di risultati. Tali risultati vengono elaborati direttamente, inseriti nell'oggetto <xref:System.Data.DataSet> di ADO.NET in modo da consentirne l'esposizione adeguata all'utente, combinati con dati provenienti da più origini o passati tra livelli. È inoltre possibile usare l'oggetto `DataSet` indipendentemente da un provider di dati .NET Framework per gestire i dati locali dell'applicazione o derivati da XML.  
  
 Le classi di ADO.NET sono incluse in System.Data.dll e vengono integrate con le classi XML presenti in System.Xml.dll. Per codice di esempio che si connette a un database, recuperare dati da esso e quindi visualizzare tali dati in una finestra della console, vedere [esempi di codice ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md).  
  
 ADO.NET fornisce agli sviluppatori che scrivono codice gestito funzionalità simili a quelle offerte da ADO (ActiveX Data Objects) agli sviluppatori con COM (Component Object Model) nativo. Per l'accesso ai dati nelle applicazioni .NET è consigliabile usare ADO.NET e non ADO.  
  
 ADO.NET fornisce il metodo più diretto per l'accesso ai dati in .NET Framework. Per un'astrazione di livello superiore che consente alle applicazioni di usare un modello concettuale anziché il modello di archiviazione sottostante, vedere la [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
 **Informativa sulla privacy**: Gli assembly System, System, DLL, System, System, SqlServerCe. dll e DataSetExtensions. dll non viene fatta distinzione tra un utente dati privati e pubblici.  Questi assembly non raccolgono, archiviano o trasportano i dati privati degli utenti, tuttavia possono essere usati da applicazioni di terze parti per tali scopi.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Architettura di ADO.NET](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 Viene fornita una descrizione generale dell'architettura e dei componenti di ADO.NET.  
  
 [Opzioni e linee guida per la tecnologia ADO.NET](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 Vengono descritti i prodotti e le tecnologie inclusi nella piattaforma EDM.  
  
 [LINQ e ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Viene descritta l'implementazione di Language-Integrated Query (LINQ) in ADO.NET e vengono forniti collegamenti agli argomenti rilevanti.  
  
 [Provider di dati .NET Framework](../../../../docs/framework/data/adonet/data-providers.md)  
 Vengono fornite informazioni generali sulle caratteristiche del provider di dati .NET Framework e dei provider di dati .NET Framework inclusi in ADO.NET.  
  
 [Oggetti DataSet ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 Vengono fornite informazioni generali relative all'architettura e ai componenti del `DataSet`.  
  
 [Esecuzione side-by-side in ADO.NET](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 Vengono descritte le differenze tra le diverse versioni di ADO.NET e le relative ripercussioni sull'esecuzione contemporanea di diverse versioni e la compatibilità tra applicazioni.  
  
 [Esempi di codice ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 Vengono forniti esempi di codice in cui vengono recuperati dati usando i provider di dati di ADO.NET.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Novità in ADO.NET](../../../../docs/framework/data/adonet/whats-new.md)  
 Vengono descritte le nuove funzionalità di ADO.NET.  
  
 [Protezione delle applicazioni ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Vengono descritte le tecniche che consentono di scrivere codice sicuro quando si usa ADO.NET.  
  
 [Mapping dei tipi di dati in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 Vengono descritti i mapping tra i tipi di dati .NET Framework e i provider di dati .NET Framework.  
  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Viene descritto come connettersi a un'origine dati, recuperare e modificare i dati, inclusi `DataReaders` e `DataAdapters`.  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
