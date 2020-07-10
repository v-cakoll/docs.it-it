---
title: Introduzione a Blazor per gli sviluppatori di Web form ASP.NET
description: Introduzione Blazor e scrittura di app Web con stack completo con .NET
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: 8ef2c7d66d50abb34e536b6333e3aa68ee2bb07d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173133"
---
# <a name="an-introduction-to-blazor-for-aspnet-web-forms-developers"></a>Introduzione a Blazor per gli sviluppatori di Web form ASP.NET

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il framework Web Forms di ASP.NET è stato uno sviluppo Web .NET, dal momento che il .NET Framework è stato inizialmente fornito in 2002. Quando il Web era ancora in gran parte nel suo complesso, ASP.NET Web Forms rendeva semplice e produttiva la creazione di app Web grazie all'adozione di molti dei modelli utilizzati per lo sviluppo di applicazioni desktop. Nei Web Form ASP.NET, le pagine Web possono essere composte rapidamente da controlli dell'interfaccia utente riutilizzabili. Le interazioni dell'utente vengono gestite naturalmente come eventi. È disponibile un ampio ecosistema di controlli dell'interfaccia utente Web Form forniti da Microsoft e dai fornitori di controlli. I controlli semplificano l'attività di connessione alle origini dati e la visualizzazione di visualizzazioni dei dati avanzate. Per l'inclinazione visiva, progettazione Web Form fornisce una semplice interfaccia di trascinamento della selezione per la gestione dei controlli.

Nel corso degli anni Microsoft ha introdotto nuovi framework Web basati su ASP.NET per risolvere le tendenze dello sviluppo Web. Alcuni framework Web includono ASP.NET MVC, Pagine Web ASP.NET e ASP.NET Core più di recente. Con ogni nuovo Framework, alcuni hanno stimato il calo imminente dei Web Form ASP.NET e hanno criticato come Framework Web obsoleto e obsoleto. Nonostante queste stime, molti sviluppatori Web .NET continuano a trovare ASP.NET Web Forms un metodo semplice, stabile e produttivo per svolgere le proprie attività.

Al momento della stesura di questo articolo, quasi mezzo milione di sviluppatori Web utilizzano i Web Form ASP.NET ogni mese. Il framework Web Form ASP.NET è stabile al punto in cui documenti, esempi, libri e post di Blog di un decennio fa rimangono utili e pertinenti. Per molti sviluppatori Web .NET, "ASP.NET" è ancora sinonimo di "ASP.NET Web Forms" così com'era quando .NET è stato concepito per la prima volta. Gli argomenti per i pro e i contro di ASP.NET Web Forms rispetto agli altri nuovi framework Web .NET potrebbero infuriare. ASP.NET Web Forms rimane un Framework comune per la creazione di app Web.

Anche in questo caso, le innovazioni di sviluppo software non rallentano. Tutti gli sviluppatori di software devono rimanere aggiornati sulle nuove tecnologie e tendenze. In particolare, è opportuno considerare due tendenze:

1. Il passaggio a Open Source e multipiattaforma
2. Spostamento della logica dell'applicazione al client

## <a name="an-open-source-and-cross-platform-net"></a>.NET open source e multipiattaforma

Quando .NET e ASP.NET Web Forms sono stati distribuiti per la prima volta, l'ecosistema della piattaforma è stato notevolmente diverso rispetto a quello attualmente disponibile. I mercati desktop e server erano dominati da Windows. Piattaforme alternative come macOS e Linux hanno ancora difficoltà a ottenere la trazione. ASP.NET Web Forms viene fornito con il .NET Framework come componente solo Windows, il che significa che le app Web Form ASP.NET possono essere eseguite solo su computer Windows Server. Molti ambienti moderni usano ora tipi diversi di piattaforme per server e computer di sviluppo, in modo che il supporto multipiattaforma per molti utenti sia un requisito assoluto.

La maggior parte dei framework Web moderni è ora Open Source, che offre diversi vantaggi. Gli utenti non sono tenuti a un singolo proprietario del progetto per correggere i bug e aggiungere funzionalità. I progetti open source offrono una maggiore trasparenza sullo stato di avanzamento dello sviluppo e sulle modifiche imminenti. I progetti open source offrono contributi da un'intera community e favoriscono un ecosistema open source di supporto. Nonostante i rischi derivanti da Open Source, molti utenti e collaboratori hanno riscontrato misure di mitigazione appropriate che consentono loro di sfruttare i vantaggi di un ecosistema open source in modo sicuro e ragionevole. Esempi di tali mitigazioni includono i contratti di licenza con collaboratori, le licenze semplici, le analisi genealogiche e le fondamenta di supporto.

