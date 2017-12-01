---
title: Compilazione di immagini Docker per .NET Core
description: Informazioni sulle immagini Docker e su .NET Core
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>Compilazione di immagini Docker per applicazioni .NET Core

 In questa esercitazione, l'attenzione su come usare .NET Core in Docker. In primo luogo, è esplorare le immagini di Docker diverse offerte e gestiti da Microsoft e casi d'uso. È quindi come compilare e dockerize un'app di ASP.NET Core.

Nel corso di questa esercitazione, si apprenderà:
> [!div class="checklist"]
> * Informazioni sulle immagini di Microsoft .NET Core Docker 
> * Ottenere un ASP.NET Core app di esempio per Dockerize
> * Eseguire localmente l'app di esempio ASP.NET
> * Compilare ed eseguire l'esempio con Docker per i contenitori di Linux
> * Compilare ed eseguire l'esempio con i contenitori di Docker per Windows

## <a name="docker-image-optimizations"></a>Ottimizzazioni delle immagini Docker

Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione su tre scenari principali:

* Immagini usate per sviluppare app .NET Core
* Immagini usate per compilare app .NET Core
* Immagini usate per eseguire app .NET Core

Perché tre immagini?
Durante lo sviluppo, compilazione e l'esecuzione di applicazioni nei contenitori, abbiamo diverse priorità.

* **Sviluppo:** la priorità è incentrata sulla scorrere rapidamente le modifiche e la possibilità di eseguire il debug delle modifiche. Le dimensioni dell'immagine non sono importante, piuttosto possibile si apportano modifiche al codice e visualizzarli rapidamente?

* **Compilazione:** questa immagine contiene tutti gli elementi necessari per compilare l'app, che include il compilatore e delle dipendenze per ottimizzare i file binari.  Utilizzare l'immagine di compilazione per creare asset di che inserire in un'immagine di produzione. Viene utilizzata l'immagine di compilazione per l'integrazione continua o in un ambiente di compilazione. Questo approccio consente a un agente di compilazione compilare e compilare l'applicazione (con tutte le dipendenze necessarie) in un'istanza di immagine di compilazione. Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker.

* **Produzione:** la velocità con cui è possibile distribuire e avviare l'immagine? Questa immagine è piccola, pertanto le prestazioni di rete dal Registro di sistema Docker per gli host Docker sono ottimizzata. Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'esecuzione Docker e l'elaborazione dei risultati. Compilazione dinamica del codice non è necessaria nel modello di Docker. Il contenuto inserito in questa immagine sarà limitato ai file binari e al contenuto necessario per eseguire l'applicazione,

    Ad esempio, il `dotnet publish` output contiene:

    * i file binari compilati
    * file con estensione js e CSS


Il motivo per includere il `dotnet publish` output del comando in un'immagine di produzione è quello di mantenere il ' dimensioni al minimo.

Alcune immagini .NET Core condividono livelli tra tag diversi, pertanto il tag più recente di download è un processo relativamente semplice. Se si dispone di una versione precedente del computer, questa architettura consente di ridurre lo spazio su disco necessaria.

Quando più applicazioni utilizzano immagini comuni nello stesso computer, la memoria è condivisa tra le immagini più comuni. Le immagini devono essere uguali a essere condivisi.

## <a name="docker-image-variations"></a>Variazioni delle immagini Docker

