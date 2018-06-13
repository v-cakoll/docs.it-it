---
title: Cenni preliminari sui componenti aggiuntivi di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 942f5706a83a9f9e9cd969701ed5625c57b76f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557862"
---
# <a name="wpf-add-ins-overview"></a>Cenni preliminari sui componenti aggiuntivi di WPF
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] include un modello di componente aggiuntivo che gli sviluppatori possono usare per creare applicazioni che supportano l'estendibilità mediante componenti aggiuntivi. Questo modello consente di creare componenti aggiuntivi che si integrano con le funzionalità dell'applicazione estendendole. In alcuni scenari le applicazioni devono anche visualizzare [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornite dai componenti aggiuntivi. Questo argomento mostra in che modo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per consentire questi scenari e illustra l'architettura che sta alla base, i suoi vantaggi e le sue limitazioni.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 È necessario avere familiarità con il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Per altre informazioni, vedere [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md).  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>Cenni preliminari sui componenti aggiuntivi  
 Per evitare le complessità legate alla ricompilazione e alla ridistribuzione di un'applicazione per incorporare nuove funzionalità, le applicazioni implementano meccanismi di estendibilità che consentono agli sviluppatori dell'applicazione e a quelli di terze parti di creare altre applicazioni che si integrano con esse. Il metodo più comune per supportare questo tipo di estendibilità consiste nell'usare i componenti aggiuntivi, noti anche come "plug-in". Di seguito sono riportati alcuni esempi di applicazioni reali che espongono l'estendibilità mediante componenti aggiuntivi:  
  
-   Componenti aggiuntivi di Internet Explorer.  
  
-   Plug-in di Windows Media Player.  
  
-   Componenti aggiuntivi di Visual Studio.  
  
 Il modello di componente aggiuntivo di Windows Media Player, ad esempio, consente agli sviluppatori di terze parti di implementare "plug-in" che estendono Windows Media Player in diversi modi, come tramite la creazione di decodificatori e codificatori per formati multimediali non supportati a livello nativo da Windows Media Player (ad esempio DVD, MP3), effetti audio e interfacce. Ogni modello di componente aggiuntivo è creato per esporre funzionalità univoche di un'applicazione, anche se ci sono diversi comportamenti ed entità comuni a tutti i modelli.  
  
 Le tre entità principali delle soluzioni tipiche di estendibilità mediante componenti aggiuntivi sono *contratti*, *componenti aggiuntivi* e *applicazioni host*. I contratti definiscono la modalità di integrazione dei componenti aggiuntivi con le applicazioni host in due modi:  
  
-   I componenti aggiuntivi si integrano con le funzionalità implementate dalle applicazioni host.  
  
-   Le applicazioni host espongono funzionalità con cui i componenti aggiuntivi si integrano.  
  
 Per poter usare i componenti aggiuntivi, le applicazioni host devono trovarli e caricarli in fase di esecuzione. Di conseguenza, le applicazioni che supportano i componenti aggiuntivi hanno le ulteriori responsabilità seguenti:  
  
-   **Individuazione**: trovare i componenti aggiuntivi conformi ai contratti supportati dalle applicazioni host.  
  
-   **Attivazione**: caricare ed eseguire i componenti aggiuntivi e stabilire la comunicazione con essi.  
  
-   **Isolamento**: usare i processi o i domini dell'applicazione per stabilire i limiti di isolamento che proteggono le applicazioni da potenziali problemi di sicurezza e di esecuzione relativi ai componenti aggiuntivi.  
  
-   **Comunicazione**: consentire ai componenti aggiuntivi e alle applicazioni host di comunicare tra loro oltre i limiti di isolamento, mediante la chiamata a metodi e il passaggio di dati.  
  
-   **Gestione della durata**: caricare e scaricare processi e domini dell'applicazione in modo netto e prevedibile (vedere [Domini applicazione](../../../../docs/framework/app-domains/application-domains.md)).  
  
-   **Controllo delle versioni**: assicurare che le applicazioni host e i componenti aggiuntivi possano continuare a comunicare quando vengono create nuove versioni.  
  
 In definitiva, lo sviluppo di un modello di componente aggiuntivo affidabile è un'operazione tutt'altro che banale. Per questo motivo, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornisce un'infrastruttura per la creazione di modelli di componente aggiuntivo.  
  
> [!NOTE]
>  Per informazioni più dettagliate sui componenti aggiuntivi, vedere [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Cenni preliminari sul modello di componente aggiuntivo .NET Framework  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello del componente aggiuntivo, vedere il <xref:System.AddIn> spazio dei nomi, contiene un set di tipi che sono progettati per semplificare lo sviluppo di componenti di estendibilità. L'unità fondamentale del modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] è il *contratto*, che definisce la modalità di comunicazione tra un'applicazione host e un componente aggiuntivo. Un contratto viene esposto a un'applicazione host usando una *vista* del contratto specifica dell'applicazione host. Analogamente, una *vista* del contratto specifica del componente aggiuntivo viene esposta al componente aggiuntivo. Un *adattatore* consente a un'applicazione host e a un componente aggiuntivo di comunicare tra le rispettive viste del contratto. Contratti, viste e adattatori vengono detti segmenti e un set di segmenti correlati costituisce una *pipeline*. Le pipeline sono gli elementi su cui il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] si basa per supportare l'individuazione, l'attivazione, l'isolamento di sicurezza, l'isolamento di esecuzione (tramite processi e domini dell'applicazione), la comunicazione, la gestione della durata e il controllo delle versioni.  
  
 Questo supporto consente agli sviluppatori di creare componenti aggiuntivi che si integrano con le funzionalità di un'applicazione host. Alcuni scenari richiedono tuttavia che le applicazioni host visualizzino [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornite dai componenti aggiuntivi. Dal momento che ogni tecnologia di presentazione in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ha il proprio modello di implementazione delle [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] non supporta alcuna tecnologia di presentazione specifica. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estende invece il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con supporto dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per i componenti aggiuntivi.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>Componenti aggiuntivi WPF  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], insieme al modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consente di gestire numerosi scenari che richiedono la visualizzazione di [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] dei componenti aggiuntivi nelle applicazioni host. In particolare, questi scenari vengono gestiti da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] con i due modelli di programmazione seguenti:  
  
1.  **Componente aggiuntivo che restituisce un'interfaccia utente**. Un componente aggiuntivo restituisce un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] all'applicazione host tramite una chiamata a un metodo, come definito dal contratto. Questo scenario viene usato nei casi seguenti:  
  
    -   L'aspetto di un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] restituita da un componente aggiuntivo dipende da dati o condizioni esistenti solo in fase di esecuzione, ad esempio report generati in modo dinamico.  
  
    -   L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per i servizi fornita da un componente aggiuntivo è diversa dall'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] delle applicazioni host che possono usare il componente aggiuntivo.  
  
    -   Il componente aggiuntivo svolge principalmente un servizio per l'applicazione host e segnala lo stato all'applicazione host con un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **Componente aggiuntivo che costituisce un'interfaccia utente**. Un componente aggiuntivo è un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], come definito dal contratto. Questo scenario viene usato nei casi seguenti:  
  
    -   Un componente aggiuntivo non fornisce alcun servizio eccetto la sua visualizzazione, come nel caso di un annuncio.  
  
    -   L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per i servizi fornita da un componente aggiuntivo è comune a tutte le applicazioni host che possono usare il componente aggiuntivo, ad esempio una calcolatrice o un'interfaccia di selezione colori.  
  
 Questi scenari richiedono che gli oggetti dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] possano essere passati tra i domini dell'applicazione del componente aggiuntivo e dell'applicazione host. Poiché il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] si basa sulla comunicazione remota tra domini dell'applicazione, gli oggetti passati devono poter essere usati in remoto.  
  
 Un oggetto che può essere usato in remoto è un'istanza di una classe che soddisfa una o più delle condizioni seguenti:  
  