La community di .NET ha adottato sia il supporto multipiattaforma che Open Source. .NET Core è un'implementazione open source e multipiattaforma di .NET in esecuzione su una vasta gamma di piattaforme, tra cui Windows, macOS e varie distribuzioni di Linux. Novell fornisce mono, una versione open source di .NET. Mono viene eseguito in Android, iOS e una serie di altri fattori di forma, tra cui orologi e Smart TV. Microsoft ha annunciato che [.NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/) riconcilia .NET Core e mono in "un singolo runtime .NET e un Framework che può essere usato ovunque e che offre comportamenti di runtime uniformi ed esperienze di sviluppo".

ASP.NET Web Forms può trarre vantaggio dal passaggio al supporto Open Source e multipiattaforma? La risposta, purtroppo, è no o almeno non nello stesso extent del resto della piattaforma. Il team di .NET [ha recentemente reso chiaro](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) che i Web Form ASP.NET non verranno trasportati in .NET Core o .NET 5. Perché?

Sono state rilevate attività nei primi giorni di .NET Core per trasferire i Web Form ASP.NET. Il numero di modifiche di rilievo necessarie risulta troppo drastico. Esiste anche un'ammissione che anche per Microsoft, esiste un limite al numero di Framework Web che può supportare simultaneamente. Forse qualcuno della community prenderà la causa della creazione di una versione open source e multipiattaforma di ASP.NET Web Forms. Il [codice sorgente per ASP.NET Web Forms](https://github.com/microsoft/referencesource) è stato reso disponibile pubblicamente in forma di riferimento. Ma per il momento, sembra che i Web Form ASP.NET rimangano solo Windows e senza un modello di contributo open source. Se il supporto multipiattaforma o open source diventa importante per gli scenari in uso, sarà necessario cercare qualcosa di nuovo.

Questo significa che i Web Form ASP.NET sono *inattivi* e non devono più essere usati? Certo che no! Fino a quando il .NET Framework viene fornito come parte di Windows, ASP.NET Web Forms sarà un Framework supportato. Per molti sviluppatori di Web Form, la mancanza di supporto multipiattaforma e open source non è un problema. Se non si ha un requisito per il supporto multipiattaforma, open source o una delle altre nuove funzionalità di .NET Core o .NET 5, è bene usare ASP.NET Web Forms su Windows. I Web Form ASP.NET continueranno a essere un modo produttivo per scrivere app Web per molti anni.

Tuttavia, c'è un'altra tendenza che vale la pena prendere in considerazione e questo è il passaggio al client.

## <a name="client-side-web-development"></a>Sviluppo Web sul lato client

Tutti i. I framework Web basati su NET, inclusi i Web Form ASP.NET, hanno storicamente un elemento in comune: il *rendering server*è stato eseguito. Nelle app Web sottoposte a rendering server il browser esegue una richiesta al server, che esegue il codice (codice .NET nelle app ASP.NET) per produrre una risposta. Tale risposta viene inviata di nuovo al browser per la gestione. In questo modello il browser viene usato come motore di rendering sottile. Il lavoro difficile per produrre l'interfaccia utente, eseguire la logica di business e gestire lo stato si verifica nel server.

Tuttavia, i browser sono diventati piattaforme versatili. Implementano un numero sempre crescente di standard Web aperti che concedono l'accesso alle funzionalità del computer dell'utente. Perché non sfruttare i vantaggi della potenza di calcolo, dell'archiviazione, della memoria e di altre risorse del dispositivo client? Le interazioni dell'interfaccia utente in particolare possono trarre vantaggio da una sensazione più ricca e interattiva quando viene gestita almeno parzialmente o completamente lato client. La logica e i dati che devono essere gestiti sul server possono comunque essere gestiti sul lato server. È possibile usare chiamate API Web o persino su protocolli in tempo reale, come WebSocket. Questi vantaggi sono disponibili per gli sviluppatori Web gratuitamente se sono disposti a scrivere JavaScript. I Framework dell'interfaccia utente lato client, ad esempio angolare, React e VME, semplificano lo sviluppo Web sul lato client e sono diventati più popolari. Gli sviluppatori di Web Form ASP.NET possono inoltre trarre vantaggio dall'utilizzo del client e persino avere un supporto predefinito con Framework JavaScript integrati come ASP.NET AJAX.

