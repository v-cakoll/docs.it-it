---
title: Nozioni di Docker con .NET Core
description: Un Docker e l'esercitazione di base di .NET Core
keywords: .NET, .NET core, Docker, esercitazione
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
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>Nozioni di Docker con .NET Core

In questa esercitazione Docker contenitore compilare e distribuire le attività per un'applicazione .NET Core. Nel corso di questa esercitazione, si apprenderà:

> [!div class="checklist"]
> * Come creare un Dockerfile
> * Come creare un'applicazione .NET Core.
> * Come distribuire l'app in un contenitore Docker.

Il [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utilizza il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare rapidamente e pacchetti di applicazioni di esempio [immagini Docker](https://docs.docker.com/glossary/?term=image). Queste immagini vengono scritti [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) formato per essere distribuito ed eseguito un [a più livelli contenitore](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

## <a name="net-core-easiest-way-to-get-started"></a>.NET core: Il modo più semplice per iniziare

Prima di creare l'immagine di Docker, è necessario disporre di un'applicazione a inserita in un contenitore. È possibile crearlo in Linux, MacOS o Windows. Il modo più rapido e semplice per eseguire questa operazione consiste nell'utilizzare .NET Core.

Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).

È possibile creare contenitori di Windows e Linux con [multi-arch basati su tag](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>La prima app .NET Core Docker

### <a name="prerequisites"></a>Prerequisiti

Per completare questa esercitazione:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

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

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Creare un'applicazione console .NET Core 2.0 per Dockerization

Aprire un prompt dei comandi e creare una cartella denominata *Hello*. Passare alla cartella creata e digitare i comandi seguenti:

```console
dotnet new console
dotnet run
```

Ecco una descrizione rapida dei comandi digitati:

1. `$ dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.  Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.
   
   `Hello.csproj`:

   Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.

   * Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.
   * Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione. In uno scenario avanzato, è possibile specificare più Framework di destinazione e per i Framework specificati in una singola operazione di compilazione. In questa esercitazione, si compila per Core .NET 2.0.

   `Program.cs`:

   Il programma viene avviato da `using System`. Questa istruzione indica, "importare tutti gli elementi il `System` dello spazio dei nomi nell'ambito di questo file." Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.

   Viene quindi definito uno spazio dei nomi denominato `Hello`. È possibile modificare lo spazio dei nomi per immettere le informazioni desiderate. All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe. Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato. In questo esempio, il programma scrive solo "Hello World!" nella console.

2. `$ dotnet restore`

   In .NET Core 2. x, **dotnet nuovo** viene eseguito il [ `dotnet restore` ](../tools/dotnet-restore.md) comando. **Ripristino dotnet** Ripristina l'albero delle dipendenze con un [NuGet](https://www.nuget.org/)chiamata (gestione di pacchetti .NET).
   NuGet esegue le attività seguenti:
   * Analizza il *Hello.csproj* file 
   * Scarica il file delle dipendenze (o acrobazie dalla cache del computer)
   * Scrive il *obj/project.assets.json* file

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   Il *project.assets.json* file è un set completo di grafico di dipendenze di NuGet, associazione risoluzioni e altri metadati dell'app. Questa richiesta di file è utilizzato da altri strumenti, ad esempio [ `dotnet build` ](../tools/dotnet-build.md) e [ `dotnet run` ](../tools/dotnet-run.md), elaborare correttamente il codice sorgente.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)chiamate [ `dotnet build` ](../tools/dotnet-build.md) per verificare una compilazione corretta, quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    Per gli scenari avanzati, vedere [distribuzione dell'applicazione .NET Core](../deploying/index.md) per informazioni dettagliate.

## <a name="dockerize-the-net-core-application"></a>Dockerize l'applicazione .NET Core

L'applicazione console Hello .NET Core viene eseguito correttamente in locale. Ora si fare un passo ulteriormente e di compilare ed eseguire l'app in Docker.

### <a name="your-first-dockerfile"></a>Il primo Dockerfile

Aprire l'editor di testo ed è possibile iniziare subito! Stiamo ancora lavorando dalla directory Hello in che è compilata l'app.

Aggiungere le seguenti istruzioni di Docker per entrambi Linux o [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) in un nuovo file. Al termine, salvarlo nella radice della directory Hello come **Dockerfile**, senza estensione (potrebbe essere necessario impostare il tipo di file `All types (*.*)` o simile).

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile contiene le istruzioni di compilazione Docker che vengono eseguiti in sequenza.

La prima istruzione deve essere [ **FROM**](https://docs.docker.com/engine/reference/builder/#from). Questa istruzione consente di inizializzare una nuova fase di compilazione e imposta l'immagine di Base per le istruzioni rimanenti. I tag più arch pull contenitori di Windows o Linux a seconda di Docker per Windows [modalità contenitore](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers). L'immagine di Base per l'esempio è l'immagine di 2.0 sdk dal repository, microsoft/dotnet

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

Il [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) istruzione imposta la directory di lavoro per eseguire rimanenti, CMD, il punto di ingresso, copia e Aggiungi Dockerfile istruzioni. Se la directory non esiste, viene creato. In questo caso, WORKDIR è impostata per la directory dell'applicazione.

```Dockerfile
WORKDIR /app
```

Il [ **copia** ](https://docs.docker.com/engine/reference/builder/#copy) istruzione consente di copiare nuovi file o directory dal percorso di origine e li aggiunge al file System di contenitore di destinazione. Con questa istruzione, viene copiato il file di progetto c# per il contenitore.

```Dockerfile
COPY *.csproj ./
```

Il [ **eseguire** ](https://docs.docker.com/engine/reference/builder/#run) istruzione esegue i comandi in un nuovo livello nella parte superiore dell'immagine corrente ed eseguire il commit dei risultati. L'immagine di commit risultante viene utilizzato per il passaggio successivo nel documento Dockerfile. È in esecuzione **dotnet ripristino** per acquisire le dipendenze necessarie del file di progetto c#. 

```Dockerfile
RUN dotnet restore
```

Questo **copia** istruzione copia il resto dei file in questo contenitore in nuovi [livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Si sta pubblicando l'app con questo **eseguire** (istruzione). Il [ **dotnet pubblicare** ](../tools/dotnet-publish.md) comando compila l'applicazione, legge le dipendenze specificate nel file di progetto e pubblica il set di file in una directory. L'app viene pubblicato con un **versione** configurazione e l'output nella directory predefinita.

```Dockerfile
RUN dotnet publish -c Release -o out
```

Il [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) istruzione consente al contenitore per l'esecuzione come eseguibile.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Ora si dispone di un Dockerfile che:

* Copia l'immagine dell'app
* dipendenze dell'applicazione per l'immagine
* Compila l'app per l'esecuzione come eseguibile

### <a name="build-and-run-the-hello-net-core-20-app"></a>Compilare ed eseguire l'applicazione Hello .NET Core 2.0

#### <a name="essential-docker-commands"></a>Comandi di Docker essenziali

Questi comandi di Docker sono essenziali:

* [compilazione docker](https://docs.docker.com/engine/reference/commandline/build/)
* [esecuzione di docker](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [arresto di docker](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [rmi docker](https://docs.docker.com/engine/reference/commandline/rmi/)
* [immagine di docker](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Compilare ed eseguire

È stato scritto il dockerfile; ora Docker compila l'app e quindi esegue il contenitore.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

L'output di `docker build` comando dovrebbe essere simile al seguente output di console:

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

Come si vede dall'output, il motore Docker usati Dockerfile per creare il contenitore.

L'output di `docker run` comando dovrebbe essere simile al seguente output di console:

```console
Hello World!
```

La procedura è stata completata. sono disponibili solo:
> [!div class="checklist"]
> * Ha creato un'applicazione .NET Core locale
> * Creare un Dockerfile per creare il primo contenitore
> * Compilato ed eseguito l'app Dockerized



## <a name="next-steps"></a>Passaggi successivi

Ecco alcuni dei passaggi da eseguire:

* [Introduzione a .NET Docker immagini Video](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker e istanze di contenitori Azure meglio insieme!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Docker per la Guida introduttiva di Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Distribuire l'app in Docker per Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Se non si dispone di una sottoscrizione di Azure, [Iscriviti oggi stesso](https://azure.microsoft.com/free/?b=16.48) per un account gratuito di 30 giorni e get 200 dollari di crediti di Azure per provare qualsiasi combinazione di servizi di Azure.

## <a name="docker-images-used-in-this-sample"></a>Immagini docker usate in questo esempio

Le immagini Docker seguenti vengono utilizzate in questo esempio

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Risorse correlate

* [Esempi di .NET core Docker](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Dockerfile in contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Esempi di .NET framework Docker](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core in cui DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Un'applicazione .NET Core - esercitazione Docker dockerize](https://docs.docker.com/engine/examples/dotnetcore/)
* [Utilizzo degli strumenti di Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Distribuzione di immagini Docker dal Registro di sistema contenitore di Azure per le istanze di contenitore di Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)