-   Deriva la <xref:System.MarshalByRefObject> classe.  
  
-   Implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
-   È il <xref:System.SerializableAttribute> attributo applicato.  
  
> [!NOTE]
>  Per altre informazioni relative alla creazione di oggetti [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] che possono essere usati in remoto, vedere [Impostazione degli oggetti per essere utilizzabili in remoto](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a).  
  
 I tipi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] non possono essere usati in remoto. Per risolvere il problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estende il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per consentire la visualizzazione nelle applicazioni host dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] creata dai componenti aggiuntivi. Questo supporto viene fornito da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] da due tipi: il <xref:System.AddIn.Contract.INativeHandleContract> interfaccia e due metodi statici implementati dal <xref:System.AddIn.Pipeline.FrameworkElementAdapters> classe: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A livello generale, questi tipi e metodi vengono usati nel modo seguente:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è necessario che [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornito da componenti aggiuntivi sono classi che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>, ad esempio forme, controlli, i controlli utente, pannelli di layout e pagine.  
  
2.  Ogni volta che il contratto dichiara che verrà passata un'interfaccia utente tra il componente aggiuntivo e l'applicazione host, deve essere dichiarato come un <xref:System.AddIn.Contract.INativeHandleContract> (non un <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> è una rappresentazione utilizzabile in remoto del componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che possono essere passati attraverso i confini di isolamento.  
  
3.  Prima di essere passati dal dominio applicazione del componente aggiuntivo, un <xref:System.Windows.FrameworkElement> viene compresso come un <xref:System.AddIn.Contract.INativeHandleContract> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Una volta passato al dominio dell'applicazione host, il <xref:System.AddIn.Contract.INativeHandleContract> devono essere convertiti come un <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Come <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> vengono utilizzati dipendono dallo scenario specifico. Le sezioni seguenti forniscono informazioni dettagliate per ogni modello di programmazione.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>Componente aggiuntivo che restituisce un'interfaccia utente  
 Per fare in modo che un componente aggiuntivo restituisca un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a un'applicazione host, è necessario quanto segue:  
  
1.  L'applicazione host, il componente aggiuntivo e la pipeline devono essere creati, come descritto nella documentazione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md).  
  
2.  Il contratto deve implementare <xref:System.AddIn.Contract.IContract> e, per restituire un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], il contratto deve dichiarare un metodo con un valore restituito di tipo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che viene passato tra il componente aggiuntivo e l'host dell'applicazione deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.  
  
4.  Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] restituito dal componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> per un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento.  
  
