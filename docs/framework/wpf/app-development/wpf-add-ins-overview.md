---
title: Cenni preliminari sui componenti aggiuntivi
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
ms.openlocfilehash: 93904e308932ea41c736ca849ce0efb200502a7e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738936"
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

- **Individuazione**: trovare i componenti aggiuntivi conformi ai contratti supportati dalle applicazioni host.

- **Attivazione**: caricare ed eseguire i componenti aggiuntivi e stabilire la comunicazione con essi.

- **Isolamento**: usare i processi o i domini dell'applicazione per stabilire i limiti di isolamento che proteggono le applicazioni da potenziali problemi di sicurezza e di esecuzione relativi ai componenti aggiuntivi.

- **Comunicazione**: consentire ai componenti aggiuntivi e alle applicazioni host di comunicare tra loro oltre i limiti di isolamento, mediante la chiamata a metodi e il passaggio di dati.

- **Gestione della durata**: caricare e scaricare processi e domini dell'applicazione in modo netto e prevedibile (vedere [Domini applicazione](../../app-domains/application-domains.md)).

- **Controllo delle versioni**: assicurare che le applicazioni host e i componenti aggiuntivi possano continuare a comunicare quando vengono create nuove versioni.

In definitiva, lo sviluppo di un modello di componente aggiuntivo affidabile è un'operazione tutt'altro che banale. Per questo motivo, il .NET Framework fornisce un'infrastruttura per la creazione di modelli di componenti aggiuntivi.

> [!NOTE]
> Per informazioni più dettagliate sui componenti aggiuntivi, vedere [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a>Cenni preliminari sul modello di componente aggiuntivo .NET Framework

Il .NET Framework modello di componente aggiuntivo, disponibile nello spazio dei nomi <xref:System.AddIn>, contiene un set di tipi progettati per semplificare lo sviluppo dell'estensibilità dei componenti aggiuntivi. L'unità fondamentale del modello di componente aggiuntivo .NET Framework è il *contratto*, che definisce il modo in cui un'applicazione host e un componente aggiuntivo comunicano tra loro. Un contratto viene esposto a un'applicazione host usando una *vista* del contratto specifica dell'applicazione host. Analogamente, una *vista* del contratto specifica del componente aggiuntivo viene esposta al componente aggiuntivo. Un *adattatore* consente a un'applicazione host e a un componente aggiuntivo di comunicare tra le rispettive viste del contratto. Contratti, viste e adattatori vengono detti segmenti e un set di segmenti correlati costituisce una *pipeline*. Le pipeline costituiscono la base su cui il modello di componente aggiuntivo .NET Framework supporta l'individuazione, l'attivazione, l'isolamento della sicurezza, l'isolamento dell'esecuzione (mediante domini applicazione e processi), la comunicazione, la gestione della durata e il controllo delle versioni.

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

- Deriva dalla classe <xref:System.MarshalByRefObject>.

- Implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- Viene applicato l'attributo <xref:System.SerializableAttribute>.

> [!NOTE]
> Per ulteriori informazioni sulla creazione di oggetti .NET Framework utilizzabili in remoto, vedere [rendere gli oggetti utilizzabili in remoto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100)).

I tipi di interfaccia utente WPF non sono utilizzabili in remoto. Per risolvere il problema, WPF estende il modello di componente aggiuntivo .NET Framework per consentire la visualizzazione dell'interfaccia utente WPF creata dai componenti aggiuntivi dalle applicazioni host. Questo supporto viene fornito da WPF da due tipi: l'interfaccia <xref:System.AddIn.Contract.INativeHandleContract> e due metodi statici implementati dalla classe <xref:System.AddIn.Pipeline.FrameworkElementAdapters>: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A livello generale, questi tipi e metodi vengono usati nel modo seguente:

1. WPF richiede che le interfacce utente fornite dai componenti aggiuntivi siano classi che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>, ad esempio forme, controlli, controlli utente, pannelli di layout e pagine.

