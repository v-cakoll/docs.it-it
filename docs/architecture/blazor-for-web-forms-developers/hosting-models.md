---
title: Modelli di hosting dell'app Blazor
description: Informazioni sui diversi modi per ospitare un'app Blazor, anche nel browser su WebAssembly o sul server.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 77a022b01efba01038790c9601ea03f315a28fdf
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607932"
---
# <a name="blazor-app-hosting-models"></a>Modelli di hosting dell'app Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le app Blazor possono essere ospitate in IIS proprio come le app Web Form ASP.NET. Le app Blazor possono anche essere ospitate in uno dei seguenti modi:

- Lato client nel browser su WebAssembly.
- Lato server in un'app ASP.NET Core.

## <a name="blazor-webassembly-apps"></a>App Blazor WebAssembly

Le app Blazor WebAssembly vengono eseguite direttamente nel browser in un runtime .NET basato su WebAssembly. Le app Blazor WebAssembly funzionano in modo simile ai framework JavaScript front-end come Angular o React. Tuttavia, invece di scrivere JavaScript si scrive c'è. Il runtime .NET viene scaricato con l'app insieme all'assembly dell'app e alle eventuali dipendenze necessarie. Non sono necessari plug-in o estensioni del browser.

Gli assembly scaricati sono normali assembly .NET, come si userebbe in qualsiasi altra app .NET. Poiché il runtime supporta .NET Standard, è possibile utilizzare le librerie .NET Standard esistenti con l'app Blazor WebAssembly. Tuttavia, questi assembly verranno comunque eseguiti nella sandbox di sicurezza del browser. Alcune funzionalità possono <xref:System.PlatformNotSupportedException>generare un , ad esempio il tentativo di accedere al file system o l'apertura di connessioni di rete arbitrarie.

Quando l'app viene caricata, il runtime di .NET viene avviato e punta all'assembly dell'app. Viene eseguita la logica di avvio dell'app e viene eseguito il rendering dei componenti radice. Blazor calcola gli aggiornamenti dell'interfaccia utente in base all'output di rendering dai componenti. Vengono quindi applicati gli aggiornamenti DOM.

![WebAssembly Blazor](media/hosting-models/blazor-webassembly.png)

Le app Blazor WebAssembly vengono eseguite esclusivamente sul lato client. Tali app possono essere distribuite in soluzioni di hosting di siti statici come GitHub Pages o Azure Static Website Hosting. .NET non è necessario nel server. Il collegamento diretto a parti dell'app richiede in genere una soluzione di routing nel server. La soluzione di routing reindirizza le richieste alla radice dell'app. Ad esempio, questo reindirizzamento può essere gestito utilizzando le regole di riscrittura URL in IIS.

Per ottenere tutti i vantaggi dello sviluppo Web .NET full-stack e full-stack, ospitare l'app Blazor WebAssembly con ASP.NET Core. Usando .NET sia sul client che sul server, puoi facilmente condividere il codice e compilare la tua app usando un set coerente di linguaggi, framework e strumenti. Blazor fornisce modelli pratici per l'impostazione di una soluzione che contiene sia un'applicazione Blazor WebAssembly che un progetto host ASP.NET Core. Quando la soluzione viene compilata, i file statici compilati dall'app Blazor sono ospitati dall'app ASP.NET Core con il routing di fallback già configurato.

## <a name="blazor-server-apps"></a>App Blazor Server

Ricordiamo dalla discussione [sull'architettura Blazor](architecture-comparison.md#blazor) che i componenti Blazor `RenderTree`rendono l'output in un'astrazione intermedia denominata . Il framework Blazor confronta quindi ciò che è stato eseguito il rendering con ciò che è stato precedentemente renderizzato. Le differenze vengono applicate al DOM. I componenti Blazor vengono disaccoppiati dal modo in cui viene applicato l'output sottoposto a rendering. Di conseguenza, i componenti stessi non devono essere eseguiti nello stesso processo del processo di aggiornamento dell'interfaccia utente. Infatti, non devono nemmeno funzionare sulla stessa macchina.

Nelle app Blazor Server, i componenti vengono eseguiti sul server anziché sul lato client nel browser. Gli eventi dell'interfaccia utente che si verificano nel browser vengono inviati al server tramite una connessione in tempo reale. Gli eventi vengono inviati alle istanze del componente corretto. Il rendering dei componenti e la differenza dell'interfaccia utente calcolata viene serializzata e inviata al browser in cui viene applicato al DOM.

![Server Blazor](media/hosting-models/blazor-server.png)

Il modello di hosting Blazor Server può sembrare familiare <xref:System.Web.UI.UpdatePanel> se è stato utilizzato ASP.NET AJAX e il controllo. Il `UpdatePanel` controllo gestisce l'applicazione di aggiornamenti parziali della pagina in risposta agli eventi trigger nella pagina. Quando viene attivato, richiede `UpdatePanel` un aggiornamento parziale e quindi lo applica senza dover aggiornare la pagina. Lo stato dell'interfaccia `ViewState`utente viene gestito tramite . Le app del server Blazor sono leggermente diverse in quanto l'app richiede una connessione attiva con il client. Inoltre, tutto lo stato dell'interfaccia utente viene mantenuto nel server. A parte queste differenze, i due modelli sono concettualmente simili.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Come scegliere il modello di hosting Blazor giusto

Come descritto nel [modello di hosting Blazor docs](/aspnet/core/blazor/hosting-models), i diversi modelli di hosting Blazor hanno diversi compromessi.

Il modello di hosting Blazor WebAssembly presenta i vantaggi seguenti:

- Non esiste alcuna dipendenza sul lato server .NET. L'app è completamente funzionante dopo essere stata scaricata nel client.
- Le risorse e le funzionalità dei client sono sfruttate appieno.
- Il lavoro viene scaricato dal server al client.
- Non è necessario un server Web ASP.NET Core per ospitare l'app. Scenari di distribuzione senza server sono possibili (ad esempio, la gestione dell'app da una rete CDN).