5.  Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] restituito deve essere convertita da un <xref:System.AddIn.Contract.INativeHandleContract> per un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.  
  
6.  L'applicazione host Visualizza l'oggetto restituito <xref:System.Windows.FrameworkElement>.  
  
 Per un esempio che illustra come implementare un componente aggiuntivo che restituisce un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Creare un componente aggiuntivo che restituisce un'interfaccia utente](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>Componente aggiuntivo che costituisce un'interfaccia utente  
 Quando un componente aggiuntivo costituisce un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è necessario quanto segue:  
  
1.  L'applicazione host, il componente aggiuntivo e la pipeline devono essere creati, come descritto nella documentazione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md).  
  
2.  Deve implementare l'interfaccia del contratto per il componente aggiuntivo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Il componente aggiuntivo che viene passato all'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.  
  
4.  Il componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> per un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento.  
  
5.  Il componente aggiuntivo deve essere convertito da un <xref:System.AddIn.Contract.INativeHandleContract> per un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.  
  
6.  L'applicazione host Visualizza l'oggetto restituito <xref:System.Windows.FrameworkElement>.  
  
 Per un esempio che illustra come implementare un componente aggiuntivo che costituisce un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Creare un componente aggiuntivo che costituisce un'interfaccia utente](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Restituzione di più interfacce utente da un componente aggiuntivo  
 I componenti aggiuntivi spesso forniscono più [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] per la visualizzazione nelle applicazioni host. Considerare, ad esempio un componente aggiuntivo che costituisce un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che fornisce anche informazioni sullo stato all'applicazione host, sempre sotto forma di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Un componente aggiuntivo di questo tipo può essere implementato usando una combinazione di tecniche dei modelli [Componente aggiuntivo che restituisce un'interfaccia utente](#ReturnUIFromAddInContract) e [Componente aggiuntivo che costituisce un'interfaccia utente](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Componenti aggiuntivi e applicazioni browser XAML  
 Negli esempi illustrati fino a questo momento l'applicazione host era un'applicazione autonoma installata. Anche le [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] possono però ospitare componenti aggiuntivi, sebbene con i requisiti di compilazione e implementazione aggiuntivi seguenti:  
  
-   Il manifesto dell'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve essere appositamente configurato per scaricare la pipeline (cartelle e assembly) e l'assembly del componente aggiuntivo nella cache dell'applicazione [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] sul computer client, nella stessa cartella dell'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Il codice [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che consente di individuare e caricare i componenti aggiuntivi deve usare la cache dell'applicazione [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] per [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] come percorso della pipeline e del componente aggiuntivo.  
  
-   L'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve caricare il componente aggiuntivo in un contesto di sicurezza speciale se tale componente fa riferimento a file separati che si trovano nel sito di origine. Se sono ospitati da applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], i componenti aggiuntivi possono fare riferimento unicamente ai file separati che si trovano nel sito di origine dell'applicazione host.  
  
 Queste attività sono descritte in dettaglio nelle sottosezioni seguenti.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configurazione della pipeline e del componente aggiuntivo per la distribuzione ClickOnce  
 Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] vengono scaricate in una cartella sicura nella cache di distribuzione [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] ed eseguite da questa posizione. Affinché un'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ospiti un componente aggiuntivo, anche l'assembly della pipeline e del componente aggiuntivo deve essere scaricato nella cartella sicura. A tale scopo, è necessario configurare il manifesto dell'applicazione per includere l'assembly della pipeline e del componente aggiuntivo per il download. Questo risulta più semplice in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], anche se l'assembly della pipeline e del componente aggiuntivo deve trovarsi nella cartella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host affinché [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] rilevi gli assembly della pipeline.  
  
 Di conseguenza, il primo passaggio consiste nel compilare l'assembly della pipeline e del componente aggiuntivo nella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], impostando l'output di compilazione di ogni progetto di assembly della pipeline e di assembly del componente aggiuntivo. La tabella seguente mostra i percorsi dell'output di compilazione per i progetti di assembly della pipeline e il progetto di assembly del componente aggiuntivo che si trovano nella stessa soluzione e cartella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host.  
  
 Tabella 1: Percorsi dell'output di compilazione per gli assembly della pipeline ospitati da un'applicazione XBAP  
  
