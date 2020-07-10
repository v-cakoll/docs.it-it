---
title: Blazormodelli di hosting di app
description: Informazioni sui diversi modi per ospitare un' Blazor app, ad esempio nel browser in WebAssembly o nel server.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: a0d37392a65cfcbff9642476d9fdb1e5c662e66a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173263"
---
# <a name="blazor-app-hosting-models"></a>Blazormodelli di hosting di app

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazorle app possono essere ospitate in IIS esattamente come le app Web Form ASP.NET. Blazorle app possono anche essere ospitate in uno dei modi seguenti:

- Lato client nel browser WebAssembly .
- Lato server in un'app ASP.NET Core.

## <a name="blazor-webassembly-apps"></a>BlazorWebAssemblyapp di

BlazorWebAssemblyle app vengono eseguite direttamente nel browser in un WebAssembly Runtime .NET basato su. Blazorle WebAssembly app funzionano in modo analogo ai Framework JavaScript front-end come angolari o React. Tuttavia, invece di scrivere JavaScript, scrivere C#. Il Runtime .NET viene scaricato con l'app insieme all'assembly dell'app e a tutte le dipendenze necessarie. Non sono necessarie estensioni o plug-in del browser.

Gli assembly scaricati sono assembly .NET normali, come si farebbe per qualsiasi altra app .NET. Poiché il runtime supporta .NET Standard, è possibile usare le librerie di .NET Standard esistenti con l' Blazor WebAssembly app. Tuttavia, questi assembly vengono comunque eseguiti nella sandbox di sicurezza del browser. Alcune funzionalità possono generare un <xref:System.PlatformNotSupportedException> , ad esempio il tentativo di accedere al file System o l'apertura di connessioni di rete arbitrarie.

Quando l'app viene caricata, il Runtime .NET viene avviato e punta all'assembly dell'app. Viene eseguita la logica di avvio dell'app e viene eseguito il rendering dei componenti radice. Blazorcalcola gli aggiornamenti dell'interfaccia utente in base all'output di cui è stato eseguito il rendering dai componenti. Vengono quindi applicati gli aggiornamenti DOM.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazorle WebAssembly app vengono eseguite esclusivamente sul lato client. Queste app possono essere distribuite in siti statici che ospitano soluzioni come pagine GitHub o hosting di siti web statici di Azure. .NET non è necessario nel server. Il collegamento approfondito a parti dell'app richiede in genere una soluzione di routing sul server. La soluzione di routing reindirizza le richieste alla radice dell'app. Questo reindirizzamento, ad esempio, può essere gestito con le regole di riscrittura URL in IIS.

Per sfruttare tutti i vantaggi dello Blazor sviluppo Web .NET e dello stack completo, ospitare l' Blazor WebAssembly app con ASP.NET Core. Utilizzando .NET sia nel client che nel server, è possibile condividere facilmente il codice e compilare l'app utilizzando un set coerente di linguaggi, Framework e strumenti. Blazorfornisce modelli pratici per la configurazione di una soluzione che contiene sia un' Blazor WebAssembly app che un progetto host ASP.NET Core. Quando la soluzione viene compilata, i file statici compilati dall' Blazor app sono ospitati dall'app ASP.NET Core con routing di fallback già configurato.

## <a name="blazor-server-apps"></a>BlazorApp Server

Dal dibattito sull' [ Blazor architettura](architecture-comparison.md#blazor) , i Blazor componenti eseguono il rendering dell'output in un'astrazione intermedia denominata `RenderTree` . Il Blazor Framework confronta quindi gli elementi di cui è stato eseguito il rendering con quello precedentemente sottoposto a rendering. Le differenze vengono applicate al DOM. Blazori componenti sono separati dalla modalità di applicazione dell'output sottoposto a rendering. Di conseguenza, non è necessario che i componenti vengano eseguiti nello stesso processo del processo di aggiornamento dell'interfaccia utente. In realtà, non è nemmeno necessario eseguirli nello stesso computer.

Nelle Blazor app Server, i componenti vengono eseguiti sul server invece che sul lato client nel browser. Gli eventi dell'interfaccia utente che si verificano nel browser vengono inviati al server tramite una connessione in tempo reale. Gli eventi vengono inviati alle istanze dei componenti corrette. I componenti eseguono il rendering e la differenza dell'interfaccia utente calcolata viene serializzata e inviata al browser dove viene applicata al DOM.

![BlazorServer](media/hosting-models/blazor-server.png)

