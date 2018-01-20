---
title: Considerazioni sulla migrazione (Entity Framework)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8e4c1b06e5a3a7717b99379fd9bca2c5a8a14a6a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="migration-considerations-entity-framework"></a>Considerazioni sulla migrazione (Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework offre diversi vantaggi alle applicazioni esistenti. Uno dei principali vantaggi consiste nella possibilità di usare un modello concettuale per separare le strutture di dati impiegate dall'applicazione dallo schema presente nell'origine dati in modo da apportare facilmente modifiche future al modello di archiviazione o all'origine dati stessa senza effettuare modifiche di compensazione nell'applicazione. Per ulteriori informazioni sui vantaggi dell'utilizzo di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], vedere [Entity Framework Panoramica](../../../../../docs/framework/data/adonet/ef/overview.md) e [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Per sfruttare i vantaggi del [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è possibile eseguire la migrazione di un'applicazione esistente per il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Alcune attività sono comuni a tutte le applicazioni migrate. Tra queste figurano l'aggiornamento dell'applicazione per utilizzare il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 Service Pack 1 (SP1), la definizione di modelli e mapping e configurazione di Entity Framework. Quando si esegue la migrazione di un'applicazione a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] occorre tenere presenti considerazioni aggiuntive. che dipendono dal tipo di applicazione migrato e dalla funzionalità specifica dell'applicazione. In questo argomento vengono fornite informazioni grazie alle quali è possibile scegliere l'approccio ideale da usare quando si aggiorna un'applicazione esistente.  
  
## <a name="general-migration-considerations"></a>Considerazioni generali sulla migrazione  
 Le considerazioni seguenti riguardano l'esecuzione della migrazione di un'applicazione ad [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   Qualsiasi applicazione che utilizza il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 SP1 possono essere migrati a Entity Framework, come il provider di dati per l'origine dati utilizzata dall'applicazione supporta Entity Framework.  
  
-   Entity Framework potrebbe non supportare tutte le funzionalità di un provider dell'origine dati, anche se supportato da tale provider.  
  
-   Nel caso di applicazioni complesse o di grandi dimensioni non è necessario eseguire la migrazione dell'intera applicazione a Entity Framework in una sola volta. È comunque necessario sostituire le parti dell'applicazione che non usano Entity Framework quando si cambia l'origine dati.  
  
-   La connessione al provider di dati usata da Entity Framework può essere condivisa con altre parti dell'applicazione in quanto [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] usa provider di dati [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] per accedere all'origine dati. Il provider SqlClient viene ad esempio usato da Entity Framework per accedere a un database di SQL Server. Per ulteriori informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Attività comuni di migrazione  
 Il percorso per eseguire la migrazione di un'applicazione esistente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] dipende dal tipo di applicazione e dalla strategia di accesso ai dati esistente. È invece necessario effettuare sempre le attività seguenti quando si esegue la migrazione di un'applicazione esistente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Tutte le attività indicate vengono eseguite automaticamente quando si usano gli strumenti di Entity Data Model a partire da [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)]. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
1.  Aggiornamento dell'applicazione.  
  
     Un progetto creato utilizzando una versione precedente di [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] e [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] deve essere aggiornato per utilizzare [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 e [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 SP1.  
  
2.  Definire i modelli e il mapping.  
  
     I file di modello e di mapping definiscono entità nel modello concettuale, ovvero le strutture dell'origine dati, quali le tabelle, le stored procedure e le visualizzazioni, e il mapping tra le entità e tali strutture. Per ulteriori informazioni, vedere [procedura: definire manualmente i file di modello e Mapping](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  
  
     I tipi definiti nel modello di archiviazione devono corrispondere al nome degli oggetti presenti nell'origine dati. Se nell'applicazione esistente i dati sono esposti come oggetti, è necessario assicurarsi che le entità e le proprietà definite nel modello concettuale corrispondano ai nomi delle proprietà e delle classi di dati esistenti. Per ulteriori informazioni, vedere [procedura: personalizzare modellazione e i file di Mapping per l'utilizzo di oggetti personalizzati](http://msdn.microsoft.com/library/bb40c4db-0121-4e45-a167-8fb06707a708).  
  
    > [!NOTE]
    >  Entity Data Model Designer consente di rinominare le entità presenti nel modello concettuale in modo che corrispondano agli oggetti esistenti. Per ulteriori informazioni, vedere [Entity Data Model Designer](http://msdn.microsoft.com/library/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  
  
3.  Definizione della stringa di connessione.  
  
     In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] viene usata una stringa di connessione con formattazione speciale per l'esecuzione di query sul modello concettuale. In tale stringa sono incapsulate le informazioni relative ai file di modello e di mapping e alla connessione all'origine dati. Per ulteriori informazioni, vedere [procedura: definire la stringa di connessione](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Configurare il progetto [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)].  
  
     È necessario aggiungere i riferimenti agli assembly di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e i file di modello e di mapping al progetto [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]. L'aggiunta di tali file di mapping al progetto consente di garantirne la distribuzione con l'applicazione nel percorso indicato nella stringa di connessione. Per ulteriori informazioni, vedere [procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Considerazioni per le applicazioni con oggetti esistenti  
 A partire da [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versione 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta gli oggetti POCO ("plain old" CLR objects), denominati anche oggetti che non riconoscono la persistenza. Nella maggior parte dei casi, gli oggetti esistenti possono essere usati con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] apportando piccole modifiche. Per ulteriori informazioni, vedere [utilizzo delle entità POCO](http://msdn.microsoft.com/library/5e0fb82a-b6d1-41a1-b37b-c12db61629d3). È inoltre possibile migrare un'applicazione per il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e utilizzare le classi di dati che vengono generate dagli strumenti di Entity Framework. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Considerazioni per le applicazioni che usano provider ADO.NET  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]provider, ad esempio SqlClient, consentono di eseguire una query di un'origine dati per restituire dati tabulari. Dati inoltre possono essere caricati in un [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] set di dati. Nell'elenco seguente vengono riportate e illustrate le considerazioni che riguardano l'aggiornamento di un'applicazione che usa un provider [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] esistente:  
  
 Visualizzazione di dati tabulari mediante un lettore dati.  
 È possibile eseguire un [!INCLUDE[esql](../../../../../includes/esql-md.md)] query usando il provider EntityClient e l'enumerazione tramite l'oggetto restituito <xref:System.Data.EntityClient.EntityDataReader> oggetto. Eseguire questa operazione solo se l'applicazione visualizza dati tabulari mediante un lettore dati e non richiede le funzionalità offerte da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] per la materializzazione dei dati in oggetti, il rilevamento delle modifiche e l'applicazione di aggiornamenti. È possibile continuare a usare il codice di accesso ai dati esistente che applica gli aggiornamenti all'origine dati servendosi comunque della connessione esistente cui si accede dalla proprietà <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> di <xref:System.Data.EntityClient.EntityConnection>. Per ulteriori informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 Uso di set di dati.  
 Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] offre molte delle stesse funzionalità fornite dai set di dati, inclusi la persistenza in memoria, rilevamento delle, associazione dati e la serializzazione degli oggetti come dati XML. Per ulteriori informazioni, vedere [lavora con gli oggetti](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Se il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] non fornisce la funzionalità del set di dati richiesto dall'applicazione, è possibile comunque sfruttare dei vantaggi delle query LINQ tramite [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]. Per altre informazioni, vedere [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Considerazioni per le applicazioni che associano dati ai controlli  
 Il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] consente di incapsulare dati in un'origine dati, ad esempio un set di dati o un [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] controllo origine dati e quindi associare elementi dell'interfaccia utente ai controlli dati. Nell'elenco seguente vengono riportate e illustrate le considerazioni relative all'associazione dei controlli ai dati di Entity Framework.  
  
 Associazione di dati a controlli.  
 Quando si esegue una query al modello concettuale, il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] restituisce i dati come oggetti che sono istanze dei tipi di entità. Questi oggetti possono essere associati direttamente a controlli e l'associazione definita supporta gli aggiornamenti. Ciò significa che le modifiche apportate ai dati in un controllo, ad esempio una riga in un <xref:System.Windows.Forms.DataGridView>, automaticamente vengono salvati nel database quando il <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> metodo viene chiamato.  
  
 Se l'applicazione enumera i risultati di una query per visualizzare i dati in un controllo <xref:System.Windows.Forms.DataGridView> o in un altro tipo di controllo che supporti l'associazione dati, è possibile modificarla in modo da associare il controllo al risultato di un oggetto <xref:System.Data.Objects.ObjectQuery%601>.  
  
 Per ulteriori informazioni, vedere [Binding di oggetti ai controlli](http://msdn.microsoft.com/library/2fd34855-929b-4303-a91e-4bb69d958f2b).  
  
 Controlli origine dati [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
 Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] include un controllo origine dati progettato per semplificare il data binding in [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] applicazioni Web. Per ulteriori informazioni, vedere [controllo origine dati di Entity Framework](http://msdn.microsoft.com/library/1f09af00-9578-4744-a029-765710a3c83f).  
  
## <a name="other-considerations"></a>Altre considerazioni  
 Di seguito vengono riportate le considerazioni di cui è possibile tenere conto quando si esegue la migrazione di tipi specifici di applicazione a Entity Framework.  
  
 Applicazioni che espongono servizi di dati.  
 I servizi e le applicazioni Web basati su Windows Communication Foundation (WCF) espongono i dati provenienti da un'origine dati sottostante usando un formato di messaggistica di richiesta/risposta XML. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta la serializzazione degli oggetti entità mediante la serializzazione dei contratti di dati WCF, binaria o XML. I tipi di serializzazione binaria e WCF implicano la serializzazione completa degli oggetti grafici. Per ulteriori informazioni, vedere [compilazione di applicazioni a più livelli](http://msdn.microsoft.com/library/9439d2ba-6b5f-44e8-be65-8a442d922cbb).  
  
 Applicazioni che usano dati XML.  
 La serializzazione degli oggetti consente di creare servizi di dati di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Tali servizi forniscono dati alle applicazioni che usano dati XML, quali le applicazioni Internet basate su Ajax. In questi casi usare [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Questi servizi dati basati su Entity Data Model e forniscono accesso dinamico ai dati di entità tramite azioni Representational State Transfer (REST) HTTP standard, ad esempio GET, PUT e POST. Per ulteriori informazioni, vedere [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] non supporta un tipo di dati XML nativo. Ciò significa che, quando viene eseguito il mapping di un'entità a una tabella con una colonna XML, la proprietà dell'entità equivalente della colonna XML è una stringa. Gli oggetti possono essere disconnessi e serializzati come XML. Per ulteriori informazioni, vedere [serializzazione di oggetti](http://msdn.microsoft.com/library/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99).  
  
 Se l'applicazione richiede la funzionalità di query sui dati XML, è comunque possibile sfruttare i vantaggi delle query LINQ usando LINQ to XML. Per ulteriori informazioni, vedere [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 Applicazioni che gestiscono lo stato.  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]Applicazioni Web devono gestire frequentemente lo stato di una pagina Web o di una sessione utente. Gli oggetti in un <xref:System.Data.Objects.ObjectContext> istanza può essere archiviata nello stato di visualizzazione client o nello stato sessione sul server e in un secondo momento recuperata e ricollegata a un nuovo contesto dell'oggetto. Per ulteriori informazioni, vedere [collegamento e scollegamento di oggetti](http://msdn.microsoft.com/library/41d5c1ef-1b78-4502-aa10-7e1438d62d23).  
  
## <a name="see-also"></a>Vedere anche  
 [Considerazioni sulla distribuzione](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)  
 [Terminologia relativa a Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)
