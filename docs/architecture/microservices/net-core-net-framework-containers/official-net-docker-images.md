---
title: Immagini Docker .NET ufficiali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Immagini Docker .NET ufficiali
ms.date: 01/30/2020
ms.openlocfilehash: 50a50587b35f811859841c4e049f40cb99479372
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501873"
---
# <a name="official-net-docker-images"></a>Immagini Docker .NET ufficiali

Le immagini Docker .NET ufficiali sono immagini Docker create e ottimizzate da Microsoft. Sono disponibili pubblicamente nei repository Microsoft nell'[hub Docker](https://hub.docker.com/u/microsoft/). Ogni repository può contenere più immagini, a seconda delle versioni di .NET e a seconda del sistema operativo e delle relative versioni, ad esempio Linux Debian, Linux Spline, Windows Nano Server, Windows Server Core e così via.

Dal momento che .NET Core 2,1, tutte le immagini .NET Core, incluse per ASP.NET Core sono disponibili nell'hub Docker nel repository di immagini .NET Core: <https://hub.docker.com/_/microsoft-dotnet-core/>.

Dal 2018 maggio, le immagini Microsoft vengono comunicate [nel container Registry Microsoft](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/). Il catalogo ufficiale è ancora disponibile solo nell'hub Docker ed è disponibile l'indirizzo aggiornato per eseguire il pull dell'immagine.

La maggior parte dei repository di immagini fornisce tag completi che consentono di selezionare non solo una versione specifica del Framework, ma anche di scegliere un sistema operativo (distribuzione Linux o versione di Windows).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Ottimizzazioni delle immagini .NET Core e Docker per lo sviluppo e la produzione

Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione sugli scenari principali seguenti:

- Immagini usate per *sviluppare* e compilare app .NET Core.

- Immagini usate per *eseguire* app .NET Core.

Perché sono disponibili più immagini? Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni in contenitori, è necessario tenere conto di diverse priorità. Fornendo immagini diverse per queste attività separate, Microsoft consente di ottimizzare i processi per lo sviluppo, la compilazione e la distribuzione di app.

### <a name="during-development-and-build"></a>Durante lo sviluppo e la compilazione

Durante lo sviluppo, ciò che conta è la velocità di iterazione delle modifiche e la possibilità di eseguire il debug delle modifiche. Le dimensioni dell'immagine non sono importanti come la possibilità di apportare modifiche al codice e visualizzare rapidamente le modifiche. Alcuni strumenti e i "contenitori dell'agente di compilazione" usano l'immagine .NET Core di sviluppo (*MCR.Microsoft.com/dotnet/Core/SDK:3.1*) durante il processo di sviluppo e compilazione. Quando si compila in un contenitore Docker, gli aspetti importanti sono gli elementi necessari per compilare l'app. Tra questi, il compilatore e le eventuali altre dipendenze di .NET.

Perché questo tipo di immagine di compilazione è importante? Questa immagine non viene distribuita nell'ambiente di produzione. Si tratta invece di un'immagine usata per compilare il contenuto inserito in un'immagine di produzione. Questa immagine verrà usata nell'ambiente di integrazione continua (CI) o nell'ambiente di compilazione quando si usano le compilazioni in più fasi di Docker.

### <a name="in-production"></a>In produzione

Ciò che conta nella produzione è quanto velocemente è possibile distribuire e avviare i contenitori basati su un'immagine .NET Core di produzione. Di conseguenza, l'immagine solo di runtime basata su *MCR.Microsoft.com/dotnet/Core/ASPNET:3.1* è ridotta, in modo che possa viaggiare rapidamente attraverso la rete dal registro Docker agli host docker. Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'avvio del contenitore e l'elaborazione dei risultati. Nel modello Docker, non è necessario eseguire la compilazione dal codice C\#, come quando si eseguono i comandi dotnet build o dotnet publish con il contenitore di compilazione.

In questa immagine ottimizzata vengono inseriti solo i file binari e altri contenuti necessari per eseguire l'applicazione. Ad esempio, il contenuto creato da `dotnet publish` contiene solo i file binari .NET, le immagini, i file con estensione js e CSS compilati. Nel corso del tempo, si vedranno immagini contenenti pacchetti pre-JIT (la compilazione dal linguaggio intermedio al codice nativo che avviene in fase di esecuzione).

Anche se sono presenti più versioni delle immagini .NET Core e ASP.NET Core, tutte queste versioni condividono uno o più livelli, incluso il livello di base. La quantità di spazio su disco necessaria per archiviare un'immagine è quindi ridotta ed è costituita solo dal valore differenziale tra l'immagine personalizzata e l'immagine di base. Ne consegue quindi che il pull dell'immagine dal registro è veloce.

Durante l'esplorazione dei repository di immagini .NET nell'hub Docker, si troveranno più versioni delle immagini classificate o contrassegnate con tag. Questi tag consentono di decidere l'immagine da usare a seconda della versione necessaria, come quelle nella tabella seguente:

| Immagine | Comments |
|-------|----------|
| mcr.microsoft.com/dotnet/core/aspnet:**3,1** | ASP.NET Core, con ottimizzazioni ASP.NET Core e solo runtime, in Linux e Windows (multiarchitettura) |
| mcr.microsoft.com/dotnet/core/sdk:**3,1** | .NET Core, con SDK inclusi, in Linux e Windows (multiarchitettura) |

> [!div class="step-by-step"]
> [Precedente](net-container-os-targets.md)
> [Successivo](../architect-microservice-container-applications/index.md)
