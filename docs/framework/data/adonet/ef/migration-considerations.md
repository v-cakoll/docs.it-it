---
title: Considerazioni sulla migrazione (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: b6224dcf883daef7b35ef50b7556fc568e433a46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310421"
---
# <a name="migration-considerations-entity-framework"></a>Considerazioni sulla migrazione (Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework offre diversi vantaggi alle applicazioni esistenti. Uno dei principali vantaggi consiste nella possibilità di usare un modello concettuale per separare le strutture di dati impiegate dall'applicazione dallo schema presente nell'origine dati in modo da apportare facilmente modifiche future al modello di archiviazione o all'origine dati stessa senza effettuare modifiche di compensazione nell'applicazione. Per altre informazioni sui vantaggi dell'uso di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], vedere [Panoramica di Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) e [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Per sfruttare i vantaggi del [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è possibile eseguire la migrazione di un'applicazione esistente per il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Alcune attività sono comuni a tutte le applicazioni migrate. Queste figurano l'aggiornamento dell'applicazione per usare il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 Service Pack 1 (SP1), la definizione di modelli e mapping e la configurazione di Entity Framework. Quando si esegue la migrazione di un'applicazione a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] occorre tenere presenti considerazioni aggiuntive. che dipendono dal tipo di applicazione migrato e dalla funzionalità specifica dell'applicazione. In questo argomento vengono fornite informazioni grazie alle quali è possibile scegliere l'approccio ideale da usare quando si aggiorna un'applicazione esistente.  
  
## <a name="general-migration-considerations"></a>Considerazioni generali sulla migrazione  
 Le considerazioni seguenti riguardano l'esecuzione della migrazione di un'applicazione ad [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   Qualsiasi applicazione che utilizza il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 SP1 possono essere migrati a Entity Framework, purché il provider di dati per l'origine dati utilizzata dall'applicazione supporta Entity Framework.  
  
-   Entity Framework potrebbe non supportare tutte le funzionalità di un provider dell'origine dati, anche se supportato da tale provider.  
  
-   Nel caso di applicazioni complesse o di grandi dimensioni non è necessario eseguire la migrazione dell'intera applicazione a Entity Framework in una sola volta. È comunque necessario sostituire le parti dell'applicazione che non usano Entity Framework quando si cambia l'origine dati.  
  
-   La connessione al provider di dati usata da Entity Framework può essere condivisa con altre parti dell'applicazione in quanto [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] usa provider di dati [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] per accedere all'origine dati. Il provider SqlClient viene ad esempio usato da Entity Framework per accedere a un database di SQL Server. Per altre informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Attività comuni di migrazione  
 Il percorso per eseguire la migrazione di un'applicazione esistente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] dipende dal tipo di applicazione e dalla strategia di accesso ai dati esistente. È invece necessario effettuare sempre le attività seguenti quando si esegue la migrazione di un'applicazione esistente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Tutte queste attività vengono eseguite automaticamente quando si usano gli strumenti di Entity Data Model a partire da Visual Studio 2008. Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
1. Aggiornamento dell'applicazione.  
  
     Un progetto creato utilizzando una versione precedente di Visual Studio e il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] deve essere aggiornato per usare Visual Studio 2008 SP1 e [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partire dalla versione 3.5 SP1.  
  
2. Definire i modelli e il mapping.  
  
     I file di modello e di mapping definiscono entità nel modello concettuale, ovvero le strutture dell'origine dati, quali le tabelle, le stored procedure e le visualizzazioni, e il mapping tra le entità e tali strutture. Per altre informazioni, vedere [Procedura: File di Mapping e definire il modello manualmente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).  
  
     I tipi definiti nel modello di archiviazione devono corrispondere al nome degli oggetti presenti nell'origine dati. Se nell'applicazione esistente i dati sono esposti come oggetti, è necessario assicurarsi che le entità e le proprietà definite nel modello concettuale corrispondano ai nomi delle proprietà e delle classi di dati esistenti. Per altre informazioni, vedere [Procedura: Personalizzare i file di Mapping per utilizzarli con oggetti personalizzati e di modellazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100)).  
  
    > [!NOTE]
    >  Entity Data Model Designer consente di rinominare le entità presenti nel modello concettuale in modo che corrispondano agli oggetti esistenti. Per altre informazioni, vedere [Entity Data Model Designer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3. Definizione della stringa di connessione.  
  
     In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] viene usata una stringa di connessione con formattazione speciale per l'esecuzione di query sul modello concettuale. In tale stringa sono incapsulate le informazioni relative ai file di modello e di mapping e alla connessione all'origine dati. Per altre informazioni, vedere [Procedura: Definire la stringa di connessione](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4. Configurare il progetto di Visual Studio.  
  
     I riferimenti a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] file di assembly e il modello e i mapping devono essere aggiunti al progetto di Visual Studio. L'aggiunta di tali file di mapping al progetto consente di garantirne la distribuzione con l'applicazione nel percorso indicato nella stringa di connessione. Per altre informazioni, vedere [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Considerazioni per le applicazioni con oggetti esistenti  
 A partire da [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versione 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta gli oggetti POCO ("plain old" CLR objects), denominati anche oggetti che non riconoscono la persistenza. Nella maggior parte dei casi, gli oggetti esistenti possono essere usati con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] apportando piccole modifiche. Per altre informazioni, vedere [utilizzano entità POCO](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). È anche possibile migrare un'applicazione per il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e usare le classi di dati generate dagli strumenti di Entity Framework. Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Considerazioni per le applicazioni che usano provider ADO.NET  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] provider, ad esempio SqlClient, consentono di eseguire una query di un'origine dati per restituire dati tabulari. I dati possono anche essere caricati in un [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] set di dati. Nell'elenco seguente vengono riportate e illustrate le considerazioni che riguardano l'aggiornamento di un'applicazione che usa un provider [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] esistente:  
  
- Visualizzazione di dati tabulari mediante un lettore dati.  

  È possibile eseguire un' [!INCLUDE[esql](../../../../../includes/esql-md.md)] eseguire una query utilizzando il provider EntityClient ed enumerare l'oggetto restituito <xref:System.Data.EntityClient.EntityDataReader> oggetto. Eseguire questa operazione solo se l'applicazione visualizza dati tabulari mediante un lettore dati e non richiede le funzionalità offerte da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] per la materializzazione dei dati in oggetti, il rilevamento delle modifiche e l'applicazione di aggiornamenti. È possibile continuare a utilizzare il codice di accesso ai dati esistente che applica gli aggiornamenti all'origine dati servendosi comunque della connessione esistente cui si accede dalla proprietà <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> di <xref:System.Data.EntityClient.EntityConnection>. Per altre informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
- Uso di set di dati.  

  Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] fornisce molte delle stesse funzionalità fornite dal set di dati, inclusi la persistenza in memoria, rilevamento delle modifiche, l'associazione dati e la serializzazione degli oggetti come dati XML. Per altre informazioni, vedere [utilizzo di oggetti](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
  Se il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] non fornisce la funzionalità del set di dati richiesti dall'applicazione, è comunque sfruttare i vantaggi delle query LINQ usando [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]. Per altre informazioni, vedere [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Considerazioni per le applicazioni che associano dati ai controlli  
 Il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] consente di incapsulare i dati in un'origine dati, ad esempio un set di dati o un [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] dati controllo del codice sorgente e quindi associare gli elementi dell'interfaccia utente ai controlli dati. Nell'elenco seguente vengono riportate e illustrate le considerazioni relative all'associazione dei controlli ai dati di Entity Framework.  
  