Gli aspetti negativi del modello di hosting Blazor WebAssembly sono:

- Le funzionalità del browser limitano l'app.
- È necessario utilizzare hardware e software client in grado (ad esempio, il supporto WebAssembly).
- Le dimensioni del download sono maggiori e il caricamento delle app richiede più tempo.
- Il supporto di runtime e strumenti .NET è meno maturo. Ad esempio, esistono limitazioni nel supporto e nel debug di [.NET Standard.For](../../standard/net-standard.md) example, there are limitations in .NET Standard support and debugging.

Al contrario, il modello di hosting Blazor Server offre i seguenti vantaggi:

- Le dimensioni del download sono molto più piccole di un'app lato client e l'app viene caricata molto più velocemente.
- L'app sfrutta appieno le funzionalità del server, incluso l'uso di qualsiasi API compatibile con .NET Core.
- .NET Core nel server viene usato per eseguire l'app, pertanto gli strumenti .NET esistenti, ad esempio il debug, funzionano come previsto.
- Sono supportati i thin client. Ad esempio, le app sul lato server funzionano con browser che non supportano WebAssembly e su dispositivi con risorse limitate.
- La base di codice .NET/Cè dell'app, incluso il codice del componente dell'app, non viene servita ai client.

Gli svantaggi del modello di hosting di Blazor Server sono:

- Latenza dell'interfaccia utente più elevata. Ogni interazione dell'utente comporta un hop di rete.
- Non è disponibile alcun supporto offline. Se la connessione client non riesce, l'app smette di funzionare.
- La scalabilità è complessa per le app con molti utenti. Il server deve gestire più connessioni client e gestire lo stato client.
- Per gestire l'app è necessario un server ASP.NET Core. Gli scenari di distribuzione senza server non sono possibili. Ad esempio, non è possibile gestire l'app da una rete CDN.

L'elenco precedente di compromessi potrebbe essere intimidatorio, ma il modello di hosting può essere modificato in un secondo momento. Indipendentemente dal modello di hosting Blazor selezionato, il modello di componente è *lo stesso.* In linea di principio, gli stessi componenti possono essere utilizzati con entrambi i modelli di hosting. Il codice dell'app non cambia; Tuttavia, è consigliabile introdurre astrazioni in modo che i componenti rimangano indipendenti dal modello. Le astrazioni consentono all'app di adottare più facilmente un modello di hosting diverso.

## <a name="deploy-your-app"></a>Distribuire l'app Web

ASP.NET le applicazioni Web Form sono in genere ospitate in IIS in un computer o un cluster Windows Server. Le app Blazor possono anche:

- Essere ospitato in IIS, come file statici o come un'app ASP.NET Core.
- Sfrutta ASP.NET flessibilità di Core per essere ospitata su varie piattaforme e infrastrutture server. Ad esempio, è possibile ospitare un'app Blazor utilizzando [Nginx](/aspnet/core/host-and-deploy/linux-nginx) o Apache su Linux.For example, you can host a Blazor App using Nginx or [Apache](/aspnet/core/host-and-deploy/linux-apache) on Linux. Per altre informazioni su come pubblicare e distribuire app Blazor, vedere la documentazione relativa all'hosting e alla distribuzione di Blazor.For more information about how to publish and deploy Blazor apps, see the Blazor [Hosting and deployment](/aspnet/core/host-and-deploy/blazor/) documentation.

Nella sezione successiva verrà illustrato come vengono impostati i progetti per le app Blazor WebAssembly e Blazor Server.

>[!div class="step-by-step"]
>[Successivo](architecture-comparison.md)
>[precedente](project-structure.md)
