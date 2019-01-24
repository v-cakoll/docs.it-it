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
ms.openlocfilehash: 48981a942461570c0ef822dba9b18cb9a41f59f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662738"
---
# <a name="wpf-add-ins-overview"></a>Cenni preliminari sui componenti aggiuntivi di WPF
<a name="Introduction"></a> .NET Framework include un modello di componente aggiuntivo che gli sviluppatori possono usare per creare applicazioni che supportano l'estendibilità mediante componenti aggiuntivi. Questo modello consente di creare componenti aggiuntivi che si integrano con le funzionalità dell'applicazione estendendole. In alcuni scenari, le applicazioni devono anche visualizzare le interfacce utente fornite dai componenti aggiuntivi. In questo argomento viene illustrato come WPF integra il modello di componente aggiuntivo .NET Framework per consentire questi scenari, l'architettura sottostante, i vantaggi e le relative limitazioni.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 È necessario avere familiarità con il modello di componente aggiuntivo di .NET Framework. Per altre informazioni, vedere [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
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
  
-   **Individuazione**: Ricerca di componenti aggiuntivi conformi ai contratti supportati dalle applicazioni host.  
  
-   **Attivazione**: Il caricamento, esecuzione e stabilire la comunicazione con componenti aggiuntivi.  
  
-   **Isolamento**: Utilizzare i processi o domini applicazione per stabilire i limiti di isolamento che proteggono le applicazioni di sicurezza potenziali e i problemi di esecuzione con i componenti aggiuntivi.  
  
-   **Comunicazione**: Consentire ai componenti aggiuntivi e ospitare applicazioni di comunicare tra loro attraverso i limiti di isolamento chiamando i metodi e passando i dati.  
  
-   **Gestione della durata**: Caricamento e scaricamento di domini applicazione e i processi in modo netto e prevedibile (vedere [domini applicazione](../../../../docs/framework/app-domains/application-domains.md)).  
  
-   **Controllo delle versioni**: Verificare che le applicazioni host e componenti aggiuntivi possono comunque comunicare quando vengono create nuove versioni.  
  
 In definitiva, lo sviluppo di un modello di componente aggiuntivo affidabile è un'operazione tutt'altro che banale. Per questo motivo, .NET Framework fornisce un'infrastruttura per la creazione di modelli di componente aggiuntivo.  
  
> [!NOTE]
>  Per informazioni più dettagliate sui componenti aggiuntivi, vedere [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Cenni preliminari sul modello di componente aggiuntivo .NET Framework  
 Il modello .NET Framework aggiuntivo, trovato nel <xref:System.AddIn> dello spazio dei nomi, contiene un set di tipi che sono progettati per semplificare lo sviluppo dell'estendibilità di componente aggiuntivo. L'unità fondamentale del modello di componente aggiuntivo .NET Framework è la *contratto*, che definisce la modalità di un'applicazione host e un componente aggiuntivo di comunicare tra loro. Un contratto viene esposto a un'applicazione host usando una *vista* del contratto specifica dell'applicazione host. Analogamente, una *vista* del contratto specifica del componente aggiuntivo viene esposta al componente aggiuntivo. Un *adattatore* consente a un'applicazione host e a un componente aggiuntivo di comunicare tra le rispettive viste del contratto. Contratti, viste e adattatori vengono detti segmenti e un set di segmenti correlati costituisce una *pipeline*. Le pipeline sono la base su cui il modello di componente aggiuntivo di .NET Framework supporta l'individuazione, l'attivazione, isolamento di sicurezza, l'isolamento di esecuzione (tramite processi e domini dell'applicazione), comunicazione, la gestione della durata e il controllo delle versioni.  
  
 Questo supporto consente agli sviluppatori di creare componenti aggiuntivi che si integrano con le funzionalità di un'applicazione host. Tuttavia, alcuni scenari richiedono le applicazioni host visualizzino le interfacce utente fornite dai componenti aggiuntivi. Poiché ogni tecnologia di presentazione in .NET Framework ha un proprio modello per l'implementazione di interfacce utente, il modello di componente aggiuntivo di .NET Framework non supporta alcuna tecnologia di presentazione specifico. Al contrario, WPF offre il modello di componente aggiuntivo .NET Framework con il supporto dell'interfaccia utente per componenti aggiuntivi.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>Componenti aggiuntivi WPF  
 WPF, in combinazione con il modello .NET Framework aggiuntivo, consente di soddisfare un'ampia gamma di scenari che richiedono l'hosting di applicazioni per visualizzare le interfacce utente dai componenti aggiuntivi. In particolare, questi scenari vengono gestiti da WPF con i due modelli di programmazione seguenti:  
  
