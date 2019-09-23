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
ms.openlocfilehash: a146f15a1c2755f254e198d471a42ca9ec29b072
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182540"
---
# <a name="wpf-add-ins-overview"></a>Cenni preliminari sui componenti aggiuntivi di WPF

<a name="Introduction"></a>Il .NET Framework include un modello di componente aggiuntivo che gli sviluppatori possono utilizzare per creare applicazioni che supportano l'estensibilità dei componenti aggiuntivi. Questo modello consente di creare componenti aggiuntivi che si integrano con le funzionalità dell'applicazione estendendole. In alcuni scenari, le applicazioni devono anche visualizzare le interfacce utente fornite dai componenti aggiuntivi. In questo argomento viene illustrato come WPF amplia il modello di componente aggiuntivo .NET Framework per abilitare questi scenari, l'architettura sottostante, i vantaggi e le limitazioni.

<a name="Requirements"></a>

## <a name="prerequisites"></a>Prerequisiti

È necessaria una certa familiarità con il modello di componente aggiuntivo .NET Framework. Per altre informazioni, vedere [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).

<a name="AddInsOverview"></a>

## <a name="add-ins-overview"></a>Cenni preliminari sui componenti aggiuntivi

Per evitare le complessità legate alla ricompilazione e alla ridistribuzione di un'applicazione per incorporare nuove funzionalità, le applicazioni implementano meccanismi di estendibilità che consentono agli sviluppatori dell'applicazione e a quelli di terze parti di creare altre applicazioni che si integrano con esse. Il metodo più comune per supportare questo tipo di estendibilità consiste nell'usare i componenti aggiuntivi, noti anche come "plug-in". Di seguito sono riportati alcuni esempi di applicazioni reali che espongono l'estendibilità mediante componenti aggiuntivi:

- Componenti aggiuntivi di Internet Explorer.

- Plug-in di Windows Media Player.

- Componenti aggiuntivi di Visual Studio.

Il modello di componente aggiuntivo di Windows Media Player, ad esempio, consente agli sviluppatori di terze parti di implementare "plug-in" che estendono Windows Media Player in diversi modi, come tramite la creazione di decodificatori e codificatori per formati multimediali non supportati a livello nativo da Windows Media Player (ad esempio DVD, MP3), effetti audio e interfacce. Ogni modello di componente aggiuntivo è creato per esporre funzionalità univoche di un'applicazione, anche se ci sono diversi comportamenti ed entità comuni a tutti i modelli.

Le tre entità principali delle soluzioni tipiche di estendibilità mediante componenti aggiuntivi sono *contratti*, *componenti aggiuntivi* e *applicazioni host*. I contratti definiscono la modalità di integrazione dei componenti aggiuntivi con le applicazioni host in due modi:

- I componenti aggiuntivi si integrano con le funzionalità implementate dalle applicazioni host.

- Le applicazioni host espongono funzionalità con cui i componenti aggiuntivi si integrano.

Per poter usare i componenti aggiuntivi, le applicazioni host devono trovarli e caricarli in fase di esecuzione. Di conseguenza, le applicazioni che supportano i componenti aggiuntivi hanno le ulteriori responsabilità seguenti:

- **Individuazione**: Ricerca di componenti aggiuntivi che rispettano i contratti supportati dalle applicazioni host.

- **Attivazione**: Caricamento, esecuzione e determinazione della comunicazione con i componenti aggiuntivi.

- **Isolamento**: Utilizzo di domini applicazione o processi per stabilire limiti di isolamento che proteggono le applicazioni da potenziali problemi di sicurezza e di esecuzione con i componenti aggiuntivi.

- **Comunicazione**: Consentire ai componenti aggiuntivi e alle applicazioni host di comunicare tra loro attraverso i limiti di isolamento chiamando metodi e passando i dati.

- **Gestione della durata**: Caricamento e scaricamento di domini applicazione e processi in modo pulito e prevedibile (vedere [domini applicazione](../../app-domains/application-domains.md)).

