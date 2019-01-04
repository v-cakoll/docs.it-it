---
title: Panoramica delle immagini Docker
description: Informazioni su come usare le immagini Docker per .NET Core pubblicate dal registro Docker. Si apprenderà anche come eseguire il pull delle immagini e compilare immagini personalizzate.
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: dd8c6c500dc2177768e6cba0c1e303950e20d4f3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656037"
---
# <a name="learn-about-docker-images-for-net-core"></a>Informazioni sulle immagini Docker per .NET Core

Questa esercitazione è incentrata su come usare .NET Core in Docker. Vengono prima di tutto presentati le diverse immagini Docker offerte e gestite da Microsoft e i casi d'uso. Verranno poi descritte le procedure per compilare un'app di ASP.NET Core e inserirla in un contenitore Docker.

Nel corso di questa esercitazione verranno illustrate le attività seguenti:
> [!div class="checklist"]
> * Informazioni sulle immagini Docker per Microsoft .NET Core 
> * Ottenere un'app di esempio ASP.NET Core da inserire in un contenitore Docker
> * Eseguire localmente l'app di esempio ASP.NET
> * Compilare ed eseguire l'esempio con Docker per i contenitori Linux
> * Compilare ed eseguire l'esempio con Docker per i contenitori Windows

## <a name="docker-image-optimizations"></a>Ottimizzazioni delle immagini Docker

Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione su tre scenari principali:

* Immagini usate per sviluppare app .NET Core
* Immagini usate per compilare app .NET Core
* Immagini usate per eseguire app .NET Core

Perché tre immagini?
Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni nei contenitori, è necessario tenere conto di diverse priorità.

* **Sviluppo:**  le priorità sono la velocità di iterazione delle modifiche e la possibilità di eseguirne il debug. Le dimensioni dell'immagine non sono essenziali, mentre è importante la possibilità di apportare modifiche al codice e visualizzare rapidamente tali modifiche.

* **Compilazione:** questa immagine contiene tutti gli elementi necessari per compilare l'app, inclusi il compilatore ed eventuali altre dipendenze per ottimizzare i file binari.  L'immagine di compilazione viene usata per creare gli asset da includere in un'immagine di produzione. Questa immagine verrà usata per l'integrazione continuativa o in un ambiente di compilazione. Questo approccio consente a un agente di compilazione di compilare l'applicazione (con tutte le dipendenze necessarie) in un'istanza dell'immagine di compilazione. Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker.

* **Produzione:** con quale velocità è possibile distribuire e avviare l'immagine? Questa immagine ha dimensioni ridotte, quindi le prestazioni di rete dal registro Docker agli host Docker sono ottimizzate. Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'esecuzione Docker e l'elaborazione dei risultati. La compilazione dinamica del codice non è necessaria nel modello di Docker. Il contenuto inserito in questa immagine sarà limitato ai file binari e al contenuto necessario per eseguire l'applicazione,

    Ad esempio, l'output `dotnet publish` contiene:

    * i file binari compilati
    * i file con estensione js e css


Il motivo per includere l'output del comando `dotnet publish` nell'immagine di produzione è mantenerne il più possibile ridotte le dimensioni.

Alcune immagini .NET Core condividono i livelli tra tag diversi, quindi il download del tag più recente è un processo relativamente leggero. Se è già disponibile una versione precedente nel computer in uso, questa architettura consente di ridurre lo spazio su disco necessario.

Quando più applicazioni usano immagini comuni nello stesso computer, la memoria viene condivisa tra le immagini comuni. Le immagini devono essere uguali per essere condivise.

## <a name="docker-image-variations"></a>Variazioni delle immagini Docker

Per raggiungere gli obiettivi sopra descritti, in [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) sono disponibili varianti delle immagini.

* `microsoft/dotnet:<version>-sdk` (`microsoft/dotnet:2.1-sdk`). Questa immagine contiene .NET Core SDK che include gli strumenti .NET Core e quelli dell'interfaccia della riga di comando. Questa immagine è mappata allo **scenario di sviluppo**. Usare questa immagine per operazioni locali di sviluppo, debug e testing unità. Questa immagine può essere usata anche per gli scenari di **compilazione**. L'uso di `microsoft/dotnet:sdk` consente di ottenere sempre la versione più recente.