1.  **Componente aggiuntivo che restituisce un'interfaccia utente**. Un componente aggiuntivo restituisce un'interfaccia utente all'applicazione host tramite una chiamata al metodo, come definito dal contratto. Questo scenario viene usato nei casi seguenti:  
  
    -   L'aspetto di un'interfaccia utente che viene restituita da un componente aggiuntivo è dipenda da dati o condizioni che esiste solo in fase di esecuzione, ad esempio in modo dinamico i report generati.  
  
    -   L'interfaccia utente per i servizi forniti da un componente aggiuntivo è diverso dall'interfaccia utente delle applicazioni host che è possibile usare il componente aggiuntivo.  
  
    -   Il componente aggiuntivo principalmente esegue un servizio per l'applicazione host e segnala lo stato all'applicazione host con un'interfaccia utente.  
  
2.  **Componente aggiuntivo che costituisce un'interfaccia utente**. Un componente aggiuntivo è un'interfaccia utente, come definito dal contratto. Questo scenario viene usato nei casi seguenti:  
  
    -   Un componente aggiuntivo non fornisce alcun servizio eccetto la sua visualizzazione, come nel caso di un annuncio.  
  
    -   L'interfaccia utente per i servizi forniti da un componente aggiuntivo è comune a tutte le applicazioni host possono utilizzare tale componente aggiuntivo, ad esempio una calcolatrice o selezione colori.  
  
 Questi scenari richiedono che gli oggetti dell'interfaccia utente possono essere passati tra domini applicazione componente aggiuntivo e dell'applicazione host. Poiché .NET Framework modello di componente aggiuntivo si basa sulla comunicazione tra i domini applicazione remota, gli oggetti che vengono passati tra di essi devono essere utilizzabili in remoto.  
  
 Un oggetto che può essere usato in remoto è un'istanza di una classe che soddisfa una o più delle condizioni seguenti:  
  
-   Deriva dal <xref:System.MarshalByRefObject> classe.  
  
-   Implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Ha il <xref:System.SerializableAttribute> attributo viene applicato.  
  