- **Controllo delle versioni**: Verificare che le applicazioni e i componenti aggiuntivi host possano ancora comunicare quando vengono create nuove versioni di.

In definitiva, lo sviluppo di un modello di componente aggiuntivo affidabile è un'operazione tutt'altro che banale. Per questo motivo, il .NET Framework fornisce un'infrastruttura per la creazione di modelli di componenti aggiuntivi.

> [!NOTE]
> Per informazioni più dettagliate sui componenti aggiuntivi, vedere [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a>Cenni preliminari sul modello di componente aggiuntivo .NET Framework

Il .NET Framework modello di componente aggiuntivo, disponibile nello <xref:System.AddIn> spazio dei nomi, contiene un set di tipi progettati per semplificare lo sviluppo dell'estensibilità dei componenti aggiuntivi. L'unità fondamentale del modello di componente aggiuntivo .NET Framework è il *contratto*, che definisce il modo in cui un'applicazione host e un componente aggiuntivo comunicano tra loro. Un contratto viene esposto a un'applicazione host usando una *vista* del contratto specifica dell'applicazione host. Analogamente, una *vista* del contratto specifica del componente aggiuntivo viene esposta al componente aggiuntivo. Un *adattatore* consente a un'applicazione host e a un componente aggiuntivo di comunicare tra le rispettive viste del contratto. Contratti, viste e adattatori vengono detti segmenti e un set di segmenti correlati costituisce una *pipeline*. Le pipeline costituiscono la base su cui il modello di componente aggiuntivo .NET Framework supporta l'individuazione, l'attivazione, l'isolamento della sicurezza, l'isolamento dell'esecuzione (mediante domini applicazione e processi), la comunicazione, la gestione della durata e il controllo delle versioni.

Questo supporto consente agli sviluppatori di creare componenti aggiuntivi che si integrano con le funzionalità di un'applicazione host. Tuttavia, alcuni scenari richiedono che le applicazioni host visualizzino le interfacce utente fornite dai componenti aggiuntivi. Poiché ogni tecnologia di presentazione del .NET Framework dispone di un proprio modello per l'implementazione di interfacce utente, il modello di componente aggiuntivo .NET Framework non supporta alcuna tecnologia di presentazione particolare. WPF estende invece il modello di componente aggiuntivo .NET Framework con supporto dell'interfaccia utente per i componenti aggiuntivi.

<a name="WPFAddInModel"></a>

## <a name="wpf-add-ins"></a>Componenti aggiuntivi WPF

WPF, insieme al modello di componente aggiuntivo .NET Framework, consente di gestire un'ampia gamma di scenari che richiedono che le applicazioni host visualizzino le interfacce utente dai componenti aggiuntivi. In particolare, questi scenari vengono risolti da WPF con i due modelli di programmazione seguenti:

1. **Componente aggiuntivo che restituisce un'interfaccia utente**. Un componente aggiuntivo restituisce un'interfaccia utente all'applicazione host tramite una chiamata al metodo, come definito dal contratto. Questo scenario viene usato nei casi seguenti:

    - L'aspetto di un'interfaccia utente restituita da un componente aggiuntivo dipende da dati o condizioni che esistono solo in fase di esecuzione, ad esempio i report generati dinamicamente.

    - L'interfaccia utente per i servizi forniti da un componente aggiuntivo è diversa dall'interfaccia utente delle applicazioni host che possono usare il componente aggiuntivo.

    - Il componente aggiuntivo esegue principalmente un servizio per l'applicazione host e segnala lo stato all'applicazione host con un'interfaccia utente.

2. **Componente aggiuntivo che costituisce un'interfaccia utente**. Un componente aggiuntivo è un'interfaccia utente, in base a quanto definito dal contratto. Questo scenario viene usato nei casi seguenti:

    - Un componente aggiuntivo non fornisce alcun servizio eccetto la sua visualizzazione, come nel caso di un annuncio.

    - L'interfaccia utente per i servizi forniti da un componente aggiuntivo è comune a tutte le applicazioni host che possono utilizzare tale componente aggiuntivo, ad esempio un calcolatore o una selezione colori.

Questi scenari richiedono che gli oggetti dell'interfaccia utente possano essere passati tra i domini dell'applicazione host e del componente aggiuntivo. Poiché il .NET Framework modello di componente aggiuntivo si basa sulla comunicazione remota per la comunicazione tra domini dell'applicazione, gli oggetti passati tra di essi devono essere utilizzabili in remoto.

Un oggetto che può essere usato in remoto è un'istanza di una classe che soddisfa una o più delle condizioni seguenti:

- Deriva dalla <xref:System.MarshalByRefObject> classe.

- Implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- Ha l' <xref:System.SerializableAttribute> attributo applicato.

> [!NOTE]
> Per ulteriori informazioni sulla creazione di oggetti .NET Framework utilizzabili in remoto, vedere [rendere gli oggetti utilizzabili in remoto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100)).