2. Ogni volta che il contratto dichiara che un'interfaccia utente viene passata tra il componente aggiuntivo e l'applicazione host, deve essere dichiarata come <xref:System.AddIn.Contract.INativeHandleContract> (non come <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> è una rappresentazione utilizzabile in remoto dell'interfaccia utente del componente aggiuntivo che può essere passata attraverso i limiti di isolamento.

3. Prima di essere passati dal dominio applicazione del componente aggiuntivo, un <xref:System.Windows.FrameworkElement> viene incluso nel pacchetto come <xref:System.AddIn.Contract.INativeHandleContract> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.

4. Dopo essere stato passato al dominio applicazione dell'applicazione host, è necessario riassemblare il <xref:System.AddIn.Contract.INativeHandleContract> come <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.

La modalità di utilizzo di <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> dipende dallo scenario specifico. Le sezioni seguenti forniscono informazioni dettagliate per ogni modello di programmazione.

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a>Componente aggiuntivo che restituisce un'interfaccia utente

Per fare in modo che un componente aggiuntivo restituisca un'interfaccia utente a un'applicazione host, sono necessari gli elementi seguenti:

1. È necessario creare l'applicazione host, il componente aggiuntivo e la pipeline, come descritto nella documentazione .NET Framework [componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) .

2. Il contratto deve implementare <xref:System.AddIn.Contract.IContract> e, per restituire un'interfaccia utente, il contratto deve dichiarare un metodo con un valore restituito di tipo <xref:System.AddIn.Contract.INativeHandleContract>.

3. L'interfaccia utente passata tra il componente aggiuntivo e l'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.

4. L'interfaccia utente restituita dal componente aggiuntivo deve essere convertita da un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> prima di attraversare il limite di isolamento.

5. L'interfaccia utente restituita deve essere convertita da un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.

6. L'applicazione host Visualizza la <xref:System.Windows.FrameworkElement>restituita.

Per un esempio in cui viene illustrato come implementare un componente aggiuntivo che restituisce un'interfaccia utente, vedere [creare un componente aggiuntivo che restituisce un'interfaccia utente](how-to-create-an-add-in-that-returns-a-ui.md).

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a>Componente aggiuntivo che costituisce un'interfaccia utente

Quando un componente aggiuntivo è un'interfaccia utente, sono necessari gli elementi seguenti:

1. È necessario creare l'applicazione host, il componente aggiuntivo e la pipeline, come descritto nella documentazione .NET Framework [componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) .

2. L'interfaccia del contratto per il componente aggiuntivo deve implementare <xref:System.AddIn.Contract.INativeHandleContract>.

3. Il componente aggiuntivo passato all'applicazione host deve derivare direttamente o indirettamente da <xref:System.Windows.FrameworkElement>.

4. Il componente aggiuntivo deve essere convertito da un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> prima di superare il limite di isolamento.

5. Il componente aggiuntivo deve essere convertito da un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento.

6. L'applicazione host Visualizza la <xref:System.Windows.FrameworkElement>restituita.

Per un esempio in cui viene illustrato come implementare un componente aggiuntivo che è un'interfaccia utente, vedere [creare un componente aggiuntivo che rappresenta un'interfaccia utente](how-to-create-an-add-in-that-is-a-ui.md).

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a>Restituzione di più interfacce utente da un componente aggiuntivo