> [!TIP]
> In caso di dubbi sulle effettive esigenze, è possibile usare l'immagine `microsoft/dotnet:<version>-sdk`. In quanto immagine "de facto", è progettata per l'uso come contenitore provvisorio (montare il codice sorgente e avviare il contenitore per avviare l'app) e come immagine di base da cui compilare altre immagini.

* `microsoft/dotnet:<version>-runtime`: questa immagine contiene .NET Core (runtime e librerie) ed è ottimizzata per l'esecuzione di app .NET Core in **produzione**.

## <a name="alternative-images"></a>Immagini alternative

Oltre agli scenari ottimizzati di sviluppo, compilazione e produzione, Microsoft fornisce immagini aggiuntive:

* `microsoft/dotnet:<version>-runtime-deps`: l'immagine **runtime-deps** contiene il sistema operativo con tutte le dipendenze native richieste da .NET Core. Questa immagine è per [applicazioni indipendenti](../deploying/index.md).

Versioni più recenti di ciascuna variante:

* `microsoft/dotnet` o `microsoft/dotnet:latest` (alias per l'immagine SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Esempi da esplorare

* [Questo esempio di Docker per ASP.NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) illustra un modello di procedura consigliata per la compilazione di immagini Docker per app ASP.NET Core per la produzione. L'esempio usa contenitori sia Linux che Windows.

* Questo esempio di Docker per .NET Core illustra un modello di procedura consigliata per la [compilazione di immagini Docker per app .NET Core per la produzione](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp).

## <a name="forward-the-request-scheme-and-original-ip-address"></a>Trasferire lo schema di richiesta e l'indirizzo IP originale

Server proxy, servizi di bilanciamento del carico e altre appliance di rete spesso nascondono informazioni su una richiesta prima che questa raggiunga l'app nel contenitore:

* Quando le richieste HTTPS vengono trasmesse tramite proxy su HTTP, lo schema originale (HTTPS) viene perso e deve essere inoltrato in un'intestazione.
* Poiché un'app riceve una richiesta dal proxy e non dall'effettiva origine su Internet o nella rete aziendale, anche l'indirizzo IP originale del client deve essere inoltrato in un'intestazione.

Queste informazioni potrebbero essere importanti per l'elaborazione delle richieste, ad esempio per i reindirizzamenti, l'autenticazione, la generazione di collegamenti, la valutazione dei criteri e la georilevazione dei client.

Per trasferire lo schema e l'indirizzo IP originale a un'app ASP.NET Core presente in un contenitore, usare il middleware delle intestazioni inoltrate. Per altre informazioni, vedere [Configurare ASP.NET Core per l'utilizzo di server proxy e servizi di bilanciamento del carico](/aspnet/core/host-and-deploy/proxy-load-balancer).

## <a name="your-first-aspnet-core-docker-app"></a>La prima app Docker ASP.NET Core

In questa esercitazione verrà usata l'applicazione di esempio Docker per ASP.NET Core per l'app da inserire in un contenitore Docker. Questa applicazione di esempio Docker per ASP.NET Core illustra un modello di procedura consigliata per la compilazione di immagini Docker per app ASP.NET Core per la produzione. L'esempio usa contenitori sia Linux che Windows.

Il Dockerfile di esempio crea un'immagine Docker dell'applicazione ASP.NET Core in base all'immagine di base Docker di ASP.NET Core Runtime.

Usa la [funzionalità di compilazione in più fasi di Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) per:

* Compilare l'esempio in un contenitore in base all'immagine di base Docker di compilazione per ASP.NET Core **più grande** 
* Copia il risultato finale di compilazione in un'immagine Docker in base all'immagine di base di runtime Docker per ASP.NET Core **più piccola**

> [!NOTE]
> L'immagine di compilazione contiene gli strumenti necessari per compilare applicazioni, diversamente dall'immagine di runtime.

### <a name="prerequisites"></a>Prerequisiti

Per compilare ed eseguire, installare gli elementi seguenti:

#### <a name="net-core-21-sdk"></a>.NET Core 2.1 SDK

* Installare [.NET Core 2.1 SDK](https://www.microsoft.com/net/core).

* Installare l'editor del codice preferito, se non è già disponibile.

> [!TIP]
> È necessario installare un editor del codice? Provare [Visual Studio](https://visualstudio.com/downloads).

#### <a name="installing-docker-client"></a>Installazione del client di Docker

Installare [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) o una versione successiva del client di Docker.

Il client di Docker può essere installato in:

* Distribuzioni di Linux

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/).

#### <a name="installing-git-for-sample-repository"></a>Installazione di Git per il repository degli esempi

* Installare [Git](https://git-scm.com/download) se si desidera clonare il repository.

### <a name="getting-the-sample-application"></a>Ottenere l'applicazione di esempio

Il modo più semplice per ottenere l'esempio è clonando il [repository Docker di .NET Core](https://github.com/dotnet/dotnet-docker) con Git, seguendo le istruzioni seguenti: 

```console
git clone https://github.com/dotnet/dotnet-docker
```

È anche possibile scaricare il repository (che ha dimensioni contenute) come file zip dal repository Docker di .NET Core.

### <a name="run-the-aspnet-app-locally"></a>Eseguire localmente l'app ASP.NET

Come punto di riferimento, prima di inserire l'applicazione nei contenitori, eseguirla localmente.

È possibile compilare ed eseguire l'applicazione in locale con .NET Core 2.1 SDK tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

Dopo l'avvio dell'applicazione, visitare **http://localhost:5000** nel Web browser.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Compilare ed eseguire l'esempio con Docker per i contenitori Linux

È possibile compilare ed eseguire l'esempio in Docker usando contenitori Linux tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> L'argomento `docker run` '-p' mappa la porta 5000 nel computer locale alla porta 80 nel contenitore (il formato per il mapping delle porte è `host:container`). Per altre informazioni, vedere le informazioni di riferimento su [docker run](https://docs.docker.com/engine/reference/commandline/exec/) per i parametri della riga di comando.

Dopo l'avvio dell'applicazione, visitare **http://localhost:5000** nel Web browser.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Compilare ed eseguire l'esempio con Docker per i contenitori Windows

È possibile compilare ed eseguire l'esempio in Docker usando contenitori Windows tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> È necessario passare direttamente all'**indirizzo IP del contenitore** (in contrapposizione a `http://localhost`) nel browser quando si usano contenitori Windows. È possibile ottenere l'indirizzo IP del contenitore con i passaggi seguenti:

* Aprire un altro prompt dei comandi.
* Eseguire `docker ps` per visualizzare i contenitori in esecuzione. Deve essere presente il contenitore "aspnetcore_sample".
* Eseguire `docker exec aspnetcore_sample ipconfig`.
* Copiare l'indirizzo IP del contenitore e incollarlo nel browser (ad esempio, 172.29.245.43).

> [!NOTE]
> Il comando docker exec supporta l'identificazione dei contenitori in base al nome o all'hash. In questo esempio, viene usato il nome (aspnetcore_sample).

Vedere l'esempio seguente su come ottenere l'indirizzo IP di un contenitore Windows in esecuzione.

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

> [!NOTE]
> Il comando docker exec esegue un nuovo comando in un contenitore in esecuzione. Per altre informazioni, vedere le informazioni di riferimento su [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) per i parametri della riga di comando.

È possibile creare un'applicazione pronta per la distribuzione nell'ambiente di produzione in locale usando il comando [dotnet publish](../tools/dotnet-publish.md).

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> L'argomento - c Release compila l'applicazione in modalità di versione (l'impostazione predefinita è la modalità di debug). Per altre informazioni, vedere le informazioni di riferimento su [dotnet run](../tools/dotnet-run.md) per i parametri della riga di comando.

È possibile eseguire l'applicazione in **Windows** usando il comando seguente.

```console
dotnet published\aspnetapp.dll
```

È possibile eseguire l'applicazione in **Linux** o **macOS** usando il comando seguente.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Immagini Docker usate in questo esempio

In questo dockerfile di esempio vengono usate le immagini Docker seguenti.

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

La procedura è stata completata. Sono state eseguite le attività seguenti:
> [!div class="checklist"]
> * Raccolta di informazioni sulle immagini Docker per Microsoft .NET Core
> * Recupero di un'app di esempio ASP.NET Core da inserire in un contenitore Docker
> * Esecuzione locale dell'app di esempio ASP.NET
> * Compilazione ed esecuzione dell'esempio con Docker per i contenitori Linux
> * Compilazione ed esecuzione dell'esempio con Docker per i contenitori Windows

**Passaggi successivi**

Ecco alcuni dei possibili argomenti con cui proseguire:

* [Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro Azure Container a Istanze di Azure Container)
* [Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) (Debug con Visual Studio Code) 
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Informazioni su Visual Studio per Mac, contenitori e codice senza server nel cloud)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Lab introduttivo per Docker e Visual Studio per Mac)

> [!NOTE]
> Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.
