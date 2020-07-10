---
title: Blazorper gli sviluppatori di Web Form ASP.NET
description: Scopri come creare app Web con stack completo con .NET usando Blazor e .NET Core in modo semplice e familiare.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: 779eb47d9796c61df9939d0e7de287443870576e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173250"
---
# <a name="blazor-for-aspnet-web-forms-developers"></a>Blazorper gli sviluppatori di Web Form ASP.NET

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![Screenshot che mostra le app senza server e-book cover.](./media/index/blazor-for-web-forms-developers-cover.png)

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

> **[Daniel Roth](https://github.com/danroth27)**, responsabile del programma principale, Microsoft Corp.

> **[Jeff Fritz](https://github.com/csharpfritz)**, Senior Program Manager, Microsoft Corp.

> **[Taylor Southwick](https://github.com/twsouthwick)**, Senior Software Engineer, Microsoft Corp.

> **[Scott Addie](https://github.com/scottaddie)**, Senior Content Developer, Microsoft Corp.

## <a name="introduction"></a>Introduzione

.NET offre un ampio supporto per lo sviluppo di app Web tramite ASP.NET, un set completo di Framework e strumenti per la creazione di qualsiasi tipo di app Web. ASP.NET dispone di una propria derivazione di Framework e tecnologie Web che iniziano a tornare indietro con le pagine ASP (Classic Active Server Pages). I Framework, ad esempio ASP.NET Web Forms, ASP.NET MVC, Pagine Web ASP.NET e ASP.NET Core di recente, offrono una soluzione produttiva e potente per creare app Web con *rendering server* , in cui il contenuto dell'interfaccia utente viene generato dinamicamente sul server in risposta alle richieste HTTP. Ogni framework ASP.NET è adatto a un pubblico diverso e a una filosofia di compilazione di app. ASP.NET Web Forms è stato fornito con la versione originale del .NET Framework e lo sviluppo Web è stato abilitato utilizzando molti dei modelli noti agli sviluppatori desktop, come i controlli dell'interfaccia utente riutilizzabili con una semplice gestione degli eventi. Tuttavia, nessuna delle offerte ASP.NET fornisce un modo per eseguire il codice eseguito nel browser dell'utente. A tale scopo, è necessario scrivere JavaScript e usare uno dei numerosi Framework e strumenti JavaScript che si sono rivelati in e fuori dalla popolarità negli anni: jQuery, Knockout, angolare, React e così via.

[Blazor](https://blazor.net)è un nuovo framework Web che modifica le funzionalità possibili durante la creazione di app Web con .NET. Blazorè un Framework dell'interfaccia utente Web sul lato client basato su C# anziché su JavaScript. Con Blazor è possibile scrivere i componenti della logica lato client e dell'interfaccia utente in C#, compilarli in assembly .NET normali e quindi eseguirli direttamente nel browser usando un nuovo standard Web aperto denominato WebAssembly . In alternativa, è Blazor possibile eseguire i componenti dell'interfaccia utente .NET sul server e gestire tutte le interazioni dell'interfaccia utente in una connessione in tempo reale con il browser. Una volta abbinato a .NET in esecuzione nel server, Blazor Abilita lo sviluppo Web completo con .NET. Sebbene Blazor condivida molte comunanze con ASP.NET Web Form, ad esempio con un modello di componente riutilizzabile e un modo semplice per gestire gli eventi degli utenti, si basa anche sulle fondamenta di .NET Core per offrire un'esperienza di sviluppo web moderna e ad alte prestazioni.

Questo libro introduce gli sviluppatori Web Form ASP.NET a Blazor in modo che sia familiare e conveniente. Introduce i Blazor concetti in parallelo con concetti analoghi nei Web form ASP.NET e spiega anche i nuovi concetti che potrebbero essere meno familiari. Viene illustrata una vasta gamma di argomenti e problematiche, tra cui creazione di componenti, routing, layout, configurazione e sicurezza. Sebbene il contenuto di questo libro sia principalmente per l'abilitazione di un nuovo sviluppo, illustra anche le linee guida e le strategie per la migrazione di Web Form ASP.NET esistenti a Blazor quando si desidera modernizzare un'app esistente.

## <a name="who-should-use-the-book"></a>Chi deve usare il libro

Questo libro è per gli sviluppatori di Web Form ASP.NET che cercano un'introduzione a Blazor che riguarda le conoscenze e le competenze esistenti. Questo manuale può essere utile per iniziare rapidamente a usare un nuovo Blazor progetto basato su o per creare una guida di orientamento per la modernizzazione di un'applicazione Web form ASP.NET esistente.

## <a name="how-to-use-the-book"></a>Come usare il libro

La prima parte di questo libro riguarda il contenuto e lo confronta con lo Blazor sviluppo di app Web con ASP.NET Web Forms. Il libro illustra quindi una serie di Blazor argomenti, capitolo per capitolo, e mette in relazione ogni Blazor concetto con il concetto corrispondente in ASP.NET Web Forms o spiega completamente tutti i concetti completamente nuovi. Il libro si riferisce regolarmente anche a un'app di esempio completa implementata in Web Form ASP.NET e Blazor per dimostrare le Blazor funzionalità e fornire un case study per la migrazione da Web Form ASP.NET a Blazor . È possibile trovare entrambe le implementazioni dell'app di esempio (ASP.NET Web Forms and Blazor Versions) su [GitHub](https://github.com/dotnet-architecture/eshoponblazor).

## <a name="what-this-book-doesnt-cover"></a>Argomenti non coperti da questo libro

Questo libro è un'introduzione a Blazor , non una guida alla migrazione completa. Sebbene includa indicazioni su come approcciare la migrazione di un progetto da Web Form ASP.NET a Blazor , non tenta di coprire tutte le sfumature e i dettagli. Per indicazioni generali sulla migrazione da ASP.NET a ASP.NET Core, vedere la guida alla [migrazione](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/) nella documentazione di ASP.NET Core.

### <a name="additional-resources"></a>Risorse aggiuntive

È possibile trovare il Blazor Home page ufficiale e la documentazione all'indirizzo <https://blazor.net> .

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questo libro ed esempi correlati sono in continua evoluzione, quindi il feedback è stato accolto. Per Commenti su come migliorare questo libro, usare la sezione feedback nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Avanti](introduction.md)