I tipi di interfaccia utente WPF non sono utilizzabili in remoto. Per risolvere il problema, WPF estende il modello di componente aggiuntivo .NET Framework per consentire la visualizzazione dell'interfaccia utente WPF creata dai componenti aggiuntivi dalle applicazioni host. Questo supporto viene fornito da WPF da due tipi: l' <xref:System.AddIn.Contract.INativeHandleContract> interfaccia e due metodi statici implementati <xref:System.AddIn.Pipeline.FrameworkElementAdapters> dalla classe: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A livello generale, questi tipi e metodi vengono usati nel modo seguente:

1. WPF richiede che le interfacce utente fornite dai componenti aggiuntivi siano classi che derivano direttamente o indirettamente <xref:System.Windows.FrameworkElement>da, ad esempio forme, controlli, controlli utente, pannelli di layout e pagine.

2. Ogni volta che il contratto dichiara che un'interfaccia utente viene passata tra il componente aggiuntivo e l'applicazione host, deve essere dichiarata come <xref:System.AddIn.Contract.INativeHandleContract> (non a <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> è una rappresentazione utilizzabile in remoto dell'interfaccia utente del componente aggiuntivo che può essere passata attraverso i limiti di isolamento.

3. Prima di essere passati dal dominio dell'applicazione del componente aggiuntivo, un <xref:System.Windows.FrameworkElement> viene incluso <xref:System.AddIn.Contract.INativeHandleContract> nel pacchetto come chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.

4. Dopo essere stato passato al dominio applicazione dell'applicazione host, è <xref:System.AddIn.Contract.INativeHandleContract> necessario riassemblare <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>l'oggetto chiamando.

La <xref:System.AddIn.Contract.INativeHandleContract>modalità <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>di utilizzo <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> di, e dipende dallo scenario specifico. Le sezioni seguenti forniscono informazioni dettagliate per ogni modello di programmazione.

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a>Componente aggiuntivo che restituisce un'interfaccia utente

Per fare in modo che un componente aggiuntivo restituisca un'interfaccia utente a un'applicazione host, sono necessari gli elementi seguenti:

1. È necessario creare l'applicazione host, il componente aggiuntivo e la pipeline, come descritto nella documentazione .NET Framework [componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) .

2. Il contratto deve implementare <xref:System.AddIn.Contract.IContract> e, per restituire un'interfaccia utente, il contratto deve dichiarare un metodo con un valore restituito di <xref:System.AddIn.Contract.INativeHandleContract>tipo.

3. L'interfaccia utente passata tra il componente aggiuntivo e l'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.

4. L'interfaccia utente restituita dal componente aggiuntivo deve essere convertita da un <xref:System.Windows.FrameworkElement> oggetto a un oggetto <xref:System.AddIn.Contract.INativeHandleContract> prima di attraversare il limite di isolamento.

5. L'interfaccia utente restituita deve essere convertita da <xref:System.AddIn.Contract.INativeHandleContract> un oggetto <xref:System.Windows.FrameworkElement> a un oggetto dopo aver oltrepassato il limite di isolamento.

6. L'applicazione host Visualizza l'oggetto <xref:System.Windows.FrameworkElement>restituito.

Per un esempio in cui viene illustrato come implementare un componente aggiuntivo che restituisce un'interfaccia utente, vedere [creare un componente aggiuntivo che restituisce un'interfaccia utente](how-to-create-an-add-in-that-returns-a-ui.md).

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a>Componente aggiuntivo che costituisce un'interfaccia utente