> [!NOTE]
>  Per altre informazioni sulla creazione di oggetti di .NET Framework utilizzabili in remoto, vedere [rendere utilizzabile in remoto gli oggetti](https://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a).  
  
 I tipi WPF UI non sono utilizzabili in remoto. Per risolvere il problema, WPF offre il modello di componente aggiuntivo .NET Framework per abilitare creati dai componenti aggiuntivi di WPF UI a essere visualizzate dalle applicazioni host. Questo supporto è fornito da WPF da due tipi: i <xref:System.AddIn.Contract.INativeHandleContract> interfaccia e due metodi statici implementati dal <xref:System.AddIn.Pipeline.FrameworkElementAdapters> classe: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A livello generale, questi tipi e metodi vengono usati nel modo seguente:  
  
1.  WPF richiede che le interfacce utente fornite dai componenti aggiuntivi siano classi che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>, ad esempio forme, controlli, controlli utente, pannelli di layout e pagine.  
  
2.  Ogni volta che il contratto dichiara che un'interfaccia utente verrà passata tra il componente aggiuntivo e l'applicazione host, è necessario dichiararla come un <xref:System.AddIn.Contract.INativeHandleContract> (non un <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> è una rappresentazione utilizzabile in remoto il componente aggiuntivo dell'interfaccia utente di cui può essere passato attraverso limiti di isolamento.  
  
3.  Prima di essere passato dal dominio applicazione del componente aggiuntivo, un <xref:System.Windows.FrameworkElement> viene fornito come un <xref:System.AddIn.Contract.INativeHandleContract> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Dopo essere passati al dominio dell'applicazione host, il <xref:System.AddIn.Contract.INativeHandleContract> devono essere convertiti come un <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 La modalità <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> vengono usati dipende dallo scenario specifico. Le sezioni seguenti forniscono informazioni dettagliate per ogni modello di programmazione.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>Componente aggiuntivo che restituisce un'interfaccia utente  
 Per un componente aggiuntivo restituire un'interfaccia utente a un'applicazione host, è necessario quanto segue:  
  
1.  L'applicazione host, il componente aggiuntivo e pipeline devono essere creati, come descritto da .NET Framework [componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentazione.  
  
2.  Il contratto deve implementare <xref:System.AddIn.Contract.IContract> e, per restituire un'interfaccia utente, il contratto deve dichiarare un metodo con un valore restituito di tipo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  L'interfaccia utente che viene passato tra il componente aggiuntivo e l'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.  
  
4.  L'interfaccia utente restituito dal componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento.  
  
5.  L'interfaccia utente che viene restituito deve essere convertito da un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.  
  
6.  L'applicazione host Visualizza l'oggetto restituito <xref:System.Windows.FrameworkElement>.  
  
 Per un esempio che illustra come implementare un componente aggiuntivo che restituisce un'interfaccia utente, vedere [creare un componente aggiuntivo che restituisce un'interfaccia utente](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>Componente aggiuntivo che costituisce un'interfaccia utente  
 Quando un componente aggiuntivo è un'interfaccia utente, è necessario quanto segue:  
  
1.  L'applicazione host, il componente aggiuntivo e pipeline devono essere creati, come descritto da .NET Framework [componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentazione.  
  
2.  L'interfaccia del contratto per il componente aggiuntivo deve implementare <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Il componente aggiuntivo che viene passato all'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.  
  
4.  Il componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento.  
  
5.  Il componente aggiuntivo deve essere convertito da un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.  
  
6.  L'applicazione host Visualizza l'oggetto restituito <xref:System.Windows.FrameworkElement>.  
  
 Per un esempio che illustra come implementare un componente aggiuntivo che costituisce un'interfaccia utente, vedere [creare un componente aggiuntivo che costituisce un'interfaccia utente](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Restituzione di più interfacce utente da un componente aggiuntivo  
 Componenti aggiuntivi spesso forniscono più interfacce utente per le applicazioni host visualizzino. Si consideri ad esempio un componente aggiuntivo che costituisce un'interfaccia utente che fornisce anche informazioni sullo stato all'applicazione host, sempre come un'interfaccia utente. Un componente aggiuntivo di questo tipo può essere implementato usando una combinazione di tecniche dei modelli [Componente aggiuntivo che restituisce un'interfaccia utente](#ReturnUIFromAddInContract) e [Componente aggiuntivo che costituisce un'interfaccia utente](#AddInIsAUI).  
  
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
  
 Tabella 1: Percorsi di Output di compilazione per gli assembly della Pipeline ospitati da un'applicazione XBAP  
  
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
 Quando la pipeline e il componente aggiuntivo sono configurati per la distribuzione [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], vengono scaricati nella stessa cartella della cache [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] in cui si trova l'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Per usare la pipeline e il componente aggiuntivo dall'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], il codice [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve ottenerli dalla base dell'applicazione. I diversi tipi e membri del modello di componente aggiuntivo .NET Framework per l'uso di pipeline e componenti aggiuntivi forniscono uno speciale supporto per questo scenario. In primo luogo, il percorso è identificato dal <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> valore di enumerazione. Questo valore viene usato con gli overload dei membri pertinenti del componente aggiuntivo per l'uso delle pipeline, che includono quanto segue:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Accesso al sito di origine dell'host  
 Per assicurare che un componente aggiuntivo possa fare riferimento ai file del sito di origine, tale componente deve essere caricato con lo stesso isolamento di sicurezza dell'applicazione host. Questo livello di sicurezza è identificato dal <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> valore di enumerazione e passato al <xref:System.AddIn.Hosting.AddInToken.Activate%2A> metodo quando un componente aggiuntivo viene attivato.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Architettura dei componenti aggiuntivi WPF  
 Livello più alto, come abbiamo visto, WPF abilita componenti aggiuntivi a .NET Framework implementare le interfacce utente (che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>) usando <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Il risultato è che l'applicazione host viene restituito un <xref:System.Windows.FrameworkElement> che viene visualizzato dall'interfaccia utente nell'applicazione host.  
  
 Per semplici scenari dell'interfaccia utente aggiuntivo, si tratta di uno sviluppatore deve disporre di maggiori dettagli. Per scenari più complessi, in particolare quelli che tenta di usare servizi aggiuntivi di WPF come layout, risorse e l'associazione dati, è necessaria una conoscenza più approfondita di come WPF estende il modello di componente aggiuntivo .NET Framework con il supporto dell'interfaccia utente per comprenderne i vantaggi e le limitazioni.  
  
 Fondamentalmente, WPF non passare un'interfaccia utente da un componente aggiuntivo a un'applicazione host. WPF invece passa l'handle della finestra Win32 per l'interfaccia utente usando l'interoperabilità WPF. Di conseguenza, quando un'interfaccia utente da un componente aggiuntivo viene passata a un'applicazione host, si verifica quanto segue:  
  
-   Sul lato del componente aggiuntivo, WPF acquisisce un handle di finestra per l'interfaccia utente che verrà visualizzato dall'applicazione host. L'handle di finestra viene incapsulato da una classe WPF interna che deriva da <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e viene effettuato il marshalling dal dominio di applicazione del componente aggiuntivo al dominio dell'applicazione host.  
  
-   Sul lato dell'applicazione host WPF riassembla il <xref:System.Windows.Interop.HwndSource> come classe interna che deriva da WPF <xref:System.Windows.Interop.HwndHost> e consuma <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> all'applicazione host.  
  
 <xref:System.Windows.Interop.HwndHost> disponibile per visualizzare le interfacce utente, identificate dagli handle di finestra, dalle interfacce utente WPF. Per altre informazioni, vedere [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 In sintesi, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> esiste per consentire l'handle della finestra per una UI di WPF deve essere passato da un componente aggiuntivo a un'applicazione host, in cui viene incapsulato da un <xref:System.Windows.Interop.HwndHost> e visualizzato dell'interfaccia utente dell'applicazione host.  
  
> [!NOTE]
>  Poiché l'applicazione host ottiene un' <xref:System.Windows.Interop.HwndHost>, l'applicazione host non è possibile convertire l'oggetto restituito da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> al tipo viene implementato dal componente aggiuntivo (ad esempio, un <xref:System.Windows.Controls.UserControl>).  
  
 Per sua natura, <xref:System.Windows.Interop.HwndHost> presenta alcune limitazioni che influiscono sul modo in cui ospitare le applicazioni possono usarle. Tuttavia, WPF offre <xref:System.Windows.Interop.HwndHost> con diverse funzionalità per scenari di componente aggiuntivo. Di seguito sono illustrati i vantaggi e le limitazioni.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Vantaggi dei componenti aggiuntivi WPF  
 Poiché le interfacce utente del componente aggiuntivo di WPF sono visualizzate dalle applicazioni host tramite una classe interna che deriva da <xref:System.Windows.Interop.HwndHost>, le interfacce utente sono vincolate dalle funzionalità di <xref:System.Windows.Interop.HwndHost> rispetto a servizi WPF UI come layout, per il rendering, l'associazione dati, stili, modelli e le risorse. Tuttavia, WPF integra interna di quest ' <xref:System.Windows.Interop.HwndHost> sottoclasse con funzionalità aggiuntive che includono quanto segue:  
  
-   La tabulazione tra dell'interfaccia utente di un'applicazione host e un'interfaccia utente di un componente aggiuntivo. Si noti che il modello di programmazione "componente aggiuntivo è un'interfaccia utente" richiede che l'adattatore lato componente aggiuntivo eseguire l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> per abilitare la tabulazione, se il componente aggiuntivo sia completamente attendibile o parzialmente attendibile.  
  
-   Rispetta i requisiti di accessibilità per le interfacce utente di componenti aggiuntivi visualizzate dalle interfacce utente dell'applicazione host.  
  
-   Abilitazione delle applicazioni WPF per l'esecuzione in modo sicuro in diversi scenari di dominio dell'applicazione.  
  
-   Finestra che impedisce l'accesso non valido per il componente aggiuntivo dell'interfaccia utente gestisce quando eseguono componenti aggiuntivi con isolamento di sicurezza (vale a dire un sandbox di sicurezza con attendibilità parziale). La chiamata a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantisce questa sicurezza:  
  
    -   Per il modello di programmazione "componente aggiuntivo restituisce un'interfaccia utente", l'unico modo per passare l'handle della finestra per un componente aggiuntivo dell'interfaccia utente attraverso il limite di isolamento consiste nel chiamare <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Per il modello di programmazione "componente aggiuntivo è un'interfaccia utente", si esegue l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> sull'adattatore lato componente aggiuntivo e chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (come illustrato negli esempi precedenti) è obbligatorio, nonché la chiamata dell'adattatore lato componente aggiuntivo `QueryContract` dall'implementazione di adattatore lato host.  
  
-   Protezione dell'esecuzione per più domini dell'applicazione. A causa delle limitazioni relative ai domini dell'applicazione, le eccezioni non gestite generate nei domini dell'applicazione del componente aggiuntivo provocano un arresto anomalo dell'intera applicazione, anche in presenza di un limite di isolamento. Tuttavia, WPF e il modello di componente aggiuntivo di .NET Framework forniscono un modo semplice per risolvere questo problema e migliorare la stabilità dell'applicazione. Un componente aggiuntivo che visualizza un'interfaccia utente WPF crea un <xref:System.Windows.Threading.Dispatcher> per il thread che il dominio dell'applicazione viene eseguita, se l'applicazione host è un'applicazione WPF. È possibile rilevare le eccezioni tutti non gestite che si verificano nel dominio dell'applicazione tramite la gestione di <xref:System.Windows.Threading.Dispatcher.UnhandledException> eventi di WPF del componente aggiuntivo <xref:System.Windows.Threading.Dispatcher>. È possibile ottenere il <xref:System.Windows.Threading.Dispatcher> dal <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> proprietà.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Limitazioni dei componenti aggiuntivi WPF  
 Oltre ai vantaggi aggiunti ai comportamenti predefiniti forniti da WPF <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>e gli handle di finestra, esistono anche alcune limitazioni per le interfacce utente di componenti aggiuntivi visualizzate dalle applicazioni host:  
  
-   Interfacce utente del componente aggiuntivo visualizzate da un'applicazione host non rispettano la modalità di ritaglio dell'applicazione host.  
  
-   Il concetto di *spazio aereo* negli scenari di interoperabilità si applica anche ai componenti aggiuntivi (vedere [Cenni preliminari sulle aree di tecnologia](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)).  
  
-   Interfaccia utente dell'applicazione di un host dei servizi, ad esempio ereditarietà delle risorse, l'associazione dati e i comandi non sono automaticamente disponibili per il componente aggiuntivo interfacce utente. Per fornire questi servizi al componente aggiuntivo è necessario aggiornare la pipeline.  
  
-   Un componente aggiuntivo dell'interfaccia utente non può essere ruotata, ridimensionata, inclinata o è coinvolta in una trasformazione (vedere [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)).  
  
-   Contenuto all'interno di interfacce utente del componente aggiuntivo che viene eseguito il rendering mediante operazioni di disegno di <xref:System.Drawing> dello spazio dei nomi può includere la fusione alfa. Deve essere 100% di opacità; tuttavia, sia un componente aggiuntivo dell'interfaccia utente e l'applicazione host dell'interfaccia utente che lo contiene in altre parole, il `Opacity` proprietà sia deve essere impostata su 1.  
  
-   Se il <xref:System.Windows.Window.AllowsTransparency%2A> di una finestra nell'applicazione host che contiene un componente aggiuntivo dell'interfaccia utente è impostata su `true`, il componente aggiuntivo è invisibile. Questo vale anche se l'interfaccia utente del componente aggiuntivo è opaca al 100% (vale a dire il `Opacity` proprietà ha un valore pari a 1).  
  
-   Un'interfaccia utente del componente aggiuntivo deve essere visualizzata sopra altri elementi WPF nella stessa finestra di primo livello.  
  
-   Non eseguire il rendering la parte di UI di un componente aggiuntivo utilizzando un <xref:System.Windows.Media.VisualBrush>. Il componente aggiuntivo può invece eseguire uno snapshot dell'interfaccia utente generata per creare una bitmap che può essere passata all'applicazione host usando i metodi definiti dal contratto.  
  
-   Non è possibile riprodurre file multimediali da un <xref:System.Windows.Controls.MediaElement> in un'interfaccia utente del componente aggiuntivo.  
  
-   Gli eventi del mouse generati per l'interfaccia utente del componente aggiuntivo non vengono ricevuti né generati dall'applicazione host e il `IsMouseOver` un valore della proprietà per l'interfaccia utente dell'applicazione host è `false`.  
  
-   Quando lo stato attivo passa tra i controlli in un componente aggiuntivo dell'interfaccia utente, il `GotFocus` e `LostFocus` eventi non vengono ricevuti né generati dall'applicazione host.  
  
-   La parte di un'applicazione host che contiene un'interfaccia utente del componente aggiuntivo appare bianca quando viene stampata.  
  
-   Tutti i dispatcher (vedere <xref:System.Windows.Threading.Dispatcher>) creato dal componente aggiuntivo dell'interfaccia utente deve essere arrestati manualmente prima che il componente aggiuntivo proprietario venga scaricato se l'applicazione host continua l'esecuzione. Il contratto può implementare i metodi che consentono all'applicazione host di segnalare il componente aggiuntivo prima che il componente aggiuntivo viene scaricato, permettendo l'interfaccia utente di componente aggiuntivo arrestare i dispatcher.  
  
-   Se un componente aggiuntivo dell'interfaccia utente è un <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, non è possibile scaricare il componente aggiuntivo.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Ottimizzazione delle prestazioni  
 Per impostazione predefinita, quando vengono utilizzati più domini applicazione, gli assembly .NET Framework richiesti da ogni applicazione tutti vengono caricati nel dominio dell'applicazione. Di conseguenza, il tempo necessario per creare nuovi domini dell'applicazione e avviare le applicazioni al loro interno potrebbe influire sulle prestazioni. Tuttavia, .NET Framework fornisce un modo per ridurre i tempi di avvio indicando alle applicazioni di condividere gli assembly nei domini applicazione se sono già caricati. Eseguire questa operazione usando il <xref:System.LoaderOptimizationAttribute> attributo, che deve essere applicato al metodo del punto di ingresso (`Main`). In questo caso, è necessario usare soltanto il codice per implementare la definizione dell'applicazione (vedere [Cenni preliminari sulla gestione di applicazioni](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.LoaderOptimizationAttribute>
- [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Domini dell'applicazione](../../../../docs/framework/app-domains/application-domains.md)
- [Panoramica di .NET framework Remoting](https://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)
- [Oggetti remotizzabili](https://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/app-development/how-to-topics.md)
