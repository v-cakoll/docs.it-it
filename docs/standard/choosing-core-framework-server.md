---
title: Scegliere tra .NET Core e .NET Framework per le app server
description: Guida che consente di decidere quale implementazione di .NET usare quando si compila un'app Server.
author: cartermp
ms.date: 04/28/2020
ms.openlocfilehash: 30157276bce53ed44dca5b660172e5556dab14f8
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507442"
---
# <a name="net-core-vs-net-framework-for-server-apps"></a>Confronto tra .NET Core e .NET Framework per le app Server

Per la creazione di app sul lato server sono supportate due implementazioni di .NET: .NET Framework e .NET Core. Entrambe condividono gran parte degli stessi componenti e possono condividere codice. Esistono, però, differenze fondamentali tra le due opzioni e la scelta dipende dall'obiettivo che si vuole conseguire. Questo articolo fornisce materiale sussidiario per identificare i casi in cui è opportuno usare ciascuna delle due opzioni.

Usare .NET Core per l'applicazione server nei casi seguenti:

- Si hanno esigenze multipiattaforma.
- Sono destinati a microservizi.
- Si usano i contenitori docker.
- Si hanno esigenze di elevate prestazioni e scalabilità.
- È necessaria l'installazione side-by-side delle versioni di .NET in base all'applicazione.

Usare .NET Framework per l'applicazione server nei casi seguenti:

- L'app usa attualmente .NET Framework (si consiglia di optare per l'estensione anziché per la migrazione).
- L'app usa pacchetti NuGet o librerie .NET di terze parti non disponibili per .NET Core.
- L'app usa tecnologie .NET non disponibili per .NET Core.
- L'app usa una piattaforma che non supporta .NET Core. Windows, macOS e Linux supportano .NET Core.

## <a name="when-to-choose-net-core"></a>Quando scegliere .NET Core

Nelle sezioni seguenti sono descritti in modo più dettagliato i motivi indicati in precedenza per la scelta di .NET Core.

### <a name="cross-platform-needs"></a>Esigenze multipiattaforma

Usare .NET Core se l'applicazione (Web/servizio) deve essere eseguita su più piattaforme (Windows, Linux e macOS).

.NET Core supporta i sistemi operativi indicati in precedenza come workstation di sviluppo. Visual Studio fornisce un ambiente di sviluppo integrato (IDE) per Windows e macOS. È anche possibile usare Visual Studio Code, che viene eseguito in macOS, Linux e Windows. Visual Studio Code supporta infatti .NET Core, incluse le funzionalità IntelliSense e di debug. La maggior parte degli editor di terze parti, ad esempio Sublime, Emacs e VI, è compatibile con .NET Core. Questi editor di terze parti accedono alla funzionalità IntelliSense dell'editor tramite [Omnisharp](https://www.omnisharp.net/). È anche possibile evitare qualsiasi editor di codice e usare direttamente il [interfaccia della riga di comando di .NET Core](../core/tools/index.md), disponibile per tutte le piattaforme supportate.

### <a name="microservices-architecture"></a>Architettura di microservizi

Un'architettura di microservizi consente di usare una combinazione di tecnologie in un limite di servizi. Grazie a questa tecnologia è quindi possibile adottare gradualmente .NET Core per nuovi microservizi che operano con altri microservizi o servizi. Ad esempio, è possibile combinare microservizi o servizi sviluppati con .NET Framework, Java, Ruby o altre tecnologie monolitiche.

