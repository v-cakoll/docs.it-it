---
title: Blazor per sviluppatori Web Forms ASP.NET
description: Scopri come creare app Web full-stack con .NET usando Blazor e .NET Core in modo semplice e familiare.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 394d11038b59f4cbe9e9955df43b6198eb5daaf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73088122"
---
# <a name="blazor-for-aspnet-web-forms-developers"></a>Blazor per sviluppatori Web Forms ASP.NET

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![Screenshot che mostra la copertina dell'e-book App senza server.](./media/index/blazor-for-web-forms-developers-cover.png)

> Download disponibile all'indirizzo: <https://aka.ms/blazor-ebook>

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori:

> **[Daniel Roth,](https://github.com/danroth27)** Principal Program Manager, Microsoft Corp.

> **[Jeff Fritz,](https://github.com/csharpfritz)** Senior Program Manager, Microsoft Corp.

> **[Taylor Southwick](https://github.com/twsouthwick)**, Senior Software Engineer, Microsoft Corp.

> **[Scott Addie](https://github.com/scottaddie)**, Senior Content Developer, Microsoft Corp.

## <a name="introduction"></a>Introduzione

.NET supporta da tempo lo sviluppo di app Web tramite ASP.NET, un set completo di framework e strumenti per la creazione di qualsiasi tipo di app Web. ASP.NET ha un proprio lignaggio di framework web e tecnologie che iniziano fino in fondo con le pagine ASP (Active Server Pages) classiche. Framework come ASP.NET Web Form, ASP.NET MVC, pagine Web ASP.NET e più recentemente ASP.NET Core, forniscono un modo produttivo e potente per creare app Web sottoposte a rendering del *server,* in cui il contenuto dell'interfaccia utente viene generato dinamicamente nel server in risposta alle richieste HTTP. Ogni framework ASP.NET si rivolge a un pubblico diverso e alla filosofia di creazione di app. ASP.NET Web Form forniti con la versione originale di .NET Framework e abilitato lo sviluppo Web utilizzando molti dei modelli familiari agli sviluppatori desktop, ad esempio i controlli riutilizzabili dell'interfaccia utente con una semplice gestione degli eventi. Tuttavia, nessuna delle offerte ASP.NET fornisce un modo per eseguire il codice eseguito nel browser dell'utente. A tale scopo, è necessario scrivere JavaScript e utilizzare uno dei numerosi framework e strumenti JavaScript che hanno gradualmente introdotto in campo di popolarità nel corso degli anni: jQuery, Knockout, Angular, React e così via.

[Blazor](https://blazor.net) è un nuovo framework web che cambia ciò che è possibile quando si creano applicazioni web con .NET. Blazor è un framework dell'interfaccia utente Web lato client basato su C , anziché JavaScript. Con Blazor è possibile scrivere la logica sul lato client e i componenti dell'interfaccia utente in C, compilarli in normali assembly .NET e quindi eseguirli direttamente nel browser utilizzando un nuovo standard Web aperto denominato WebAssembly. In alternativa, Blazor può eseguire i componenti dell'interfaccia utente .NET sul server e gestire tutte le interazioni dell'interfaccia utente in modo fluido tramite una connessione in tempo reale con il browser. Se associato a .NET in esecuzione sul server, Blazor consente lo sviluppo Web completo con .NET. Mentre Blazor condivide molti punti in comune con ASP.NET Web Form, come avere un modello di componente riutilizzabile e un modo semplice per gestire gli eventi utente, si basa anche sulle basi di .NET Core per fornire un'esperienza di sviluppo Web moderna e ad alte prestazioni.

Questo libro presenta ASP.NET sviluppatori di Web Form a Blazor in un modo che è familiare e conveniente. Introduce concetti Blazor in parallelo con concetti analoghi in ASP.NET Web Form, spiegando anche nuovi concetti che possono essere meno familiari. Viene illustrata un'ampia gamma di argomenti e problemi, tra cui la creazione di componenti, il routing, il layout, la configurazione e la sicurezza. E mentre il contenuto di questo libro è principalmente per consentire il nuovo sviluppo, copre anche le linee guida e le strategie per la migrazione di ASP.NET Web Form esistenti a Blazor per quando si desidera modernizzare un'app esistente.

## <a name="who-should-use-the-book"></a>Chi dovrebbe usare il libro

Questo libro è per ASP.NET gli sviluppatori di Web Form alla ricerca di un'introduzione a Blazor che si riferisca alle loro conoscenze e competenze esistenti. Questo libro consente di iniziare rapidamente un nuovo progetto basato su Blazor o di tracciare una roadmap per la modernizzazione di un'applicazione Web Form ASP.NET esistente.

## <a name="how-to-use-the-book"></a>Come utilizzare il libro

La prima parte di questo libro illustra cos'è Blazor e lo confronta con lo sviluppo di app Web con ASP.NET Web Form. Il libro tratta quindi una varietà di argomenti Blazor, capitolo per capitolo, e mette in relazione ogni concetto Blazor al concetto corrispondente in ASP.NET Web Form, o spiega completamente tutti i concetti completamente nuovi. Il libro si riferisce anche regolarmente a un'app di esempio completa implementata sia in ASP.NET Web Form che in Blazor per illustrare le funzionalità di Blazor e per fornire un case study per la migrazione da ASP.NET Web Form a Blazor. Entrambe le implementazioni dell'app di esempio (ASP.NET le versioni di Web Form e Blazor) sono disponibili in [GitHub](https://github.com/dotnet-architecture/eshoponblazor).

## <a name="what-this-book-doesnt-cover"></a>Ciò che questo libro non copre

Questo libro è un'introduzione a Blazor, non una guida completa alla migrazione. Sebbene includa indicazioni su come affrontare la migrazione di un progetto da ASP.NET Web Form a Blazor, non tenta di coprire ogni sfumatura e dettaglio. Per indicazioni più generali sulla migrazione da ASP.NET a ASP.NET Core, fare riferimento alle linee guida sulla migrazione nella documentazione di ASP.NET Core.For more general guidance on migrating from ASP.NET to ASP.NET Core, refer to the [migration guidance](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/) in the ASP.NET Core documentation.

### <a name="additional-resources"></a>Risorse aggiuntive

È possibile trovare la home page ufficiale <https://blazor.net>Blazor e la documentazione a .

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questo libro e i relativi campioni sono in continua evoluzione, quindi il tuo feedback è il benvenuto! Se hai commenti su come questo libro può essere migliorato, utilizza la sezione commenti e suggerimenti nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Avanti](introduction.md)
