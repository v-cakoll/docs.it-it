---
title: Opzioni e linee guida per la tecnologia
ms.date: 03/30/2017
ms.assetid: c8577281-38e6-4ce5-b036-572039a4c3d8
ms.openlocfilehash: 1996a5f5b86715db099e52e163fd23be2497f5eb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094462"
---
# <a name="adonet-technology-options-and-guidelines"></a>Opzioni e linee guida per la tecnologia ADO.NET

ADO.NET Data Platform è una strategia multi-versione concepita per ridurre la quantità di codice e di interventi di manutenzione richiesti per gli sviluppatori consentendo loro di eseguire la programmazione per modelli di dati di entità concettuali. Questa piattaforma include ADO.NET Entity Framework e le tecnologie correlate.  
  
## <a name="entity-framework"></a>Entity Framework  
 ADO.NET Entity Framework è progettato per consentire agli sviluppatori di creare applicazioni di accesso ai dati tramite programmazione in base a un modello di applicazione concettuale anziché direttamente in base a uno schema di archiviazione relazionale. L'obiettivo è quello di ridurre la quantità di codice e le operazioni di manutenzione necessarie per le applicazioni orientate ai dati. Per ulteriori informazioni, vedere [ADO.NET Entity Framework](./ef/index.md).  
  
### <a name="entity-data-model-edm"></a>Entity Data Model (EDM)  
 Entity Data Model (EDM) è una specifica di progettazione che definisce i dati dell'applicazione come set di entità e relazioni. I dati in questo modello supportano il mapping relazionale oggetti e la programmabilità dei dati tra diverse applicazioni.  
  
### <a name="object-services"></a>Object Services  
 Object Services consente ai programmatori di interagire con il modello concettuale tramite un set di classi CLR (Common Language Runtime). Tali classi possono essere generate automaticamente dal modello concettuale o sviluppate in modo indipendente per riflettere la struttura del modello. Object Services offre inoltre supporto per l'infrastruttura per Entity Framework, inclusi servizi quali la gestione dello stato, il rilevamento delle modifiche, la risoluzione di identità, il caricamento e la navigazione di relazioni, la propagazione di modifiche degli oggetti in modifiche del database e il supporto per la compilazione di query per Entity SQL. Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
### <a name="linq-to-entities"></a>LINQ to Entities  
 LINQ to Entities è un'implementazione di LINQ (Language Integrated Query) che consente agli sviluppatori di creare query fortemente tipizzate sul contesto dell'oggetto di Entity Framework usando espressioni LINQ e operatori di query standard LINQ. LINQ to Entities consente agli sviluppatori di lavorare con un modello concettuale con un mapping relazionale a oggetti flessibile tra Microsoft SQL Server e database di terze parti. Per ulteriori informazioni, vedere [LINQ to Entities](./ef/language-reference/linq-to-entities.md).  
  
### <a name="entity-sql"></a>Entity SQL  
 Entity SQL è un linguaggio di query basato su testo progettato per interagire con Entity Data Model. Entity SQL è un dialetto SQL che contiene costrutti per l'esecuzione di query in termini di concetti di modellazione di livello superiore, ad esempio ereditarietà, tipi complessi e relazioni esplicite. Gli sviluppatori possono anche usare Entity SQL direttamente con Object Services. Per ulteriori informazioni, vedere la pagina relativa al [linguaggio Entity SQL](./ef/language-reference/entity-sql-language.md).  
  
### <a name="entityclient"></a>EntityClient  
 EntityClient è un nuovo provider di dati .NET Framework usato per l'interazione con Entity Data Model. Come gli altri provider di dati .NET Framework, EntityClient espone oggetti <xref:System.Data.EntityClient.EntityConnection> e <xref:System.Data.EntityClient.EntityCommand> che restituiscono un oggetto <xref:System.Data.EntityClient.EntityDataReader>. EntityClient usa il linguaggio Entity SQL, fornendo mapping flessibile ai provider di dati specifici dell'archiviazione. Per ulteriori informazioni, vedere [Provider EntityClient per Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
### <a name="entity-data-model-tools"></a>Strumenti di Entity Data Model  
 Entity Framework fornisce finestre di progettazione, procedure guidate e strumenti da riga di comando per semplificare la compilazione di applicazioni EDM. Il controllo EntityDataSource supporta scenari di data binding basati su EDM. La superficie di programmazione del controllo EntityDataSource è simile agli altri controlli origine dati in Visual Studio. Per ulteriori informazioni, vedere [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL è un'implementazione del mapping relazionale a oggetti che consente di modellare un database SQL Server tramite le classi di .NET Framework. LINQ to SQL consente di eseguire query sul database tramite LINQ, nonché di aggiornare, inserire ed eliminare dati da esso. LINQ to SQL supporta transazioni, visualizzazioni e stored procedure consentendo di integrare facilmente le regole relative alla convalida dei dati e alla logica di business nel modello dati. È possibile usare Progettazione relazionale oggetti per modellare le classi di entità e le associazioni basate sugli oggetti in un database. Per altre informazioni, vedere [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
## <a name="wcf-data-services"></a>WCF Data Services  
 WCF Data Services distribuisce i servizi dati sul Web o su una rete Intranet. I dati sono strutturati come entità e relazioni in base alle specifiche di Entity Data Model. I dati distribuiti in questo modello sono indirizzabili tramite il protocollo HTTP standard. Per altre informazioni, vedere [WCF Data Services 4.5](../wcf/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
- [Novità in ADO.NET](whats-new.md)
