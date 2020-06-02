---
title: LINQ e ADO.NET
description: Informazioni su come creare query basate su set nel codice dell'applicazione mediante LINQ (Language-Integrated Query) in ADO.NET senza dover utilizzare un linguaggio di query separato.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: a663d36f1e07c53d20e22d051e38123bd8873f06
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286753"
---
# <a name="linq-and-adonet"></a>LINQ e ADO.NET

Attualmente, molti sviluppatori aziendali devono usare due o più linguaggi di programmazione: un linguaggio di alto livello per la logica di business e i livelli di presentazione (ad esempio Visual C# o Visual Basic) e un linguaggio di query per interagire con il database (ad esempio Transact-SQL). Tale necessità non solo richiede una conoscenza approfondita di diversi linguaggi da parte degli sviluppatori, ma provoca anche problemi di mancata corrispondenza tra linguaggi nell'ambiente di sviluppo. Ad esempio, in un'applicazione che usa un'API di accesso ai dati per eseguire una query su un database la query viene specificata come valore letterale stringa racchiuso tra virgolette. Questa stringa di query non è leggibile per il compilatore e non viene verificata la presenza di errori, ad esempio una sintassi non valida o se le colonne o le righe a cui fa riferimento esistono effettivamente. Non viene eseguito il controllo dei tipi dei parametri della query, né è disponibile il supporto per `IntelliSense`.  
  
 LINQ (Language-Integrated Query) consente agli sviluppatori di creare query basate su set nel codice dell'applicazione, senza dover utilizzare un linguaggio di query distinto. È possibile scrivere query LINQ su varie origini dati enumerabili (ovvero un'origine dati che implementa l' <xref:System.Collections.IEnumerable> interfaccia), ad esempio strutture di dati in memoria, documenti XML, database SQL e <xref:System.Data.DataSet> oggetti. Sebbene queste origini dati enumerabili vengono implementate in modi diversi, espongono tutte la stessa sintassi e gli stessi costrutti di linguaggio. Poiché è possibile formare query nel linguaggio di programmazione stesso, non è necessario usare un altro linguaggio di query incorporato sotto forma di valori letterali stringa che il compilatore non è in grado di riconoscere o verificare. L'integrazione di query nel linguaggio di programmazione consente inoltre ai programmatori di Visual Studio di essere più produttivi offrendo il controllo del tipo e della sintassi in fase di compilazione, e `IntelliSense` . Queste funzionalità riducono l'esigenza di debug e correzione degli errori delle query.  
  
 Il trasferimento di dati da tabelle SQL in oggetti in memoria è un'operazione spesso laboriosa e soggetta a errori. Il provider LINQ implementato da LINQ to DataSet e [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] converte i dati di origine in <xref:System.Collections.IEnumerable> raccolte di oggetti basati su. Il programmatore visualizza sempre i dati sotto forma di una raccolta <xref:System.Collections.IEnumerable>, sia quando si esegue una query che quando si effettua un aggiornamento. Per la scrittura di query da eseguire su tali raccolte, viene fornito il supporto per `IntelliSense`.  
  
 Sono disponibili tre tecnologie LINQ (Language-Integrated Query) separate: LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] e LINQ to Entities. LINQ to DataSet offre una query più completa e ottimizzata su <xref:System.Data.DataSet> e [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database SQL Server e LINQ to Entities consente di eseguire query su un Entity Data Model.  
  
 Nel diagramma seguente viene fornita una panoramica della correlazione tra le tecnologie LINQ ADO.NET, i linguaggi di programmazione di alto livello e le origini dati con supporto LINQ.  
  
 ![Panoramica di LINQ to ADO.NET](./media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Per ulteriori informazioni su LINQ, vedere [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 Nelle sezioni seguenti vengono fornite ulteriori informazioni su LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] e LINQ to Entities.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet>È un elemento chiave del modello di programmazione disconnesso su cui si basa ADO.NET ed è ampiamente usato. LINQ to DataSet consente agli sviluppatori di compilare funzionalità di query più complesse in utilizzando <xref:System.Data.DataSet> lo stesso meccanismo di formulazione delle query disponibile per molte altre origini dati. Per altre informazioni, vedere [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] è uno strumento utile per gli sviluppatori che non necessitano del mapping a un modello concettuale. Utilizzando [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] è possibile utilizzare il modello di programmazione LINQ direttamente sullo schema di database esistente. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]consente agli sviluppatori di generare classi di .NET Framework che rappresentano i dati. Anziché eseguire il mapping a un modello di dati concettuale, tali classi generate vengono mappate direttamente a tabelle di database, visualizzazioni, stored procedure e funzioni definite dall'utente.  
  
 Con [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] , gli sviluppatori possono scrivere codice direttamente sullo schema di archiviazione utilizzando lo stesso modello di programmazione LINQ delle raccolte in memoria e <xref:System.Data.DataSet> , oltre ad altre origini dati, ad esempio XML. Per altre informazioni, vedere [LINQ to SQL](./sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 La maggior parte delle applicazioni viene attualmente scritta basandosi su database relazionali. A un certo punto è necessario che queste applicazioni interagiscano con i dati rappresentati in forma relazionale. Gli schemi di database non costituiscono sempre la soluzione ideale per la compilazione di applicazioni e i modelli concettuali di applicazione non corrispondono ai modelli logici di database. Il Entity Data Model è un modello di dati concettuale che può essere utilizzato per modellare i dati di un determinato dominio in modo che le applicazioni possano interagire con i dati come oggetti. Per ulteriori informazioni, vedere [ADO.NET Entity Framework](./ef/index.md).  
  
 Tramite Entity Data Model, i dati relazionali vengono esposti come oggetti nell'ambiente .NET. Questo rende il livello di oggetto una destinazione ideale per il supporto LINQ, consentendo agli sviluppatori di formulare query sul database dal linguaggio utilizzato per compilare la logica di business. Questa funzionalità è nota come LINQ to Entities. Per ulteriori informazioni, vedere [LINQ to Entities](./ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to DataSet](linq-to-dataset.md)
- [LINQ to SQL](./sql/linq/index.md)
- [LINQ to Entities](./ef/language-reference/linq-to-entities.md)
- [LINQ (Language Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