|Progetto di assembly della pipeline|Percorso dell'output di compilazione|  
|-------------------------------|-----------------------|  
|Contratto|`..\HostXBAP\Contracts\`|  
|Vista del componente aggiuntivo|`..\HostXBAP\AddInViews\`|  
|Adattatore sul lato del componente aggiuntivo|`..\HostXBAP\AddInSideAdapters\`|  
|Adattatore sul lato host|`..\HostXBAP\HostSideAdapters\`|  
|Componente aggiuntivo|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 Il passaggio successivo consiste nello specificare gli assembly della pipeline e l'assembly del componente aggiuntivo come file di contenuto [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] eseguendo questa procedura:  
  
1.  Includere l'assembly della pipeline e del componente aggiuntivo nel progetto facendo clic con il pulsante destro del mouse su ogni cartella della pipeline in Esplora soluzioni e scegliendo **Includi nel progetto**.  
  
2.  Impostare il valore per **Azione di compilazione** di ogni assembly della pipeline e del componente aggiuntivo su **Contenuto** nella finestra **Proprietà**.  
  
 Il passaggio finale consiste nel configurare il manifesto dell'applicazione per includere i file di assembly della pipeline e il file di assembly del componente aggiuntivo per il download. I file devono trovarsi all'interno di cartelle nella radice della cartella contenuta nella cache [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] occupata dall'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. La configurazione può essere effettuata in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] eseguendo questa procedura:  
  
1.  Fare clic con il pulsante destro del mouse sul progetto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], scegliere **Proprietà**, fare clic su **Pubblica** e quindi fare clic sul pulsante **File applicazione**.  
  
2.  Nella finestra di dialogo **File applicazione** impostare il valore di **Stato pubblicazione** di ogni DLL della pipeline e del componente aggiuntivo su **Includi (Auto)** e impostare il valore di **Gruppo di download** per ogni DLL della pipeline e del componente aggiuntivo su **(Obbligatorio)**.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Uso della pipeline e del componente aggiuntivo dalla base dell'applicazione  
 Quando la pipeline e il componente aggiuntivo sono configurati per la distribuzione [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], vengono scaricati nella stessa cartella della cache [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] in cui si trova l'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Per usare la pipeline e il componente aggiuntivo dall'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], il codice [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve ottenerli dalla base dell'applicazione. I diversi tipi e membri del modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per l'uso di pipeline e componenti aggiuntivi forniscono uno speciale supporto per questo scenario. In primo luogo, il percorso è identificato dal <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> valore di enumerazione. Questo valore viene usato con gli overload dei membri pertinenti del componente aggiuntivo per l'uso delle pipeline, che includono quanto segue:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Accesso al sito di origine dell'host  
 Per assicurare che un componente aggiuntivo possa fare riferimento ai file del sito di origine, tale componente deve essere caricato con lo stesso isolamento di sicurezza dell'applicazione host. Questo livello di sicurezza viene identificato con il <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> valore di enumerazione e passato al <xref:System.AddIn.Hosting.AddInToken.Activate%2A> metodo quando un componente aggiuntivo viene attivato.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Architettura dei componenti aggiuntivi WPF  
 Livello più alto, come abbiamo visto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aggiuntivi per implementare [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] (che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>) utilizzando <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Il risultato è che l'applicazione host viene restituita un <xref:System.Windows.FrameworkElement> che viene visualizzato da [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nell'applicazione host.  
  
 Nel caso di scenari semplici di componenti aggiuntivi dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], gli sviluppatori non necessitano di maggiori dettagli. Nel caso di scenari più complessi, in particolare quando si tenta di usare servizi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aggiuntivi come layout, risorse e data binding, è necessaria una conoscenza più dettagliata del modo in cui [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estende il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con il supporto dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], al fine di comprenderne i vantaggi e le limitazioni.  
  
 Fondamentalmente, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non passa un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da un componente aggiuntivo a un'applicazione host. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] passa invece l'handle di finestra Win32 per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] usando l'interoperabilità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Di conseguenza, quando un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene passata da un componente aggiuntivo a un'applicazione host, si verifica quanto segue:  
  
-   Sul lato del componente aggiuntivo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] acquisisce un handle di finestra per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che verrà visualizzata dall'applicazione host. L'handle di finestra viene incapsulata da un interno [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classe che deriva da <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e sottoposta a marshalling dal dominio dell'applicazione del componente aggiuntivo al dominio dell'applicazione host.  
  
-   Sul lato dell'applicazione host, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] riassembla il <xref:System.Windows.Interop.HwndSource> come comando interno [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classe che deriva da <xref:System.Windows.Interop.HwndHost> e utilizza <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> all'applicazione host.  
  
 <xref:System.Windows.Interop.HwndHost> lo scopo di visualizzare [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], identificato da handle di finestra, dalla [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]. Per altre informazioni, vedere [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 In sintesi, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> esiste per l'handle di finestra per consentire un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] deve essere passato da un componente aggiuntivo per un'applicazione host, in cui viene incapsulato da un <xref:System.Windows.Interop.HwndHost> e visualizzato l'host dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
>  Poiché l'applicazione host ottiene un <xref:System.Windows.Interop.HwndHost>, l'applicazione host non è possibile convertire l'oggetto restituito da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> per il tipo viene implementato per il componente aggiuntivo (ad esempio, un <xref:System.Windows.Controls.UserControl>).  
  
 Per sua natura, <xref:System.Windows.Interop.HwndHost> presenta alcune limitazioni che influiscono sull'utilizzano da parte delle applicazioni host. Tuttavia, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estende <xref:System.Windows.Interop.HwndHost> con diverse funzionalità per gli scenari di componente aggiuntivo. Di seguito sono illustrati i vantaggi e le limitazioni.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Vantaggi dei componenti aggiuntivi WPF  
 Poiché [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aggiuntivo [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] visualizzate dalle applicazioni host tramite una classe interna che deriva da <xref:System.Windows.Interop.HwndHost>, tali [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] sono vincolate dalle funzionalità di <xref:System.Windows.Interop.HwndHost> rispetto a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] servizi quali layout, rendering, associazione dati, stili, modelli e risorse. Tuttavia, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aumenta interni <xref:System.Windows.Interop.HwndHost> sottoclasse con funzionalità aggiuntive che includono quanto segue:  
  
-   Passaggio tra l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un'applicazione host e l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo tramite tasto TAB. Si noti che la "componente aggiuntivo è un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" modello di programmazione richiede che l'adattatore lato del componente aggiuntivo eseguire l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> per abilitare la tabulazione, se il componente aggiuntivo è completamente attendibile o parzialmente attendibile.  
  
-   Rispetto dei requisiti di accessibilità per le [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] dei componenti aggiuntivi visualizzate dalle [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] delle applicazioni host.  
  
-   Abilitazione dell'esecuzione sicura delle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in diversi scenari di dominio dell'applicazione.  
  
-   Protezione contro l'accesso illegale agli handle di finestra dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dei componenti aggiuntivi in caso di esecuzione dei componenti aggiuntivi con isolamento di sicurezza, ovvero una sandbox di sicurezza con attendibilità parziale. La chiamata <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantisce la sicurezza:  
  
    -   Per la "componente aggiuntivo che restituisce un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" modello di programmazione, l'unico modo per passare l'handle di finestra per un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] attraverso l'isolamento Limite consiste nel chiamare <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Per la "componente aggiuntivo è un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" programmazione del modello, si esegue l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> sul lato componente-scheda e chiamare il metodo <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (come illustrato negli esempi precedenti) è obbligatorio, nonché la chiamata dell'adapter sul lato componente- `QueryContract` implementazione dalla scheda sul lato host.  
  
-   Protezione dell'esecuzione per più domini dell'applicazione. A causa delle limitazioni relative ai domini dell'applicazione, le eccezioni non gestite generate nei domini dell'applicazione del componente aggiuntivo provocano un arresto anomalo dell'intera applicazione, anche in presenza di un limite di isolamento. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e il modello di componente aggiuntivo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] offrono tuttavia un modo semplice per ovviare a questo problema e migliorare la stabilità dell'applicazione. A [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aggiuntivo che consente di visualizzare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] crea un <xref:System.Windows.Threading.Dispatcher> per il thread che il dominio applicazione viene eseguita, se l'applicazione host è un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dell'applicazione. È possibile rilevare le eccezioni tutti non gestite che si verificano nel dominio dell'applicazione mediante la gestione di <xref:System.Windows.Threading.Dispatcher.UnhandledException> evento del [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] del componente aggiuntivo <xref:System.Windows.Threading.Dispatcher>. È possibile ottenere il <xref:System.Windows.Threading.Dispatcher> dal <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> proprietà.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Limitazioni dei componenti aggiuntivi WPF  
 Oltre ai vantaggi che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aggiunge i comportamenti predefiniti forniti da <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>e gli handle di finestra, vi sono inoltre limiti per il componente aggiuntivo [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] che vengono visualizzate dalle applicazioni host:  
  
-   Le [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] dei componenti aggiuntivi visualizzate da un'applicazione host non rispettano il comportamento dell'area di visualizzazione dell'applicazione host.  
  
-   Il concetto di *spazio aereo* negli scenari di interoperabilità si applica anche ai componenti aggiuntivi (vedere [Cenni preliminari sulle aree di tecnologia](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)).  
  
-   I servizi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un'applicazione host, come l'ereditarietà delle risorse, il data binding e l'esecuzione di comandi, non sono automaticamente disponibili per le [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] del componente aggiuntivo. Per fornire questi servizi al componente aggiuntivo è necessario aggiornare la pipeline.  
  
-   L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo non può essere ruotata, ridimensionata, inclinata o modificata in altro modo da una trasformazione (vedere [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)).  
  
-   Contenuto del componente aggiuntivo [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] che viene eseguito il rendering mediante operazioni di disegno di <xref:System.Drawing> dello spazio dei nomi può includere la fusione alfa. Tuttavia, sia l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo che l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione host che lo contiene devono essere opache al 100%. In altre parole, la proprietà `Opacity` deve essere impostata su 1 in entrambi i casi.  
  
-   Se il <xref:System.Windows.Window.AllowsTransparency%2A> proprietà di una finestra nell'applicazione host che contiene un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è impostato su `true`, il componente aggiuntivo non è visibile. Questo accade anche se l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del componente aggiuntivo è opaca al 100%, ovvero se la proprietà `Opacity` ha un valore pari a 1.  
  
-   L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo deve essere visualizzata sopra ad altri elementi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nella stessa finestra di primo livello.  
  
-   Nessuna parte di un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] può essere riprodotta utilizzando un <xref:System.Windows.Media.VisualBrush>. Il componente aggiuntivo può invece creare uno snapshot dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] generata per creare una bitmap che può essere passata all'applicazione host usando i metodi definiti dal contratto.  
  
-   Non è possibile riprodurre file multimediali da un <xref:System.Windows.Controls.MediaElement> in un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Gli eventi del mouse generati per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del componente aggiuntivo non vengono ricevuti né generati dall'applicazione host e la proprietà `IsMouseOver` dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione host è impostata su `false`.  
  
-   Quando lo stato attivo passa da un controllo a un altro nell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo, gli eventi `GotFocus` e `LostFocus` non vengono ricevuti né generati dall'applicazione host.  
  
-   La parte di un'applicazione host contenente l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un componente aggiuntivo appare bianca quando viene stampata.  
  
-   Tutti i dispatcher (vedere <xref:System.Windows.Threading.Dispatcher>) creato dal componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] devono essere spente manualmente prima che il componente aggiuntivo proprietario venga scaricato se l'applicazione host continua l'esecuzione. Il contratto può implementare metodi che consentono all'applicazione host di segnalare il componente aggiuntivo prima che questo venga scaricato, permettendo così all'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del componente aggiuntivo di arrestare i dispatcher.  
  
-   Se un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è un <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, non è possibile scaricare il componente aggiuntivo.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Ottimizzazione delle prestazioni  
 Per impostazione predefinita, quando si usano più domini dell'applicazione, tutti gli assembly [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] richiesti da ogni applicazione vengono caricati nel dominio. Di conseguenza, il tempo necessario per creare nuovi domini dell'applicazione e avviare le applicazioni al loro interno potrebbe influire sulle prestazioni. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] consente tuttavia di ridurre i tempi di avvio indicando alle applicazioni di condividere gli assembly tra i vari domini dell'applicazione, se già caricati. Farlo tramite il <xref:System.LoaderOptimizationAttribute> attributo, che deve essere applicato al metodo del punto di ingresso (`Main`). In questo caso, è necessario usare soltanto il codice per implementare la definizione dell'applicazione (vedere [Cenni preliminari sulla gestione di applicazioni](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.LoaderOptimizationAttribute>  
 [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md)  
 [Domini dell'applicazione](../../../../docs/framework/app-domains/application-domains.md)  
 [Panoramica di servizi remoti .NET framework](http://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [Rendere utilizzabile in remoto gli oggetti](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/app-development/how-to-topics.md)