Le piattaforme di infrastruttura disponibili sono numerose. [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) è appositamente concepita per sistemi di microservizi complessi e di grandi dimensioni. [Servizio app di Azure](https://azure.microsoft.com/services/app-service/) è la soluzione ideale per i microservizi senza stato. Le alternative basate su Docker sono adatte a qualsiasi tipo di approccio ai microservizi, come descritto nella sezione [Contenitori](#containers). Grazie al supporto di .NET Core, tutte queste piattaforme rappresentano soluzioni ideali per l'hosting dei microservizi.

Per altre informazioni sull'architettura dei microservizi, vedere [microservizi .NET. Architettura per le applicazioni .NET in contenitori](../architecture/microservices/index.md).

### <a name="containers"></a>Contenitori

I contenitori sono in genere usati insieme a un'architettura di microservizi, ma possano essere impiegati anche per creare contenitori di servizi o app Web basati su qualsiasi modello architettonico. È possibile usare .NET Framework su contenitori Windows, anche se le caratteristiche di modularità e leggerezza di .NET Core rendono questa piattaforma la scelta ideale per i contenitori. Quando si crea e si distribuisce un contenitore, la sua immagine risulta notevolmente più piccola con .NET Core rispetto a .NET Framework. Trattandosi di un'opzione multipiattaforma, è ad esempio possibile distribuire le app server in contenitori Docker di Linux.

È possibile ospitare i contenitori Docker nell'infrastruttura Linux o Windows in uso oppure in un servizio cloud, ad esempio il [servizio Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/). Il servizio Azure Kubernetes consente infatti di gestire, orchestrare e ridimensionare applicazioni basate su contenitore nel cloud.

### <a name="high-performance-and-scalable-systems"></a>Sistemi scalabili e ad alte prestazioni

Se il sistema richiede i massimi livelli di prestazioni e scalabilità, le opzioni ottimali sono rappresentate da .NET Core e ASP.NET Core. Grazie al runtime server ad alte prestazioni per Linux e Windows Server, .NET viene considerato come un framework Web dalle prestazioni ottimali nei [benchmark TechEmpower](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext).

Le prestazioni e la scalabilità sono particolarmente importanti per le architetture con centinaia di microservizi in esecuzione. Con ASP.NET Core i sistemi vengono eseguiti con un numero di server/macchine virtuali sensibilmente inferiore e questo si traduce in una riduzione dei costi di infrastruttura e hosting.

### <a name="side-by-side-net-versions-per-application-level"></a>Versioni .NET side-by-side per ogni livello di applicazione

Per installare applicazioni con dipendenze in versioni diverse di .NET, è consigliabile usare .NET Core, .NET Core supporta l'installazione side-by-side di versioni diverse del runtime di .NET Core nello stesso computer. Grazie all'installazione side-by-side, è possibile eseguire più servizi nello stesso server, ognuno con la rispettiva versione di .NET Core, riducendo inoltre i rischi e risparmiando sui costi degli aggiornamenti di applicazioni e delle operazioni IT.

L'installazione side-by-side non è possibile con .NET Framework. Si tratta di un componente di Windows e una sola versione può essere presente in un computer alla volta. Ogni versione di .NET Framework sostituisce la versione precedente. Se si installa una nuova app destinata a una versione successiva di .NET Framework, è possibile che si interrompano le app esistenti eseguite nel computer, perché la versione precedente è stata sostituita.

## <a name="when-to-choose-net-framework"></a>Quando scegliere .NET Framework

.NET Core offre vantaggi significativi per i nuovi modelli di applicazione e le nuove applicazioni. Tuttavia, .NET Framework continua a essere la scelta naturale per molti scenari esistenti e, di conseguenza, .NET Framework non viene sostituita da .NET Core per tutte le applicazioni server.

### <a name="current-net-framework-applications"></a>Applicazioni .NET Framework correnti

Nella maggior parte dei casi, non è necessario eseguire la migrazione delle applicazioni esistenti a .NET Core. Al contrario, un approccio consigliato è quello di usare .NET Core per estendere un'applicazione esistente, ad esempio con la scrittura di un nuovo servizio Web in ASP.NET Core.

### <a name="aspnet-core-on-net-framework"></a>ASP.NET Core .NET Framework

Per informazioni sul supporto di ASP.NET Core .NET Framework, vedere [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

### <a name="third-party-libraries-or-nuget-packages-not-available-for-net-core"></a>Librerie di terze parti o pacchetti NuGet non disponibili per .NET Core

Per le librerie è in corso l'adozione rapida di .NET Standard, .NET Standard Abilita la condivisione di codice in tutte le implementazioni di .NET, incluso .NET Core. Con .NET Standard 2.0, questa operazione è ancora più semplice:

- La superficie dell'API è diventata più estesa.
- È stata introdotta una modalità di compatibilità .NET Framework.

  Questa modalità consente a progetti .NET Standard e .NET Core di gestire riferimenti a librerie .NET Framework. Per altre informazioni sulla modalità di compatibilità, vedere [Announcing .NET Standard 2.0](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-0/) (Annuncio di .NET Standard 2.0).

È necessario usare .NET Framework solo nei casi in cui le librerie o i pacchetti NuGet usino tecnologie che non sono disponibili in .NET Standard o .NET Core.

### <a name="net-technologies-not-available-for-net-core"></a>Tecnologie .NET non disponibili per .NET Core

Esistono tecnologie di .NET Framework non disponibili in .NET Core. Alcune potrebbero essere incluse in versioni successive di .NET Core, mentre altre non si applicano ai nuovi modelli di applicazione basati su .NET Core ed è possibile che non vengano mai rese disponibili. Di seguito sono elencate le tecnologie più comuni non disponibili in .NET Core:

- Applicazioni Web Form ASP.NET: i Web Form ASP.NET sono disponibili solo in .NET Framework. di conseguenza non è possibile usare ASP.NET Core per Web Form ASP.NET. Non è inoltre previsto il trasferimento di Web Form ASP.NET in .NET Core.

- Applicazioni Pagine Web ASP.NET: Pagine Web ASP.NET non è incluso in ASP.NET Core.

- Implementazione di servizi WCF: Anche quando esiste una [libreria client WCF](https://github.com/dotnet/wcf) per l'utilizzo di servizi WCF da .NET Core, l'implementazione del server WCF è attualmente disponibile solo in .NET Framework. Questo scenario non fa parte del piano corrente per .NET Core, ma viene preso in considerazione per il futuro.

- I servizi correlati al flusso di lavoro: Windows Workflow Foundation (WF), servizi flusso di lavoro (WCF + WF in un unico servizio) e WCF Data Services (precedentemente noto come "ADO.NET Data Services") sono disponibili solo in .NET Framework. Non sono previsti piani per portare queste tecnologie a .NET Core.

- Supporto per i linguaggi: Visual Basic e F# sono attualmente supportati in .NET Core, ma non per tutti i tipi di progetto. Per un elenco dei modelli di progetto supportati, vedere le [opzioni del modello per dotnet new](../core/tools/dotnet-new.md#arguments).

### <a name="platform-doesnt-support-net-core"></a>Piattaforma non supporta .NET Core

Alcune piattaforme Microsoft o di terze parti non supportano .NET Core. Alcuni servizi di Azure offrono un SDK non ancora disponibile per l'utilizzo in .NET Core. Questa situazione è transitoria poiché tutti i servizi di Azure usano .NET Core. Nel frattempo, è possibile usare l'API REST equivalente anziché l'SDK client.

## <a name="see-also"></a>Vedere anche

- [Choose between ASP.NET and ASP.NET Core (Scegliere tra ASP.NET e ASP.NET Core)](/aspnet/core/choose-aspnet-framework)
- [ASP.NET Core per .NET Framework](/aspnet/core/introduction-to-aspnet-core#aspnet-core-targeting-net-framework)
- [Framework di destinazione](frameworks.md)
- [Guida a .NET Core](../core/index.yml)
- [Porting from .NET Framework to .NET Core](../core/porting/index.md) (Portabilità da .NET Framework a .NET Core)
- [Introduzione a .NET e Docker](../core/docker/introduction.md)
- [.NET Components Overview](components.md) (Panoramica dei componenti .NET)
- [Microservizi .NET. Architettura per le applicazioni .NET in contenitori](../architecture/microservices/index.md)
