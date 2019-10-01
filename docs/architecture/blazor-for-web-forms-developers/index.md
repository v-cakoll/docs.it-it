---
title: Blazor per sviluppatori Web Forms ASP.NET
description: Scopri come creare app Web con stack completo con .NET usando blazer e .NET Core in modo semplice e familiare.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 936f85d4fda9c5396a6586810735877488226157
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696936"
---
# <a name="blazor-for-aspnet-web-forms-developers"></a>Blazor per sviluppatori Web Forms ASP.NET

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![Screenshot con la copertina dell'e-book App serverless.](./media/index/blazor-for-web-forms-developers-cover.png)

> Download disponibile all'indirizzo: <https://aka.ms/blazor-ebook>

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori

> **[Daniel Roth](https://github.com/danroth27)** , responsabile del programma principale, Microsoft Corp.

> **[Jeff Fritz](https://github.com/csharpfritz)** , Senior Program Manager, Microsoft Corp.

> **[Taylor Southwick](https://github.com/twsouthwick)** , Senior Software Engineer, Microsoft Corp.

> **[Scott Addie](https://github.com/scottaddie)** , Senior Content Developer, Microsoft Corp.

## <a name="introduction"></a>Introduzione

.NET offre un ampio supporto per lo sviluppo di app Web tramite ASP.NET, un set completo di Framework e strumenti per la creazione di qualsiasi tipo di app Web. ASP.NET dispone di una propria derivazione di Framework e tecnologie Web che iniziano a tornare indietro con le pagine ASP (Classic Active Server Pages). Framework come ASP.NET Web Forms, ASP.NET MVC, Pagine Web ASP.NET e ASP.NET Core più di recente, offrono una soluzione produttiva e potente per creare app Web con *rendering server* , in cui il contenuto dell'interfaccia utente viene generato dinamicamente sul server in risposta a http richieste. Ogni framework ASP.NET è adatto a un pubblico diverso e a una filosofia di compilazione di app. ASP.NET Web Forms è stato fornito con la versione originale del .NET Framework e lo sviluppo Web è stato abilitato utilizzando molti dei modelli noti agli sviluppatori desktop, come i controlli dell'interfaccia utente riutilizzabili con una semplice gestione degli eventi. Tuttavia, nessuna delle offerte ASP.NET fornisce un modo per eseguire il codice eseguito nel browser dell'utente. A tale scopo, è necessario scrivere JavaScript e usare uno dei numerosi Framework e strumenti JavaScript che si sono rivelati in e fuori dalla popolarità negli anni: jQuery, Knockout, angolare, React e così via.

[Blazer](https://blazor.net) è un nuovo framework Web che modifica le funzionalità possibili durante la creazione di app Web con .NET. Blazer è un Framework dell'interfaccia utente Web sul lato client C# basato su anziché su JavaScript. Con blazer è possibile scrivere i componenti della logica lato client e dell'interfaccia C#utente in, compilarli in assembly .NET normali, quindi eseguirli direttamente nel browser usando un nuovo standard Web aperto denominato webassembly. In alternativa, blazer può eseguire i componenti dell'interfaccia utente .NET sul server e gestire tutte le interazioni dell'interfaccia utente in una connessione in tempo reale con il browser. Una volta abbinato a .NET in esecuzione sul server, blazer consente lo sviluppo Web con stack completo con .NET. Mentre Blazer condivide molte comunanze con i Web Form ASP.NET, ad esempio con un modello di componente riutilizzabile e un modo semplice per gestire gli eventi degli utenti, si basa anche sulle fondamenta di .NET Core per offrire un'esperienza di sviluppo web moderna e ad alte prestazioni.

In questo libro vengono introdotti gli sviluppatori di Web Form ASP.NET a blazer in modo che sia familiare e conveniente. Introduce i concetti di Blazer in parallelo con concetti analoghi nei Web Form ASP.NET e spiega anche i nuovi concetti che potrebbero essere meno familiari. Viene illustrata una vasta gamma di argomenti e problematiche, tra cui creazione di componenti, routing, layout, configurazione e sicurezza. Sebbene il contenuto di questo libro sia principalmente per l'abilitazione di un nuovo sviluppo, illustra anche le linee guida e le strategie per la migrazione di Web Form ASP.NET esistenti a blazer per quando si desidera modernizzare un'app esistente.

## <a name="who-should-use-the-book"></a>Chi deve usare il libro

Questo libro è per gli sviluppatori di Web Form ASP.NET che cercano un'introduzione a blazer che si riferisce alle proprie conoscenze e competenze esistenti. Questo manuale può essere utile per iniziare rapidamente a usare un nuovo progetto basato su blazer o per creare una guida di orientamento per la modernizzazione di un'applicazione Web Form ASP.NET esistente.

## <a name="how-to-use-the-book"></a>Come usare il libro

Nella prima parte di questo libro viene illustrata la funzionalità di blazer e viene confrontata con lo sviluppo di app Web con ASP.NET Web Form. Il libro illustra quindi una serie di argomenti, capitolo per capitolo, e mette in correlazione il concetto di Blazer al concetto corrispondente in ASP.NET Web Forms oppure spiega completamente tutti i concetti completamente nuovi. Il libro si riferisce regolarmente anche a un'app di esempio completa implementata in ASP.NET Web Forms e blazer per dimostrare le funzionalità di blazer e fornire un case study per la migrazione da Web Form ASP.NET a blazer. È possibile trovare entrambe le implementazioni dell'app di esempio (ASP.NET Web Forms and Blazer Versions) su [GitHub](https://github.com/dotnet-architecture/eshoponblazor).

## <a name="what-this-book-doesnt-cover"></a>Argomenti non coperti da questo libro

Questo libro è un'introduzione a blazer, non a una guida alla migrazione completa. Sebbene includa indicazioni su come approcciare la migrazione di un progetto da Web Form ASP.NET a blazer, non tenta di coprire tutte le sfumature e i dettagli. Per indicazioni generali sulla migrazione da ASP.NET a ASP.NET Core, vedere la guida alla [migrazione](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/) nella documentazione di ASP.NET Core.

### <a name="additional-resources"></a>Risorse aggiuntive

È possibile trovare la home page e la documentazione ufficiali di Blazer all'indirizzo <https://blazor.net>.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questo libro ed esempi correlati sono in continua evoluzione, quindi il feedback è stato accolto. Per Commenti su come migliorare questo libro, usare la sezione feedback nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[avanti](introduction.md)