Quando un componente aggiuntivo è un'interfaccia utente, sono necessari gli elementi seguenti:

1. È necessario creare l'applicazione host, il componente aggiuntivo e la pipeline, come descritto nella documentazione .NET Framework [componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) .

2. L'interfaccia del contratto per il componente aggiuntivo deve implementare <xref:System.AddIn.Contract.INativeHandleContract>.

3. Il componente aggiuntivo passato all'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.

4. Il componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> oggetto a un oggetto <xref:System.AddIn.Contract.INativeHandleContract> prima di attraversare il limite di isolamento.

5. Il componente aggiuntivo deve essere convertito da un oggetto <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> oggetto dopo aver oltrepassato il limite di isolamento.

6. L'applicazione host Visualizza l'oggetto <xref:System.Windows.FrameworkElement>restituito.

Per un esempio in cui viene illustrato come implementare un componente aggiuntivo che è un'interfaccia utente, vedere [creare un componente aggiuntivo che rappresenta un'interfaccia utente](how-to-create-an-add-in-that-is-a-ui.md).

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a>Restituzione di più interfacce utente da un componente aggiuntivo

I componenti aggiuntivi forniscono spesso più interfacce utente per la visualizzazione delle applicazioni host. Si consideri, ad esempio, un componente aggiuntivo che è un'interfaccia utente che fornisce anche informazioni sullo stato all'applicazione host, anche come interfaccia utente. Un componente aggiuntivo di questo tipo può essere implementato usando una combinazione di tecniche dei modelli [Componente aggiuntivo che restituisce un'interfaccia utente](#ReturnUIFromAddInContract) e [Componente aggiuntivo che costituisce un'interfaccia utente](#AddInIsAUI).

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a>Componenti aggiuntivi e applicazioni browser XAML

Negli esempi illustrati fino a questo momento l'applicazione host era un'applicazione autonoma installata. Anche le [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] possono però ospitare componenti aggiuntivi, sebbene con i requisiti di compilazione e implementazione aggiuntivi seguenti:

- Il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] manifesto dell'applicazione deve essere configurato appositamente per scaricare la pipeline (cartelle e assembly) e l'assembly del componente aggiuntivo nella cache dell'applicazione ClickOnce nel computer client, nella stessa cartella del [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

- Il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] codice per individuare e caricare i componenti aggiuntivi deve usare la cache dell'applicazione ClickOnce [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per come percorso della pipeline e del componente aggiuntivo.

- L'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve caricare il componente aggiuntivo in un contesto di sicurezza speciale se tale componente fa riferimento a file separati che si trovano nel sito di origine. Se sono ospitati da applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], i componenti aggiuntivi possono fare riferimento unicamente ai file separati che si trovano nel sito di origine dell'applicazione host.

Queste attività sono descritte in dettaglio nelle sottosezioni seguenti.

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configurazione della pipeline e del componente aggiuntivo per la distribuzione ClickOnce

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]vengono scaricati ed eseguiti da una cartella sicura nella cache di distribuzione ClickOnce. Affinché un'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ospiti un componente aggiuntivo, anche l'assembly della pipeline e del componente aggiuntivo deve essere scaricato nella cartella sicura. A tale scopo, è necessario configurare il manifesto dell'applicazione per includere l'assembly della pipeline e del componente aggiuntivo per il download. Questo risulta più semplice in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], anche se l'assembly della pipeline e del componente aggiuntivo deve trovarsi nella cartella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host affinché [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] rilevi gli assembly della pipeline.