Tuttavia, il bridging di due piattaforme e ecosistemi diversi, ovvero .NET e JavaScript, comporta un costo. Le competenze sono necessarie in due mondi paralleli con linguaggi, Framework e strumenti diversi. Il codice e la logica non possono essere facilmente condivisi tra client e server, causando una duplicazione e un sovraccarico di progettazione. Può anche essere difficile tenersi al passo con l'ecosistema JavaScript, che ha una cronologia di evoluzione a collo di rotta. Il Framework front-end e le preferenze dello strumento di compilazione cambiano rapidamente. Il settore ha osservato la progressione da grugnito a Gulp a Webpack e così via. Si è verificata la stessa varianza agitata con i Framework front-end, ad esempio jQuery, Knockout, angolare, React e VME. Tuttavia, dato il Monopoli del browser di JavaScript, c'era poca scelta. Ovvero, fino a quando la community Web non è stata insieme e ha causato un *miracolo* .

## <a name="webassembly-fulfills-a-need"></a>WebAssemblysoddisfa una necessità

In 2015, i principali fornitori di browser Uniti in un gruppo di community W3C hanno creato un nuovo standard Web aperto denominato WebAssembly . WebAssemblyè un codice byte per il Web. Se è possibile compilare il codice in WebAssembly , è possibile eseguirlo in qualsiasi browser su qualsiasi piattaforma con velocità quasi nativa. Sforzi iniziali incentrati su C/C++. Il risultato è una dimostrazione drammatica dell'esecuzione di motori di grafica 3D nativi direttamente nel browser senza plug-in. WebAssemblyè stato standardizzato e implementato da tutti i principali browser.

Il lavoro relativo all'esecuzione di .NET in WebAssembly è stato annunciato alla fine del 2017 e dovrebbe essere fornito in 2020, incluso il supporto di .NET 5. La possibilità di eseguire il codice .NET direttamente nel browser consente lo sviluppo Web con stack completo con .NET.

## <a name="blazor-full-stack-web-development-with-net"></a>Blazor: sviluppo Web con stack completo con .NET

In modo autonomo, la possibilità di eseguire il codice .NET in un browser non offre un'esperienza end-to-end per la creazione di app Web sul lato client. Ecco dove Blazor entra. Blazorè un Framework dell'interfaccia utente Web sul lato client basato su C# anziché su JavaScript. Blazorpuò essere eseguito direttamente nel browser tramite WebAssembly . Non è necessario alcun plug-in del browser. In alternativa, le Blazor app possono eseguire il lato server in .NET Core e gestire tutte le interazioni utente in una connessione in tempo reale con il browser.

Blazoroffre un ottimo supporto per gli strumenti in Visual Studio e Visual Studio Code. Il Framework include anche un modello di componente completo dell'interfaccia utente e offre funzionalità predefinite per:

- Moduli e convalida
- Inserimento di dipendenze
- Routing lato client
- Layout
- Debug nel browser
- Interoperabilità JavaScript

Blazorha molto in comune con ASP.NET Web Forms. Entrambi i Framework offrono modelli di programmazione dell'interfaccia utente con stato basato su componenti e basati su eventi. La differenza di architettura principale consiste nel fatto che ASP.NET Web Forms viene eseguito solo sul server. Blazorpuò essere eseguito sul client nel browser. Tuttavia, se si sta arrivando da uno sfondo Web Form ASP.NET, c'è molto da Blazor sentire familiare. Blazorè una soluzione naturale per gli sviluppatori di Web Form ASP.NET che cercano un metodo per sfruttare lo sviluppo lato client e il futuro multipiattaforma open source di .NET.

In questo libro viene fornita un'introduzione a Blazor che si rivolge in modo specifico agli sviluppatori di Web form ASP.NET. Ogni Blazor concetto viene presentato nel contesto delle funzionalità e delle procedure di ASP.NET Web Forms analoghe. Al termine di questo libro, sarà possibile comprendere quanto segue:

- Come compilare le Blazor app.
- Funzionamento Blazor .
- Come Blazor si riferisce a .NET Core.
- Strategie ragionevoli per la migrazione delle app Web Form ASP.NET esistenti a Blazor quando appropriato.

## <a name="get-started-with-blazor"></a>Introduzione ai Blazor

Per iniziare Blazor , è facile. Passare a <https://blazor.net> e seguire i collegamenti per installare il .NET Core SDK e i Blazor modelli di progetto appropriati. Sono inoltre disponibili istruzioni per la configurazione degli Blazor strumenti in Visual Studio o Visual Studio Code.

>[!div class="step-by-step"]
>[Precedente](index.md) 
> [Avanti](architecture-comparison.md)