Per ottenere gli obiettivi di cui sopra, forniamo varianti di immagine in [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Questa immagine contiene .NET Core SDK, che include .NET Core e gli strumenti della riga di comando (CLI). Questa immagine è mappata allo **scenario di sviluppo**. Utilizzare questa immagine per lo sviluppo locale e il debug di unit test. Questa immagine può essere usata anche per gli scenari di **compilazione**. Utilizzando `microsoft/dotnet:sdk` fornisce sempre la versione più recente.

> [!TIP]
> Se non si conosce le proprie esigenze, si desidera utilizzare il `microsoft/dotnet:<version>-sdk` immagine. Come l'immagine "fatto", è progettato per essere utilizzato come un'istruzione throw contenitore di stoccaggio montare il codice sorgente e avviare il contenitore per avviare l'app e come immagine di base per altre immagini da compilare.

* `microsoft/dotnet:<version>-runtime`: Questa immagine contiene .NET Core (runtime e librerie) ed è ottimizzata per l'esecuzione di App .NET Core in **produzione**.

## <a name="alternative-images"></a>Immagini alternative

Oltre agli scenari ottimizzati di sviluppo, compilazione e produzione, Microsoft fornisce immagini aggiuntive:

* `microsoft/dotnet:<version>-runtime-deps`: il **runtime deps** immagine contiene il sistema operativo con tutte le dipendenze native necessari per .NET Core. Questa immagine è per [applicazioni indipendente](https://docs.microsoft.com/dotnet/core/deploying/index).

Versioni più recenti di ciascuna variante:

* `microsoft/dotnet`o `microsoft/dotnet:latest` (alias per l'immagine SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Esempi per l'esplorazione

* [In questo esempio di ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) viene illustrato un modello migliore di procedure consigliate per la creazione di immagini Docker per ASP.NET Core App per la produzione. L'esempio funziona con contenitori di Linux e Windows.

* Questo esempio di .NET Core Docker viene illustrato un modello prassi migliori per [la creazione di immagini Docker per le applicazioni .NET Core per la produzione.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>La prima app di ASP.NET Core Docker

Per questa esercitazione consente di utilizzare un'applicazione di esempio ASP.NET Core Docker per l'app a cui che si desidera dockerize. Questa applicazione di esempio ASP.NET Core Docker viene illustrato un modello prassi migliori per la creazione di immagini Docker per ASP.NET Core App per la produzione. L'esempio funziona con contenitori di Linux e Windows.

L'esempio Dockerfile crea un'immagine di Docker dell'applicazione ASP.NET Core in base di fuori dell'immagine di base di ASP.NET Core Runtime Docker.

Usa il [funzionalità di compilazione in più fasi Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) per:

* compilare l'esempio in un contenitore in base il **maggiore** immagine di base di ASP.NET Core compilazione Docker 
* Copia il risultato finale di compilazione in un'immagine di Docker in base il **più piccoli** immagine di base del Runtime di ASP.NET Core Docker

> [!Note]
> L'immagine di compilazione contiene strumenti necessari per compilare applicazioni, mentre l'immagine di runtime non.

### <a name="prerequisites"></a>Prerequisiti

Per compilare ed eseguire, installare gli elementi seguenti:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

* Installare l'editor di codice preferito, se hai già fatto.

> [!TIP]
> È necessario installare un editor di codice? Provare a [Visual Studio](https://visualstudio.com/downloads)!

#### <a name="installing-docker-client"></a>L'installazione Client di Docker

Installare [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o versione successiva del client Docker.

Il client Docker può essere installato in:

* Distribuzioni di Linux

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/).

#### <a name="installing-git-for-sample-repository"></a>Installare Git per il repository di esempio

* Installare [git](https://git-scm.com/download) se si desidera clonare il repository.

### <a name="getting-the-sample-application"></a>L'applicazione di esempio

È il modo più semplice per ottenere il codice di esempio clonando la [repository di esempi](https://github.com/dotnet/dotnet-docker-samples) con git, seguendo le istruzioni seguenti: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

È anche possibile scaricare il repository (è piccolo) come un file zip dal repository di esempi di .NET Core Docker.

### <a name="run-the-aspnet-app-locally"></a>Eseguire localmente l'app ASP.NET

Come punto di riferimento, prima di inserire l'applicazione nei contenitori, eseguirla localmente.

È possibile compilare ed eseguire l'applicazione localmente con .NET Core 2.0 SDK tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd aspnetapp
dotnet run
```

Dopo l'avvio dell'applicazione, visitare **indirizzo http://localhost:5000/** nel web browser.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Compilare ed eseguire l'esempio con Docker per i contenitori di Linux

È possibile compilare ed eseguire l'esempio in Docker usando i contenitori di Linux usando i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] Il `docker run` '-p' argomento mappe porta 5000 sul computer locale alla porta 80 del contenitore (il modulo di mapping di porta è `host:container`). Per ulteriori informazioni, vedere il [docker eseguire](https://docs.docker.com/engine/reference/commandline/exec/) riferimento ai parametri della riga di comando.

Dopo l'avvio dell'applicazione, visitare **indirizzo http://localhost:5000/** nel web browser.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Compilare ed eseguire l'esempio con i contenitori di Docker per Windows

È possibile compilare ed eseguire l'esempio in Docker usando i contenitori di Windows usando i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> È necessario passare al **indirizzo IP contenitore** (in contrapposizione a http://localhost) nel browser direttamente quando si usano i contenitori di Windows. È possibile ottenere l'indirizzo IP del contenitore con i passaggi seguenti:

* Aprire il prompt dei comandi di un altro.
* Eseguire `docker ps` per visualizzare i contenitori in esecuzione. Il contenitore "aspnetcore_sample" deve essere presente.
* Eseguire `docker exec aspnetcore_sample ipconfig`.
* L'indirizzo IP di contenitore di copiare e incollare nel browser (ad esempio, 172.29.245.43).

> [!Note]
> Exec docker supporta i contenitori di identificazione con nome o hash. In questo esempio, viene utilizzato il nome (aspnetcore_sample).

Vedere l'esempio seguente di come ottenere l'indirizzo IP di un contenitore di Windows in esecuzione.

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> Exec docker viene eseguito un nuovo comando in un contenitore in esecuzione. Per ulteriori informazioni, vedere il [riferimento a docker exec](https://docs.docker.com/engine/reference/commandline/exec/) sui parametri della riga di comando.

È possibile creare un'applicazione che è possibile distribuire nell'ambiente di produzione in locale utilizzando il [dotnet pubblicare](../tools/dotnet-publish.md) comando.

```console
dotnet publish -c release -o published
```

> [!Note]
> L'argomento di versione - c compila l'applicazione in modalità di rilascio (il valore predefinito è la modalità di debug). Per ulteriori informazioni, vedere il [dotnet eseguire riferimento](../tools/dotnet-run.md) sui parametri della riga di comando.

È possibile eseguire l'applicazione in **Windows** usando il comando seguente.

```console
dotnet published\aspnetapp.dll
```

È possibile eseguire l'applicazione in **Linux** o **macOS** usando il comando seguente.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Immagini docker usate in questo esempio

Le immagini Docker seguenti vengono utilizzate in questo esempio

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

La procedura è stata completata. sono disponibili solo:
> [!div class="checklist"]
> * Sono fornite informazioni su Microsoft .NET Core Docker images
> * Ha ricevuto un ASP.NET Core app di esempio per Dockerize
> * È stata eseguita l'app di esempio ASP.NET localmente
> * Compilato ed eseguito il codice di esempio con Docker per i contenitori di Linux
> * Compilato ed eseguito il codice di esempio con i contenitori di Docker per Windows


**Passaggi successivi**

Ecco alcuni dei passaggi da eseguire:

* [Utilizzo degli strumenti di Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Distribuzione di immagini Docker dal Registro di sistema contenitore di Azure per le istanze di contenitore di Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Il debug con codice di Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Recupero mani nel con Visual Studio per Mac, contenitori e senza codice nel cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Introduzione a Docker e Visual Studio per Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> Se non si dispone di una sottoscrizione di Azure, [Iscriviti oggi stesso](https://azure.microsoft.com/free/?b=16.48) per un account gratuito di 30 giorni e get 200 dollari di crediti di Azure per provare qualsiasi combinazione di servizi di Azure.