I componenti aggiuntivi forniscono spesso più interfacce utente per la visualizzazione delle applicazioni host. Si consideri, ad esempio, un componente aggiuntivo che è un'interfaccia utente che fornisce anche informazioni sullo stato all'applicazione host, anche come interfaccia utente. Un componente aggiuntivo di questo tipo può essere implementato usando una combinazione di tecniche dei modelli [Componente aggiuntivo che restituisce un'interfaccia utente](#ReturnUIFromAddInContract) e [Componente aggiuntivo che costituisce un'interfaccia utente](#AddInIsAUI).

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a>Componenti aggiuntivi e applicazioni browser XAML

Negli esempi illustrati fino a questo momento l'applicazione host era un'applicazione autonoma installata. Tuttavia, le applicazioni browser XAML (XBAPs) possono anche ospitare i componenti aggiuntivi, sebbene con i seguenti requisiti di compilazione e implementazione aggiuntivi:

- Il manifesto dell'applicazione XBAP deve essere configurato appositamente per scaricare la pipeline (cartelle e assembly) e l'assembly del componente aggiuntivo nella cache dell'applicazione ClickOnce nel computer client, nella stessa cartella dell'applicazione XBAP.

- Il codice XBAP per individuare e caricare i componenti aggiuntivi deve usare la cache dell'applicazione ClickOnce per l'applicazione XBAP come percorso della pipeline e del componente aggiuntivo.

- L'applicazione XBAP deve caricare il componente aggiuntivo in un contesto di sicurezza speciale se il componente aggiuntivo fa riferimento a file separati che si trovano nel sito di origine. Quando sono ospitate da XBAP, i componenti aggiuntivi possono fare riferimento solo a file separati che si trovano nel sito di origine dell'applicazione host.

Queste attività sono descritte in dettaglio nelle sottosezioni seguenti.

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configurazione della pipeline e del componente aggiuntivo per la distribuzione ClickOnce

Le applicazioni XBAP vengono scaricate ed eseguite da una cartella sicura nella cache di distribuzione ClickOnce. Affinché un'applicazione XBAP possa ospitare un componente aggiuntivo, è necessario scaricare anche l'assembly della pipeline e del componente aggiuntivo nella cartella safe. A tale scopo, è necessario configurare il manifesto dell'applicazione per includere l'assembly della pipeline e del componente aggiuntivo per il download. Questa operazione viene eseguita più facilmente in Visual Studio, anche se l'assembly della pipeline e del componente aggiuntivo deve trovarsi nella cartella radice del progetto XBAP dell'host affinché Visual Studio rilevi gli assembly della pipeline.

Di conseguenza, il primo passaggio consiste nel compilare l'assembly della pipeline e del componente aggiuntivo nella radice del progetto XBAP impostando l'output di compilazione di ogni progetto di assembly della pipeline e del componente aggiuntivo. La tabella seguente illustra i percorsi di output di compilazione per i progetti di assembly della pipeline e il progetto di assembly del componente aggiuntivo che si trovano nella stessa soluzione e nella stessa cartella radice del progetto XBAP host.

Tabella 1: Percorsi dell'output di compilazione per gli assembly della pipeline ospitati da un'applicazione XBAP

|Progetto di assembly della pipeline|Percorso dell'output di compilazione|
|-------------------------------|-----------------------|
|Contratto|`..\HostXBAP\Contracts\`|
|Vista del componente aggiuntivo|`..\HostXBAP\AddInViews\`|
|Adattatore sul lato del componente aggiuntivo|`..\HostXBAP\AddInSideAdapters\`|
|Adattatore sul lato host|`..\HostXBAP\HostSideAdapters\`|
|Componente aggiuntivo|`..\HostXBAP\AddIns\WPFAddIn1`|

Il passaggio successivo consiste nel specificare gli assembly della pipeline e l'assembly del componente aggiuntivo come file di contenuto XBAPs in Visual Studio effettuando le operazioni seguenti:

1. Includere l'assembly della pipeline e del componente aggiuntivo nel progetto facendo clic con il pulsante destro del mouse su ogni cartella della pipeline in Esplora soluzioni e scegliendo **Includi nel progetto**.

2. Impostare il valore per **Azione di compilazione** di ogni assembly della pipeline e del componente aggiuntivo su **Contenuto** nella finestra **Proprietà**.

Il passaggio finale consiste nel configurare il manifesto dell'applicazione per includere i file di assembly della pipeline e il file di assembly del componente aggiuntivo per il download. I file devono trovarsi in cartelle alla radice della cartella nella cache ClickOnce occupata dall'applicazione XBAP. La configurazione può essere eseguita in Visual Studio eseguendo le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul progetto XBAP, scegliere **Proprietà**, fare clic su **pubblica**, quindi fare clic sul pulsante **file applicazione** .

2. Nella finestra di dialogo **File applicazione** impostare il valore di **Stato pubblicazione** di ogni DLL della pipeline e del componente aggiuntivo su **Includi (Auto)** e impostare il valore di **Gruppo di download** per ogni DLL della pipeline e del componente aggiuntivo su **(Obbligatorio)** .

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Uso della pipeline e del componente aggiuntivo dalla base dell'applicazione

Quando la pipeline e il componente aggiuntivo sono configurati per la distribuzione ClickOnce, vengono scaricati nella stessa cartella della cache ClickOnce dell'applicazione XBAP. Per utilizzare la pipeline e il componente aggiuntivo da XBAP, è necessario che il codice XBAP li ottenga dalla base dell'applicazione. I vari tipi e membri del modello di componente aggiuntivo .NET Framework per l'utilizzo di pipeline e componenti aggiuntivi forniscono supporto speciale per questo scenario. In primo luogo, il percorso viene identificato dal valore di enumerazione <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase>. Questo valore viene usato con gli overload dei membri pertinenti del componente aggiuntivo per l'uso delle pipeline, che includono quanto segue:

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a>Accesso al sito di origine dell'host

Per assicurare che un componente aggiuntivo possa fare riferimento ai file del sito di origine, tale componente deve essere caricato con lo stesso isolamento di sicurezza dell'applicazione host. Questo livello di sicurezza è identificato dal valore di enumerazione <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> e passato al metodo <xref:System.AddIn.Hosting.AddInToken.Activate%2A> quando viene attivato un componente aggiuntivo.

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a>Architettura dei componenti aggiuntivi WPF

Al livello più alto, come abbiamo visto, WPF consente ai .NET Framework componenti aggiuntivi di implementare le interfacce utente (che derivano direttamente o indirettamente da <xref:System.Windows.FrameworkElement>) usando <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Il risultato è che l'applicazione host viene restituita una <xref:System.Windows.FrameworkElement> visualizzata dall'interfaccia utente nell'applicazione host.

Per gli scenari di componenti aggiuntivi dell'interfaccia utente semplici, questo è il modo più dettagliato necessario per gli sviluppatori. Per scenari più complessi, in particolare quelli che tentano di utilizzare servizi WPF aggiuntivi come layout, risorse e data binding, una conoscenza più approfondita del modo in cui WPF estende il modello di componente aggiuntivo .NET Framework con il supporto dell'interfaccia utente è necessario per comprenderne i vantaggi e limitazioni.

Fondamentalmente, WPF non passa un'interfaccia utente da un componente aggiuntivo a un'applicazione host. al contrario, WPF passa l'handle della finestra Win32 per l'interfaccia utente utilizzando l'interoperabilità WPF. Di conseguenza, quando un'interfaccia utente di un componente aggiuntivo viene passata a un'applicazione host, si verifica quanto segue:

- Sul lato componente aggiuntivo, WPF acquisisce un handle di finestra per l'interfaccia utente che verrà visualizzata dall'applicazione host. L'handle della finestra è incapsulato da una classe WPF interna che deriva da <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ed è sottoposta a marshalling dal dominio applicazione del componente aggiuntivo al dominio applicazione dell'applicazione host.

- Sul lato dell'applicazione host, WPF riassembla il <xref:System.Windows.Interop.HwndSource> come una classe WPF interna che deriva da <xref:System.Windows.Interop.HwndHost> e utilizza <xref:System.AddIn.Contract.INativeHandleContract>. Un'istanza di questa classe viene restituita da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> all'applicazione host.

<xref:System.Windows.Interop.HwndHost> esiste per visualizzare le interfacce utente, identificate dagli handle di finestra, dalle interfacce utente WPF. Per altre informazioni, vedere [Interoperatività di WPF e Win32](../advanced/wpf-and-win32-interoperation.md).

In sintesi sono disponibili <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>e <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> per consentire il passaggio dell'handle di finestra per un'interfaccia utente WPF da un componente aggiuntivo a un'applicazione host, in cui è incapsulato da un <xref:System.Windows.Interop.HwndHost> e viene visualizzata l'interfaccia utente dell'applicazione host.

> [!NOTE]
> Poiché l'applicazione host ottiene un <xref:System.Windows.Interop.HwndHost>, l'applicazione host non è in grado di convertire l'oggetto restituito da <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> al tipo implementato dal componente aggiuntivo (ad esempio, un <xref:System.Windows.Controls.UserControl>).

Per sua natura, <xref:System.Windows.Interop.HwndHost> presenta alcune limitazioni che influiscono sul modo in cui le applicazioni host possono utilizzarle. WPF, tuttavia, estende <xref:System.Windows.Interop.HwndHost> con diverse funzionalità per gli scenari di componente aggiuntivo. Di seguito sono illustrati i vantaggi e le limitazioni.

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a>Vantaggi dei componenti aggiuntivi WPF

Poiché le interfacce utente dei componenti aggiuntivi WPF vengono visualizzate dalle applicazioni host utilizzando una classe interna che deriva da <xref:System.Windows.Interop.HwndHost>, tali interfacce utente sono limitate dalle funzionalità di <xref:System.Windows.Interop.HwndHost> rispetto ai servizi dell'interfaccia utente WPF, ad esempio layout, rendering, data binding, stili, modelli e risorse. WPF, tuttavia, aumenta la sottoclasse <xref:System.Windows.Interop.HwndHost> interna con funzionalità aggiuntive che includono quanto segue:

- Tabulazione tra l'interfaccia utente di un'applicazione host e l'interfaccia utente di un componente aggiuntivo. Si noti che il modello di programmazione "componente aggiuntivo è un'interfaccia utente" richiede che l'adattatore sul lato del componente aggiuntivo esegua l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> per abilitare la tabulazione, indipendentemente dal fatto che il componente aggiuntivo sia completamente attendibile o parzialmente attendibile.

- Rispettare i requisiti di accessibilità per le interfacce utente dei componenti aggiuntivi visualizzate dalle interfacce utente dell'applicazione host.

- Consentire l'esecuzione sicura delle applicazioni WPF in più scenari di dominio applicazione.

- Impedire l'accesso non consentito ai punti di manipolazione della finestra dell'interfaccia utente del componente aggiuntivo quando i componenti aggiuntivi vengono eseguiti con isolamento di sicurezza, ovvero un sandbox di sicurezza con attendibilità parziale. La chiamata di <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantisce la sicurezza seguente:

  - Per il modello di programmazione "componente aggiuntivo che restituisce un'interfaccia utente", l'unico modo per passare l'handle della finestra per un'interfaccia utente del componente aggiuntivo oltre il limite di isolamento consiste nel chiamare <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.

  - Per il modello di programmazione "componente aggiuntivo è un'interfaccia utente", l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> sull'adapter lato componente aggiuntivo e la chiamata di <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (come illustrato negli esempi precedenti) è obbligatorio, così come è la chiamata all'implementazione di `QueryContract` dell'adattatore sul lato del componente aggiuntivo dall'adattatore sul lato host.

- Protezione dell'esecuzione per più domini dell'applicazione. A causa delle limitazioni relative ai domini dell'applicazione, le eccezioni non gestite generate nei domini dell'applicazione del componente aggiuntivo provocano un arresto anomalo dell'intera applicazione, anche in presenza di un limite di isolamento. WPF e il .NET Framework modello di componente aggiuntivo forniscono tuttavia un modo semplice per aggirare questo problema e migliorare la stabilità dell'applicazione. Un componente aggiuntivo WPF che visualizza un'interfaccia utente crea un <xref:System.Windows.Threading.Dispatcher> per il thread in cui viene eseguito il dominio dell'applicazione, se l'applicazione host è un'applicazione WPF. È possibile rilevare tutte le eccezioni non gestite che si verificano nel dominio applicazione gestendo l'evento <xref:System.Windows.Threading.Dispatcher.UnhandledException> della <xref:System.Windows.Threading.Dispatcher>del componente aggiuntivo WPF. È possibile ottenere il <xref:System.Windows.Threading.Dispatcher> dalla proprietà <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>.

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a>Limitazioni dei componenti aggiuntivi WPF

Oltre ai vantaggi offerti da WPF ai comportamenti predefiniti forniti da <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>e handle di finestra, esistono anche alcune limitazioni per le interfacce utente dei componenti aggiuntivi visualizzate dalle applicazioni host:

- Le interfacce utente del componente aggiuntivo visualizzate da un'applicazione host non rispettano il comportamento di ritaglio dell'applicazione host.

- Il concetto di *spazio aereo* negli scenari di interoperabilità si applica anche ai componenti aggiuntivi (vedere [Cenni preliminari sulle aree di tecnologia](../advanced/technology-regions-overview.md)).

- I servizi dell'interfaccia utente di un'applicazione host, ad esempio ereditarietà delle risorse, data binding e comandi, non sono automaticamente disponibili per le interfacce utente dei componenti aggiuntivi. Per fornire questi servizi al componente aggiuntivo è necessario aggiornare la pipeline.

- Un'interfaccia utente del componente aggiuntivo non può essere ruotata, ridimensionata, inclinata o modificata in altro modo da una trasformazione. vedere [Cenni preliminari sulle trasformazioni](../graphics-multimedia/transforms-overview.md).

- Il contenuto all'interno delle interfacce utente del componente aggiuntivo di cui viene eseguito il rendering mediante operazioni di disegno dallo spazio dei nomi <xref:System.Drawing> può includere la fusione alfa. Tuttavia, l'interfaccia utente di un componente aggiuntivo e l'interfaccia utente dell'applicazione host che lo contiene devono essere di 100% opaco; in altre parole, la proprietà `Opacity` in entrambi i tipi di oggetto deve essere impostata su 1.

- Se la <xref:System.Windows.Window.AllowsTransparency%2A> proprietà di una finestra nell'applicazione host che contiene un'interfaccia utente del componente aggiuntivo è impostata su `true`, il componente aggiuntivo è invisibile. Questo vale anche se l'interfaccia utente del componente aggiuntivo è opaca al 100%, ovvero la proprietà `Opacity` ha un valore pari a 1.

- Un'interfaccia utente del componente aggiuntivo deve essere visualizzata sopra altri elementi WPF nella stessa finestra di primo livello.

- Non è possibile eseguire il rendering di alcuna parte dell'interfaccia utente di un componente aggiuntivo utilizzando un <xref:System.Windows.Media.VisualBrush>. Il componente aggiuntivo può invece creare uno snapshot dell'interfaccia utente generata per creare una bitmap che può essere passata all'applicazione host usando i metodi definiti dal contratto.

- I file multimediali non possono essere riprodotti da un <xref:System.Windows.Controls.MediaElement> in un'interfaccia utente del componente aggiuntivo.

- Gli eventi del mouse generati per l'interfaccia utente del componente aggiuntivo non vengono ricevuti né generati dall'applicazione host e il valore della proprietà `IsMouseOver` per l'interfaccia utente dell'applicazione host è `false`.

- Quando lo stato attivo viene spostato tra i controlli in un'interfaccia utente di un componente aggiuntivo, gli eventi `GotFocus` e `LostFocus` non vengono ricevuti né generati dall'applicazione host.

- La parte di un'applicazione host che contiene un'interfaccia utente del componente aggiuntivo appare bianca quando viene stampata.

- Tutti i dispatcher (vedere <xref:System.Windows.Threading.Dispatcher>) creati dall'interfaccia utente del componente aggiuntivo devono essere arrestati manualmente prima che il componente aggiuntivo del proprietario venga scaricato se l'esecuzione dell'applicazione host continua. Il contratto può implementare metodi che consentono all'applicazione host di segnalare il componente aggiuntivo prima che il componente aggiuntivo venga scaricato, consentendo così all'interfaccia utente del componente aggiuntivo di arrestare i dispatcher.

- Se un'interfaccia utente del componente aggiuntivo è un <xref:System.Windows.Controls.InkCanvas> o contiene una <xref:System.Windows.Controls.InkCanvas>, non è possibile scaricare il componente aggiuntivo.

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a>Ottimizzazione delle prestazioni

Per impostazione predefinita, quando vengono usati più domini applicazione, i vari .NET Framework assembly richiesti da ogni applicazione vengono caricati nel dominio dell'applicazione. Di conseguenza, il tempo necessario per creare nuovi domini dell'applicazione e avviare le applicazioni al loro interno potrebbe influire sulle prestazioni. Tuttavia, il .NET Framework fornisce un modo per ridurre i tempi di avvio indicando alle applicazioni di condividere gli assembly tra domini applicazione se sono già stati caricati. A tale scopo, usare l'attributo <xref:System.LoaderOptimizationAttribute>, che deve essere applicato al metodo del punto di ingresso (`Main`). In questo caso, è necessario usare soltanto il codice per implementare la definizione dell'applicazione (vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)).

## <a name="see-also"></a>Vedere anche

- <xref:System.LoaderOptimizationAttribute>
- [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Domini dell'applicazione](../../app-domains/application-domains.md)
- [Panoramica di .NET Framework Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [Creazione di oggetti in remoto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [Procedure relative alla struttura ad albero e alla serializzazione degli elementi](how-to-topics.md)