- Associazione di dati a controlli.  

  Quando si esegue una query del modello concettuale, il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] restituisce i dati come oggetti che sono istanze dei tipi di entità. Questi oggetti possono essere associati direttamente a controlli e questa associazione supporta gli aggiornamenti. Ciò significa che le modifiche apportate ai dati in un controllo, ad esempio una riga in una <xref:System.Windows.Forms.DataGridView>automaticamente vengono salvati nel database quando il <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> viene chiamato il metodo.  
  
  Se l'applicazione enumera i risultati di una query per visualizzare i dati in un controllo <xref:System.Windows.Forms.DataGridView> o in un altro tipo di controllo che supporti l'associazione dati, è possibile modificarla in modo da associare il controllo al risultato di un oggetto <xref:System.Data.Objects.ObjectQuery%601>.  
  
  Per altre informazioni, vedere [associazione di oggetti ai controlli](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- Controlli origine dati [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  

  Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] include un controllo origine dati progettato per semplificare il data binding in [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] applicazioni Web. Per altre informazioni, vedere [Cenni preliminari sul controllo Server Web EntityDataSource](https://docs.microsoft.com/previous-versions/aspnet/cc488502(v=vs.100)).  
  
## <a name="other-considerations"></a>Altre considerazioni  
 Di seguito vengono riportate le considerazioni di cui è possibile tenere conto quando si esegue la migrazione di tipi specifici di applicazione a Entity Framework.  
  
- Applicazioni che espongono servizi di dati.  

  I servizi e le applicazioni Web basati su Windows Communication Foundation (WCF) espongono i dati provenienti da un'origine dati sottostante usando un formato di messaggistica di richiesta/risposta XML. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta la serializzazione degli oggetti entità mediante la serializzazione dei contratti di dati WCF, binaria o XML. I tipi di serializzazione binaria e WCF implicano la serializzazione completa degli oggetti grafici. Per altre informazioni, vedere [compilazione di applicazioni a N livelli](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Applicazioni che usano dati XML.  

  La serializzazione degli oggetti consente di creare servizi di dati di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Tali servizi forniscono dati alle applicazioni che usano dati XML, quali le applicazioni Internet basate su Ajax. In questi casi usare [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Tali servizi sono basati su Entity Data Model e forniscono accesso dinamico ai dati delle entità tramite azioni Representational State Transfer (REST) HTTP standard, come GET, PUT e POST. Per altre informazioni, vedere [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] non supporta un tipo di dati XML nativo. Ciò significa che, quando viene eseguito il mapping di un'entità a una tabella con una colonna XML, la proprietà dell'entità equivalente della colonna XML è una stringa. Gli oggetti possono essere disconnessi e serializzati come XML. Per altre informazioni, vedere [serializzazione di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Se l'applicazione richiede la funzionalità di query sui dati XML, è comunque possibile sfruttare i vantaggi delle query LINQ usando LINQ to XML. Per altre informazioni, vedere [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) oppure [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
- Applicazioni che gestiscono lo stato.  

  [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Le applicazioni Web devono gestire frequentemente lo stato di una pagina Web o di una sessione utente. Gli oggetti in un <xref:System.Data.Objects.ObjectContext> istanza può essere archiviata nello stato di visualizzazione client o nello stato della sessione sul server e in seguito recuperata e successivamente, ricollegarli a un nuovo contesto dell'oggetto. Per altre informazioni, vedere [collegamento e scollegamento di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Considerazioni sulla distribuzione](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)
- [Terminologia relativa a Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)
