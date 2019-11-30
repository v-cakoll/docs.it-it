---
title: Considerazioni sulla migrazione (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: 168aec6ef369f446cfac22ee5c4361fa06aaf16d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569445"
---
# <a name="migration-considerations-entity-framework"></a>Considerazioni sulla migrazione (Entity Framework)
Il Entity Framework ADO.NET offre diversi vantaggi a un'applicazione esistente. Uno dei principali vantaggi consiste nella possibilità di usare un modello concettuale per separare le strutture di dati impiegate dall'applicazione dallo schema presente nell'origine dati in modo da apportare facilmente modifiche future al modello di archiviazione o all'origine dati stessa senza effettuare modifiche di compensazione nell'applicazione. Per ulteriori informazioni sui vantaggi derivanti dall'utilizzo del Entity Framework, vedere [panoramica Entity Framework](overview.md) e [Entity Data Model](../entity-data-model.md).  
  
 Per sfruttare i vantaggi offerti dalla Entity Framework, è possibile eseguire la migrazione di un'applicazione esistente al Entity Framework. Alcune attività sono comuni a tutte le applicazioni migrate. Queste attività comuni includono l'aggiornamento dell'applicazione per l'utilizzo del .NET Framework a partire dalla versione 3,5 Service Pack 1 (SP1), la definizione di modelli e il mapping e la configurazione della Entity Framework. Quando si esegue la migrazione di un'applicazione alla Entity Framework, è necessario tenere presenti ulteriori considerazioni. che dipendono dal tipo di applicazione migrato e dalla funzionalità specifica dell'applicazione. In questo argomento vengono fornite informazioni grazie alle quali è possibile scegliere l'approccio ideale da usare quando si aggiorna un'applicazione esistente.  
  
## <a name="general-migration-considerations"></a>Considerazioni generali sulla migrazione  
 Quando si esegue la migrazione di un'applicazione all'Entity Framework, si applicano le considerazioni seguenti:  
  
- È possibile eseguire la migrazione di qualsiasi applicazione che utilizza il .NET Framework a partire dalla versione 3,5 SP1 al Entity Framework, purché il provider di dati per l'origine dati utilizzata dall'applicazione supporti il Entity Framework.  
  
- Entity Framework potrebbe non supportare tutte le funzionalità di un provider dell'origine dati, anche se supportato da tale provider.  
  
- Nel caso di applicazioni complesse o di grandi dimensioni non è necessario eseguire la migrazione dell'intera applicazione a Entity Framework in una sola volta. È comunque necessario sostituire le parti dell'applicazione che non usano Entity Framework quando si cambia l'origine dati.  
  
- La connessione del provider di dati utilizzata dal Entity Framework può essere condivisa con altre parti dell'applicazione perché il Entity Framework utilizza i provider di dati ADO.NET per accedere all'origine dati. Il provider SqlClient viene ad esempio usato da Entity Framework per accedere a un database di SQL Server. Per ulteriori informazioni, vedere [provider EntityClient per la Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Attività comuni di migrazione  
 Il percorso di migrazione di un'applicazione esistente al Entity Framework dipende dal tipo di applicazione e dalla strategia di accesso ai dati esistente. Tuttavia, quando si esegue la migrazione di un'applicazione esistente alla Entity Framework, è necessario eseguire sempre le attività seguenti.  
  
> [!NOTE]
> Tutte queste attività vengono eseguite automaticamente quando si usano gli strumenti di Entity Data Model a partire da Visual Studio 2008. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
1. Aggiornamento dell'applicazione.  
  
     Un progetto creato con una versione precedente di Visual Studio e il .NET Framework deve essere aggiornato per usare Visual Studio 2008 SP1 e il .NET Framework a partire dalla versione 3,5 SP1.  
  
2. Definire i modelli e il mapping.  
  
     I file di modello e di mapping definiscono entità nel modello concettuale, ovvero le strutture dell'origine dati, quali le tabelle, le stored procedure e le visualizzazioni, e il mapping tra le entità e tali strutture. Per altre informazioni, vedere [procedura: definire manualmente i file di modello e di mapping](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).  
  
     I tipi definiti nel modello di archiviazione devono corrispondere al nome degli oggetti presenti nell'origine dati. Se nell'applicazione esistente i dati sono esposti come oggetti, è necessario assicurarsi che le entità e le proprietà definite nel modello concettuale corrispondano ai nomi delle proprietà e delle classi di dati esistenti. Per altre informazioni, vedere [procedura: personalizzare i file di modellazione e di mapping per usare oggetti personalizzati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100)).  
  
    > [!NOTE]
    > Entity Data Model Designer consente di rinominare le entità presenti nel modello concettuale in modo che corrispondano agli oggetti esistenti. Per ulteriori informazioni, vedere [Entity Data Model Designer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3. Definizione della stringa di connessione.  
  
     Il Entity Framework utilizza una stringa di connessione formattata in modo specifico durante l'esecuzione di query su un modello concettuale. In tale stringa sono incapsulate le informazioni relative ai file di modello e di mapping e alla connessione all'origine dati. Per altre informazioni, vedere [procedura: definire la stringa di connessione](how-to-define-the-connection-string.md).  
  
4. Configurare il progetto di Visual Studio.  
  
     I riferimenti agli assembly Entity Framework e ai file di modello e di mapping devono essere aggiunti al progetto di Visual Studio. L'aggiunta di tali file di mapping al progetto consente di garantirne la distribuzione con l'applicazione nel percorso indicato nella stringa di connessione. Per altre informazioni, vedere [procedura: configurare manualmente un progetto di Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Considerazioni per le applicazioni con oggetti esistenti  
 A partire da .NET Framework 4, l'Entity Framework supporta oggetti POCO (Plain Old) CLR, detti anche oggetti che non riconoscono la persistenza. Nella maggior parte dei casi, gli oggetti esistenti possono funzionare con il Entity Framework apportando modifiche minime. Per ulteriori informazioni, vedere [utilizzo di entità poco](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). È inoltre possibile eseguire la migrazione di un'applicazione al Entity Framework e utilizzare le classi di dati generate dagli strumenti di Entity Framework. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Considerazioni per le applicazioni che usano provider ADO.NET  
 I provider ADO.NET, ad esempio SqlClient, consentono di eseguire query su un'origine dati per restituire dati tabulari. I dati possono anche essere caricati in un set di dati ADO.NET. Nell'elenco seguente vengono descritte le considerazioni per l'aggiornamento di un'applicazione che utilizza un provider ADO.NET esistente:  
  
- Visualizzazione di dati tabulari mediante un lettore dati.  

  È possibile prendere in considerazione l'esecuzione di una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] usando il provider EntityClient e l'enumerazione tramite l'oggetto <xref:System.Data.EntityClient.EntityDataReader> restituito. Eseguire questa operazione solo se l'applicazione Visualizza dati tabulari mediante un lettore dati e non richiede le funzionalità fornite dal Entity Framework per materializzazione i dati negli oggetti, il rilevamento delle modifiche e la creazione di aggiornamenti. È possibile continuare a utilizzare il codice di accesso ai dati esistente che applica gli aggiornamenti all'origine dati servendosi comunque della connessione esistente cui si accede dalla proprietà <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> di <xref:System.Data.EntityClient.EntityConnection>. Per ulteriori informazioni, vedere [provider EntityClient per la Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
- Uso di set di dati.  

  Il Entity Framework offre molte delle stesse funzionalità fornite dal set di dati, tra cui la persistenza in memoria, il rilevamento delle modifiche, la data binding e la serializzazione degli oggetti come dati XML. Per ulteriori informazioni, vedere [utilizzo di oggetti](working-with-objects.md).  
  
  Se il Entity Framework non fornisce la funzionalità del set di dati necessario per l'applicazione, è comunque possibile sfruttare i vantaggi delle query LINQ usando LINQ to DataSet. Per altre informazioni, vedere [LINQ to DataSet](../linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Considerazioni per le applicazioni che associano dati ai controlli  
 Il .NET Framework consente di incapsulare i dati in un'origine dati, ad esempio un set di dati o un controllo origine dati ASP.NET, e quindi di associare gli elementi dell'interfaccia utente a tali controlli dati. Nell'elenco seguente vengono riportate e illustrate le considerazioni relative all'associazione dei controlli ai dati di Entity Framework.  
  
- Associazione di dati a controlli.  

  Quando si esegue una query sul modello concettuale, il Entity Framework restituisce i dati come oggetti che sono istanze dei tipi di entità. Questi oggetti possono essere associati direttamente ai controlli e questa associazione supporta gli aggiornamenti. Ciò significa che le modifiche apportate ai dati in un controllo, ad esempio una riga in un <xref:System.Windows.Forms.DataGridView>, vengono salvate automaticamente nel database quando viene chiamato il metodo <xref:System.Data.Objects.ObjectContext.SaveChanges%2A>.  
  
  Se l'applicazione enumera i risultati di una query per visualizzare i dati in un controllo <xref:System.Windows.Forms.DataGridView> o in un altro tipo di controllo che supporti l'associazione dati, è possibile modificarla in modo da associare il controllo al risultato di un oggetto <xref:System.Data.Objects.ObjectQuery%601>.  
  
  Per ulteriori informazioni, vedere [associazione di oggetti ai controlli](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- Controlli origine dati ASP.NET.  

  Il Entity Framework include un controllo origine dati progettato per semplificare data binding nelle applicazioni Web ASP.NET. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo server Web EntityDataSource](https://docs.microsoft.com/previous-versions/aspnet/cc488502(v=vs.100)).  
  
## <a name="other-considerations"></a>Altre considerazioni  
 Di seguito vengono riportate le considerazioni di cui è possibile tenere conto quando si esegue la migrazione di tipi specifici di applicazione a Entity Framework.  
  
- Applicazioni che espongono servizi di dati.  

  I servizi e le applicazioni Web basati su Windows Communication Foundation (WCF) espongono i dati provenienti da un'origine dati sottostante usando un formato di messaggistica di richiesta/risposta XML. Il Entity Framework supporta la serializzazione di oggetti entità utilizzando la serializzazione del contratto dati binaria, XML o WCF. I tipi di serializzazione binaria e WCF implicano la serializzazione completa degli oggetti grafici. Per altre informazioni, vedere [compilazione di applicazioni a più livelli](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Applicazioni che usano dati XML.  

  La serializzazione di oggetti consente di creare Entity Framework servizi dati. Tali servizi forniscono dati alle applicazioni che usano dati XML, quali le applicazioni Internet basate su Ajax. In questi casi, è consigliabile usare WCF Data Services. Questi servizi dati sono basati sulla Entity Data Model e forniscono accesso dinamico ai dati delle entità tramite azioni HTTP REST (Representational State Transfer) standard, ad esempio GET, PUT e POST. Per altre informazioni, vedere [WCF Data Services 4.5](../../wcf/index.md).  
  
  Il Entity Framework non supporta un tipo di dati XML nativo. Ciò significa che, quando viene eseguito il mapping di un'entità a una tabella con una colonna XML, la proprietà dell'entità equivalente della colonna XML è una stringa. Gli oggetti possono essere disconnessi e serializzati come XML. Per ulteriori informazioni, vedere [serializzazione di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Se l'applicazione richiede la funzionalità di query sui dati XML, è comunque possibile sfruttare i vantaggi delle query LINQ usando LINQ to XML. Per ulteriori informazioni, vedere [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) o [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
- Applicazioni che gestiscono lo stato.  

  Le applicazioni Web ASP.NET devono gestire spesso lo stato di una pagina Web o di una sessione utente. Gli oggetti in un'istanza di <xref:System.Data.Objects.ObjectContext> possono essere archiviati nello stato di visualizzazione del client o nello stato della sessione sul server e successivamente recuperati e ricollegati a un nuovo contesto dell'oggetto. Per ulteriori informazioni, vedere [collegamento e scollegamento di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Considerazioni sulla distribuzione](deployment-considerations.md)
- [Terminologia relativa a Entity Framework](terminology.md)
