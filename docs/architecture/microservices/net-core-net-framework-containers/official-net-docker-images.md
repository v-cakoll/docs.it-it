---
title: Immagini Docker .NET ufficiali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Immagini Docker .NET ufficiali
ms.date: 01/30/2020
ms.openlocfilehash: 50a50587b35f811859841c4e049f40cb99479372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501873"
---
# <a name="official-net-docker-images"></a>Immagini Docker .NET ufficiali

Le immagini Docker .NET ufficiali sono immagini Docker create e ottimizzate da Microsoft. Sono disponibili pubblicamente nei repository Microsoft su [Docker Hub](https://hub.docker.com/u/microsoft/). Ogni repository può contenere più immagini, a seconda delle versioni di .NET e a seconda del sistema operativo e delle relative versioni, ad esempio Linux Debian, Linux Spline, Windows Nano Server, Windows Server Core e così via.

A partire da .NET Core 2.1, tutte le immagini .NET Core, inclusa ASP.NET <https://hub.docker.com/_/microsoft-dotnet-core/>Core, sono disponibili in Docker Hub nell'archivio immagini .NET Core: .

Da maggio 2018, le immagini Microsoft vengono [sincronizzate nel Registro](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/)di sistema contenitori Microsoft . Il catalogo ufficiale è ancora disponibile solo in Docker Hub, e lì troverai l'indirizzo aggiornato per estrarre l'immagine.

La maggior parte dei repository di immagini fornisce un tagging esteso che consente di selezionare non solo una versione specifica del framework, ma anche di scegliere un sistema operativo (distribuzione Linux o Windows).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Ottimizzazioni delle immagini .NET Core e Docker per lo sviluppo e la produzione

Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione sugli scenari principali seguenti:

- Immagini usate per *sviluppare* e compilare app .NET Core.

- Immagini usate per eseguire app .NET Core.Images used to *run* .NET Core apps.

Perché sono disponibili più immagini? Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni in contenitori, è necessario tenere conto di diverse priorità. Fornendo immagini diverse per queste attività separate, Microsoft consente di ottimizzare i processi per lo sviluppo, la compilazione e la distribuzione di app.

### <a name="during-development-and-build"></a>Durante lo sviluppo e la compilazione

Durante lo sviluppo, ciò che conta è la velocità di iterazione delle modifiche e la possibilità di eseguire il debug delle modifiche. Le dimensioni dell'immagine non sono importanti quanto la possibilità di apportare modifiche al codice e visualizzare rapidamente le modifiche. Alcuni strumenti e "contenitori agente di compilazione", utilizzano l'immagine .NET Core di sviluppo (*mcr.microsoft.com/dotnet/core/sdk:3.1*) durante il processo di sviluppo e compilazione. Quando si compila all'interno di un contenitore Docker, gli aspetti importanti sono gli elementi necessari per compilare l'app. Tra questi, il compilatore e le eventuali altre dipendenze di .NET.

Perché questo tipo di immagine di compilazione è importante? Questa immagine non viene distribuita nell'ambiente di produzione. Si tratta invece di un'immagine che si usa per creare il contenuto inserito in un'immagine di produzione. Questa immagine viene usata nell'ambiente di integrazione continua (CI) o nell'ambiente di compilazione quando si usano compilazioni a più fasi di Docker.This image would be used in your continuous integration (CI) environment or build environment when using Docker multi-stage builds.

### <a name="in-production"></a>In produzione

Ciò che conta nella produzione è quanto velocemente è possibile distribuire e avviare i contenitori basati su un'immagine .NET Core di produzione. Pertanto, l'immagine di sola runtime basata su *mcr.microsoft.com/dotnet/core/aspnet:3.1* è piccola in modo che possa viaggiare rapidamente attraverso la rete dal Registro di sistema Docker agli host Docker. Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'avvio del contenitore e l'elaborazione dei risultati. Nel modello Docker, non è necessario eseguire la compilazione dal codice C\#, come quando si eseguono i comandi dotnet build o dotnet publish con il contenitore di compilazione.

In questa immagine ottimizzata, si inseriscono solo i file binari e altro contenuto necessario per eseguire l'applicazione. Ad esempio, il `dotnet publish` contenuto creato da contiene solo i file binari .NET compilati, le immagini, i file con estensione js e css. Nel corso del tempo, si vedranno immagini contenenti pacchetti pre-JIT (la compilazione dal linguaggio intermedio al codice nativo che avviene in fase di esecuzione).

Anche se sono presenti più versioni delle immagini .NET Core e ASP.NET Core, tutte queste versioni condividono uno o più livelli, incluso il livello di base. La quantità di spazio su disco necessaria per archiviare un'immagine è quindi ridotta ed è costituita solo dal valore differenziale tra l'immagine personalizzata e l'immagine di base. Ne consegue quindi che il pull dell'immagine dal registro è veloce.

Durante l'esplorazione dei repository di immagini .NET nell'hub Docker, si troveranno più versioni delle immagini classificate o contrassegnate con tag. Questi tag consentono di decidere l'immagine da usare a seconda della versione necessaria, come quelle nella tabella seguente:

| Immagine | Commenti |
|-------|----------|
| mcr.microsoft.com/dotnet/core/aspnet:**3.1** | ASP.NET Core, con ottimizzazioni ASP.NET Core e solo runtime, in Linux e Windows (multiarchitettura) |
| mcr.microsoft.com/dotnet/core/sdk:**3.1** | .NET Core, con SDK inclusi, in Linux e Windows (multiarchitettura) |

> [!div class="step-by-step"]
> [Successivo](net-container-os-targets.md)
> [precedente](../architect-microservice-container-applications/index.md)