Il Blazor modello di hosting del server può sembrare familiare se è stato usato ASP.NET AJAX e il <xref:System.Web.UI.UpdatePanel> controllo. Il `UpdatePanel` controllo gestisce l'applicazione degli aggiornamenti parziali della pagina in risposta agli eventi trigger nella pagina. Quando viene attivato, `UpdatePanel` richiede un aggiornamento parziale, quindi lo applica senza dover aggiornare la pagina. Lo stato dell'interfaccia utente viene gestito tramite `ViewState` . BlazorLe app Server sono leggermente diverse in quanto l'app richiede una connessione attiva con il client. Inoltre, tutti gli Stati dell'interfaccia utente vengono mantenuti nel server. A parte queste differenze, i due modelli sono concettualmente simili.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Come scegliere il modello di Blazor hosting appropriato

Come descritto nel [ Blazor modello di hosting docs](/aspnet/core/blazor/hosting-models), i diversi Blazor modelli di hosting presentano compromessi diversi.

Il Blazor WebAssembly modello di hosting presenta i vantaggi seguenti:

- Non esiste alcuna dipendenza lato server .NET. L'app funziona completamente dopo il download nel client.
- Le risorse e le funzionalità client sono completamente sfruttate.
- Il lavoro viene scaricato dal server al client.
- Non è necessario un server Web ASP.NET Core per ospitare l'app. Gli scenari di distribuzione senza server sono possibili, ad esempio per servire l'app da una rete CDN.

Gli svantaggi del modello di Blazor WebAssembly hosting sono:

- Le funzionalità del browser limitano l'app.
- È necessario il software e l'hardware client in grado di supportare, ad esempio il WebAssembly supporto.
- Le dimensioni del download sono maggiori e le app importano più tempo per il caricamento.
- Il supporto di runtime e strumenti .NET è meno maturo. Esistono, ad esempio, alcune limitazioni in [.NET standard](../../standard/net-standard.md) supporto e debug.

Viceversa, il modello di Blazor hosting del server offre i seguenti vantaggi:

- Le dimensioni del download sono molto più piccole di quelle di un'app sul lato client e l'app viene caricata molto più velocemente.
- L'app sfrutta appieno le funzionalità del server, incluso l'uso di tutte le API compatibili con .NET Core.
- .NET Core nel server viene usato per eseguire l'app, in modo che gli strumenti .NET esistenti, ad esempio il debug, funzionino come previsto.
- Sono supportati i thin client. Ad esempio, le app sul lato server funzionano con i browser che non supportano WebAssembly e nei dispositivi con vincoli di risorse.
- La codebase .NET/C# dell'app, incluso il codice componente dell'app, non è servita ai client.

Gli svantaggi del modello di Blazor hosting del server sono:

- Latenza dell'interfaccia utente superiore. Ogni interazione dell'utente comporta un hop di rete.
- Non è disponibile alcun supporto offline. Se la connessione client non riesce, l'app smette di funzionare.
- La scalabilità è complessa per le app con molti utenti. Il server deve gestire più connessioni client e gestire lo stato del client.
- Per gestire l'app, è necessario un server ASP.NET Core. Gli scenari di distribuzione senza server non sono possibili. Ad esempio, non è possibile gestire l'app da una rete CDN.

L'elenco precedente dei compromessi potrebbe essere intimidatorio, ma il modello di hosting può essere modificato in un secondo momento. Indipendentemente dal Blazor modello di hosting selezionato, il modello di componente è *lo stesso*. In linea di principio, gli stessi componenti possono essere utilizzati con uno dei due modelli di hosting. Il codice dell'app non cambia; Tuttavia, è consigliabile introdurre astrazioni in modo che i componenti restino a ospitare indipendente dal modello. Le astrazioni consentono all'app di adottare più facilmente un modello di hosting diverso.

## <a name="deploy-your-app"></a>Distribuire l'app

Le app Web Form ASP.NET sono in genere ospitate in IIS in un computer o in un cluster Windows Server. Blazorle app possono anche:

- Essere ospitati in IIS, come file statici o come app ASP.NET Core.
- Sfrutta la flessibilità di ASP.NET Core per essere ospitata su diverse piattaforme e infrastrutture server. Ad esempio, è possibile ospitare un' Blazor app usando [nginx](/aspnet/core/host-and-deploy/linux-nginx) o [Apache](/aspnet/core/host-and-deploy/linux-apache) in Linux. Per ulteriori informazioni su come pubblicare e distribuire Blazor le app, vedere la Blazor documentazione relativa all' [hosting e alla distribuzione](/aspnet/core/host-and-deploy/blazor/) .

Nella sezione successiva verrà esaminato il modo in Blazor WebAssembly Blazor cui vengono configurati i progetti per e le app Server.

>[!div class="step-by-step"]
>[Precedente](architecture-comparison.md) 
> [Avanti](project-structure.md)