Di conseguenza, il primo passaggio consiste nel compilare l'assembly della pipeline e del componente aggiuntivo nella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], impostando l'output di compilazione di ogni progetto di assembly della pipeline e di assembly del componente aggiuntivo. La tabella seguente mostra i percorsi dell'output di compilazione per i progetti di assembly della pipeline e il progetto di assembly del componente aggiuntivo che si trovano nella stessa soluzione e cartella radice del progetto di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host.

Tabella 1: Percorsi di output di compilazione per gli assembly della pipeline ospitati da un'applicazione XBAP

|Progetto di assembly della pipeline|Percorso dell'output di compilazione|
|-------------------------------|-----------------------|
|Contratto|`..\HostXBAP\Contracts\`|
|Vista del componente aggiuntivo|`..\HostXBAP\AddInViews\`|
|Adattatore sul lato del componente aggiuntivo|`..\HostXBAP\AddInSideAdapters\`|
|Adattatore sul lato host|`..\HostXBAP\HostSideAdapters\`|
|Componente aggiuntivo|`..\HostXBAP\AddIns\WPFAddIn1`|

Il passaggio successivo consiste nello specificare gli assembly della pipeline e l'assembly del componente aggiuntivo come file di contenuto [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] eseguendo questa procedura:

1. Includere l'assembly della pipeline e del componente aggiuntivo nel progetto facendo clic con il pulsante destro del mouse su ogni cartella della pipeline in Esplora soluzioni e scegliendo **Includi nel progetto**.

2. Impostare il valore per **Azione di compilazione** di ogni assembly della pipeline e del componente aggiuntivo su **Contenuto** nella finestra **Proprietà**.

Il passaggio finale consiste nel configurare il manifesto dell'applicazione per includere i file di assembly della pipeline e il file di assembly del componente aggiuntivo per il download. I file devono trovarsi in cartelle alla radice della cartella nella cache ClickOnce occupata dall' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] applicazione. La configurazione può essere effettuata in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] eseguendo questa procedura:

1. Fare clic con il pulsante destro del mouse sul progetto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], scegliere **Proprietà**, fare clic su **Pubblica** e quindi fare clic sul pulsante **File applicazione**.

2. Nella finestra di dialogo **File applicazione** impostare il valore di **Stato pubblicazione** di ogni DLL della pipeline e del componente aggiuntivo su **Includi (Auto)** e impostare il valore di **Gruppo di download** per ogni DLL della pipeline e del componente aggiuntivo su **(Obbligatorio)** .

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Uso della pipeline e del componente aggiuntivo dalla base dell'applicazione

Quando la pipeline e il componente aggiuntivo sono configurati per la distribuzione ClickOnce, vengono scaricati nella stessa cartella [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]della cache ClickOnce della. Per usare la pipeline e il componente aggiuntivo dall'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], il codice [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] deve ottenerli dalla base dell'applicazione. I vari tipi e membri del modello di componente aggiuntivo .NET Framework per l'utilizzo di pipeline e componenti aggiuntivi forniscono supporto speciale per questo scenario. In primo luogo, il percorso viene identificato dal <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> valore di enumerazione. Questo valore viene usato con gli overload dei membri pertinenti del componente aggiuntivo per l'uso delle pipeline, che includono quanto segue:

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a>Accesso al sito di origine dell'host

Per assicurare che un componente aggiuntivo possa fare riferimento ai file del sito di origine, tale componente deve essere caricato con lo stesso isolamento di sicurezza dell'applicazione host. Questo livello di sicurezza è identificato dal <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> valore di enumerazione e passato <xref:System.AddIn.Hosting.AddInToken.Activate%2A> al metodo quando viene attivato un componente aggiuntivo.

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a>Architettura dei componenti aggiuntivi WPF

Al livello più alto, come abbiamo visto, WPF consente ai .NET Framework componenti aggiuntivi di implementare le interfacce utente (che derivano direttamente o indirettamente <xref:System.Windows.FrameworkElement>da) <xref:System.AddIn.Contract.INativeHandleContract>utilizzando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> , <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>e. Il risultato è che all'applicazione host viene restituito un <xref:System.Windows.FrameworkElement> oggetto visualizzato dall'interfaccia utente nell'applicazione host.

Per gli scenari di componenti aggiuntivi dell'interfaccia utente semplici, questo è il modo più dettagliato necessario per gli sviluppatori. Per scenari più complessi, in particolare quelli che tentano di utilizzare servizi WPF aggiuntivi come layout, risorse e data binding, una conoscenza più approfondita del modo in cui WPF estende il modello di componente aggiuntivo .NET Framework con il supporto dell'interfaccia utente è necessario per comprenderne i vantaggi e limitazioni.

Fondamentalmente, WPF non passa un'interfaccia utente da un componente aggiuntivo a un'applicazione host. al contrario, WPF passa l'handle della finestra Win32 per l'interfaccia utente utilizzando l'interoperabilità WPF. Di conseguenza, quando un'interfaccia utente di un componente aggiuntivo viene passata a un'applicazione host, si verifica quanto segue:

- Sul lato componente aggiuntivo, WPF acquisisce un handle di finestra per l'interfaccia utente che verrà visualizzata dall'applicazione host. L'handle della finestra è incapsulato da una classe WPF interna che deriva <xref:System.Windows.Interop.HwndSource> da e <xref:System.AddIn.Contract.INativeHandleContract>implementa. Un'istanza di questa classe viene restituita <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> da e viene sottoposta a marshalling dal dominio applicazione del componente aggiuntivo al dominio applicazione dell'applicazione host.

- Sul lato dell'applicazione host, WPF riassembla <xref:System.Windows.Interop.HwndSource> come una classe WPF interna che deriva da <xref:System.Windows.Interop.HwndHost> e utilizza <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> da all'applicazione host.

<xref:System.Windows.Interop.HwndHost>esiste per visualizzare le interfacce utente, identificate dagli handle di finestra, dalle interfacce utente WPF. Per altre informazioni, vedere [Interoperatività di WPF e Win32](../advanced/wpf-and-win32-interoperation.md).

In sintesi, <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> esistono per consentire il passaggio dell'handle di finestra per un'interfaccia utente di WPF da un componente aggiuntivo a un'applicazione host, in cui è incapsulato da <xref:System.Windows.Interop.HwndHost> un oggetto e viene visualizzata l'interfaccia utente dell'applicazione host.

> [!NOTE]
> Poiché l'applicazione host ottiene un <xref:System.Windows.Interop.HwndHost>oggetto, l'applicazione host non è in grado di convertire l' <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> oggetto restituito da nel tipo di cui è implementata dal componente aggiuntivo (ad esempio, <xref:System.Windows.Controls.UserControl>a).

Per sua natura, <xref:System.Windows.Interop.HwndHost> presenta alcune limitazioni che influiscono sul modo in cui le applicazioni host possono utilizzarle. Tuttavia, WPF si <xref:System.Windows.Interop.HwndHost> estende con diverse funzionalità per gli scenari di componente aggiuntivo. Di seguito sono illustrati i vantaggi e le limitazioni.

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a>Vantaggi dei componenti aggiuntivi WPF

Poiché le interfacce utente dei componenti aggiuntivi WPF vengono visualizzate dalle applicazioni host mediante una classe interna che deriva da <xref:System.Windows.Interop.HwndHost>, tali interfacce utente sono limitate dalle funzionalità di <xref:System.Windows.Interop.HwndHost> rispetto ai servizi dell'interfaccia utente WPF, ad esempio il layout. rendering, data binding, stili, modelli e risorse. WPF, tuttavia, aumenta la sottoclasse interna <xref:System.Windows.Interop.HwndHost> con funzionalità aggiuntive che includono quanto segue:

- Tabulazione tra l'interfaccia utente di un'applicazione host e l'interfaccia utente di un componente aggiuntivo. Si noti che il modello di programmazione "componente aggiuntivo è un'interfaccia utente" richiede che l'adattatore sul lato del componente <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> aggiuntivo esegua l'override di per abilitare la tabulazione, indipendentemente dal fatto che il componente aggiuntivo sia completamente attendibile o parzialmente attendibile.

- Rispettare i requisiti di accessibilità per le interfacce utente dei componenti aggiuntivi visualizzate dalle interfacce utente dell'applicazione host.

- Consentire l'esecuzione sicura delle applicazioni WPF in più scenari di dominio applicazione.

- Impedire l'accesso non consentito ai punti di manipolazione della finestra dell'interfaccia utente del componente aggiuntivo quando i componenti aggiuntivi vengono eseguiti con isolamento di sicurezza, ovvero un sandbox di sicurezza con attendibilità parziale. La <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> chiamata a garantisce la sicurezza seguente:

  - Per il modello di programmazione "componente aggiuntivo che restituisce un'interfaccia utente", l'unico modo per passare l'handle della finestra per un'interfaccia utente del componente aggiuntivo oltre il limite <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>di isolamento consiste nel chiamare.

  - Per il modello di programmazione "componente aggiuntivo è un'interfaccia utente", è <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> necessario eseguire l'override dell'adattatore sul lato del componente <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> aggiuntivo e chiamare (come illustrato negli esempi precedenti), così come chiama l' `QueryContract` implementazione dell'adattatore sul lato del componente aggiuntivo dal adattatore sul lato host.

- Protezione dell'esecuzione per più domini dell'applicazione. A causa delle limitazioni relative ai domini dell'applicazione, le eccezioni non gestite generate nei domini dell'applicazione del componente aggiuntivo provocano un arresto anomalo dell'intera applicazione, anche in presenza di un limite di isolamento. WPF e il .NET Framework modello di componente aggiuntivo forniscono tuttavia un modo semplice per aggirare questo problema e migliorare la stabilità dell'applicazione. Un componente aggiuntivo WPF che visualizza un'interfaccia utente crea un <xref:System.Windows.Threading.Dispatcher> oggetto per il thread in cui viene eseguito il dominio dell'applicazione, se l'applicazione host è un'applicazione WPF. È possibile rilevare tutte le eccezioni non gestite che si verificano nel dominio applicazione gestendo <xref:System.Windows.Threading.Dispatcher.UnhandledException> l'evento del componente aggiuntivo <xref:System.Windows.Threading.Dispatcher>WPF. È possibile ottenere <xref:System.Windows.Threading.Dispatcher> <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> dalla proprietà.

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a>Limitazioni dei componenti aggiuntivi WPF

Oltre ai vantaggi che WPF aggiunge ai comportamenti predefiniti forniti dagli handle di <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost>finestra, e, esistono anche alcune limitazioni per le interfacce utente dei componenti aggiuntivi visualizzate dalle applicazioni host:

- Le interfacce utente del componente aggiuntivo visualizzate da un'applicazione host non rispettano il comportamento di ritaglio dell'applicazione host.

- Il concetto di *spazio aereo* negli scenari di interoperabilità si applica anche ai componenti aggiuntivi (vedere [Cenni preliminari sulle aree di tecnologia](../advanced/technology-regions-overview.md)).

- I servizi dell'interfaccia utente di un'applicazione host, ad esempio ereditarietà delle risorse, data binding e comandi, non sono automaticamente disponibili per le interfacce utente dei componenti aggiuntivi. Per fornire questi servizi al componente aggiuntivo è necessario aggiornare la pipeline.

- Un'interfaccia utente del componente aggiuntivo non può essere ruotata, ridimensionata, inclinata o modificata in altro modo da una trasformazione. vedere [Cenni preliminari sulle](../graphics-multimedia/transforms-overview.md)trasformazioni.

- Il contenuto all'interno delle interfacce utente del componente aggiuntivo di cui è stato eseguito <xref:System.Drawing> il rendering mediante operazioni di disegno dallo spazio dei nomi può includere la fusione alfa. Tuttavia, l'interfaccia utente di un componente aggiuntivo e l'interfaccia utente dell'applicazione host che lo contiene devono essere di 100% opaco; in altre parole, la `Opacity` proprietà deve essere impostata su 1.

- Se la <xref:System.Windows.Window.AllowsTransparency%2A> proprietà di una finestra nell'applicazione host che contiene un'interfaccia utente del componente aggiuntivo è impostata su `true`, il componente aggiuntivo è invisibile. Questo vale anche se l'interfaccia utente del componente aggiuntivo è opaca al 100%, ovvero se `Opacity` la proprietà ha un valore pari a 1.

- Un'interfaccia utente del componente aggiuntivo deve essere visualizzata sopra altri elementi WPF nella stessa finestra di primo livello.

- Non è possibile eseguire il rendering di alcuna parte dell'interfaccia utente di un <xref:System.Windows.Media.VisualBrush>componente aggiuntivo utilizzando un oggetto. Il componente aggiuntivo può invece creare uno snapshot dell'interfaccia utente generata per creare una bitmap che può essere passata all'applicazione host usando i metodi definiti dal contratto.

- I file multimediali non possono essere riprodotti da un <xref:System.Windows.Controls.MediaElement> in un'interfaccia utente del componente aggiuntivo.

- Gli eventi del mouse generati per l'interfaccia utente del componente aggiuntivo non vengono ricevuti né generati dall'applicazione host e `IsMouseOver` la proprietà per l'interfaccia utente dell'applicazione host `false`ha il valore.

- Quando lo stato attivo viene spostato tra i controlli in un'interfaccia utente di `GotFocus` un `LostFocus` componente aggiuntivo, gli eventi e non vengono ricevuti né generati dall'applicazione host.

- La parte di un'applicazione host che contiene un'interfaccia utente del componente aggiuntivo appare bianca quando viene stampata.

- Tutti i dispatcher (vedere <xref:System.Windows.Threading.Dispatcher>) creati dall'interfaccia utente del componente aggiuntivo devono essere arrestati manualmente prima che il componente aggiuntivo del proprietario venga scaricato se l'esecuzione dell'applicazione host continua. Il contratto può implementare metodi che consentono all'applicazione host di segnalare il componente aggiuntivo prima che il componente aggiuntivo venga scaricato, consentendo così all'interfaccia utente del componente aggiuntivo di arrestare i dispatcher.

- Se un'interfaccia utente del componente aggiuntivo è <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, non è possibile scaricare il componente aggiuntivo.

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a>Ottimizzazione delle prestazioni

Per impostazione predefinita, quando vengono usati più domini applicazione, i vari .NET Framework assembly richiesti da ogni applicazione vengono caricati nel dominio dell'applicazione. Di conseguenza, il tempo necessario per creare nuovi domini dell'applicazione e avviare le applicazioni al loro interno potrebbe influire sulle prestazioni. Tuttavia, il .NET Framework fornisce un modo per ridurre i tempi di avvio indicando alle applicazioni di condividere gli assembly tra domini applicazione se sono già stati caricati. A tale scopo, usare l' <xref:System.LoaderOptimizationAttribute> attributo, che deve essere applicato al metodo del punto di ingresso`Main`(). In questo caso, è necessario usare soltanto il codice per implementare la definizione dell'applicazione (vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)).

## <a name="see-also"></a>Vedere anche

- <xref:System.LoaderOptimizationAttribute>
- [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Domini dell'applicazione](../../app-domains/application-domains.md)
- [Panoramica di .NET Framework Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [Creazione di oggetti in remoto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [Procedure relative alle proprietà](how-to-topics.md)
