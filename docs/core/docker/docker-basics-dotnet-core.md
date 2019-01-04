---
title: Distribuire un'app in un contenitore con Docker
description: Questa esercitazione illustra come creare un'applicazione .NET Core di base e come distribuirla in un contenitore con Docker.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: eed72553576f4154fe63b2e5cf035a781afe4b7c
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169586"
---
# <a name="how-to-containerize-a-net-core-application"></a>Come distribuire un'applicazione .NET Core in un contenitore

Questa esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core. La [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare e creare pacchetti rapidamente per le app come [immagini Docker](https://docs.docker.com/glossary/?term=image). Queste immagini vengono scritte nel formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) per la distribuzione e l'esecuzione in un [contenitore su più livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Nel corso di questa esercitazione verranno illustrate le attività seguenti:

> [!div class="checklist"]
> * Come creare un Dockerfile
> * Come creare un'app .NET Core.
> * Come distribuire l'app in un contenitore Docker.

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: il modo più semplice per iniziare

Prima di creare l'immagine Docker è necessaria un'applicazione da aggiungere a un contenitore. È possibile crearla in Linux, MacOS o Windows. Il modo più veloce e semplice per farlo consiste nell'usare .NET Core.

Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).

È possibile compilare sia contenitori Windiws che Linux con [tag basati su più architetture](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>La prima app Docker .NET Core

### <a name="prerequisites"></a>Prerequisiti

Per completare questa esercitazione:

#### <a name="net-core-sdk"></a>.NET Core SDK

* Installare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) o versione successiva.

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.1., le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.1. Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 - Versioni di sistemi operativi supportate).

* Installare l'editor del codice preferito, se non è già disponibile.

> [!TIP]
> È necessario installare un editor del codice? Provare [Visual Studio Code](https://code.visualstudio.com/download).

#### <a name="installing-docker-client"></a>Installazione del client di Docker

Installare [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) o una versione successiva del client di Docker.

Il client di Docker può essere installato in:

* Distribuzioni di Linux

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/).

### <a name="create-a-net-core-21-console-app-for-dockerization"></a>Creare un'app console .NET Core 2.1 per il contenitore Docker

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
   * Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione. In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per i framework specificati in un'unica operazione. In questa esercitazione, la destinazione di compilazione è .NET Core 2.1.

   `Program.cs`:

   Il programma inizia con `using System`. Questa istruzione significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file". Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.

   Viene quindi definito uno spazio dei nomi denominato `Hello`. È comunque possibile modificare lo spazio dei nomi secondo le proprie esigenze. All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe. Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato. In questo esempio, il programma scrive solo "Hello World!" nella console.

   **dotnet new** esegue il comando [`dotnet restore`](../tools/dotnet-restore.md). **Dotnet restore** ripristina l'albero delle dipendenze con una chiamata [NuGet](https://www.nuget.org/) (gestione pacchetti .NET).
   NuGet esegue le attività seguenti:
   * Analizza il file *Hello.csproj*.
   * Scarica le dipendenze del file (o le recupera dalla cache del computer).
   * Scrive il file *obj/project.assets.json*.

   Il file *project.assets.json* è un set completo delle grafico delle dipendenze di NuGet, delle risoluzioni dei binding e di altri metadati dell'app. Questo file obbligatorio viene usato da altri strumenti, ad esempio [`dotnet build`](../tools/dotnet-build.md) e [`dotnet run`](../tools/dotnet-run.md), per elaborare correttamente il codice sorgente.

2. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per verificare che la compilazione sia corretta e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione.

    ```console
    $ dotnet run

    Hello World!
    ```

    Per scenari avanzati, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md) per altri dettagli.

## <a name="dockerize-the-net-core-application"></a>Usare i contenitori Docker per l'applicazione .NET Core

L'app console .NET Core Hello viene eseguita correttamente in locale. A questo punto è possibile procedere e compilare ed eseguire l'app in Docker.

### <a name="your-first-dockerfile"></a>Il primo Dockerfile

Per iniziare, aprire l'editor di testo. Si lavorerà ancora dalla directory Hello in cui è stata compilata l'app.

Aggiungere le istruzioni seguenti di Docker per i contenitori Linux o i [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) in un nuovo file. Al termine, salvarlo nella radice della directory Hello come **Dockerfile**, senza estensione (potrebbe essere necessario impostare il tipo di file su `All types (*.*)` o un valore analogo).

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Il Dockerfile contiene istruzioni per la compilazione di Docker eseguite in sequenza.

La prima istruzione deve essere [**FROM**](https://docs.docker.com/engine/reference/builder/#from). Questa istruzione inizializza una nuova fase di compilazione e imposta l'immagine di base per le istruzioni rimanenti. I tag basati su più architetture eseguono il pull dei contenitori Windows o Linux a seconda della [modalità contenitore](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) di Docker per Windows. L'immagine di base per l'esempio è l'immagine 2.1-sdk dal repository microsoft/dotnet:

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

L'istruzione [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) imposta la directory di lavoro per eventuali istruzioni Dockerfile RUN, CMD, ENTRYPOINT, COPY e ADD rimanenti. Se la directory non esiste, viene creata. In questo caso, WORKDIR viene impostata sulla directory dell'app.

```Dockerfile
WORKDIR /app
```

L'istruzione [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia i nuovi file o le nuove directory dal percorso di origine e li aggiunge al file system del contenitore di destinazione. Con questa istruzione, il file di progetto C# viene copiato nel contenitore.

```Dockerfile
COPY *.csproj ./
```

L'istruzione [**RUN**](https://docs.docker.com/engine/reference/builder/#run) esegue qualsiasi comando in un nuovo livello sopra l'immagine corrente ed esegue il commit dei risultati. L'immagine risultante viene usata nel passaggio successivo nel Dockerfile. Viene eseguito il comando **dotnet restore** per ottenere le dipendenze necessarie del file di progetto C#. 

```Dockerfile
RUN dotnet restore
```

L'istruzione **COPY** copia il resto dei file nel contenitore in nuovi [livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

L'app viene pubblicata con questa istruzione **RUN**. Il comando [**dotnet publish**](../tools/dotnet-publish.md) compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory. L'app viene pubblicata con la configurazione **Versione** e l'output collocato nella directory predefinita.

```Dockerfile
RUN dotnet publish -c Release -o out
```

L'istruzione [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) consente di eseguire il contenitore come eseguibile.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

È ora disponibile un Dockerfile che:

* Copia l'app nell'immagine
* Include le dipendenze dell'app nell'immagine
* Compila l'app per l'esecuzione come eseguibile

### <a name="build-and-run-the-hello-net-core-app"></a>Compilare ed eseguire l'app .NET Core Hello

#### <a name="essential-docker-commands"></a>Comandi Docker essenziali

Questi comandi Docker sono essenziali:

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Compilare ed eseguire

Dopo aver scritto il Dockerfile, Docker ora compila l'app e quindi esegue il contenitore.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

L'output del comando `docker build` dovrebbe essere simile all'output della console seguente:

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

Come si vede dall'output, il motore Docker ha usato il Dockerfile per creare il contenitore.

L'output del comando `docker run` dovrebbe essere simile all'output della console seguente:

```console
Hello World!
```

La procedura è stata completata. Sono state eseguite le attività seguenti:
> [!div class="checklist"]
> * Creazione di un'app .NET Core locale
> * Creazione di un Dockerfile per creare il primo contenitore
> * Compilazione ed esecuzione dell'app nel contenitore Docker

## <a name="next-steps"></a>Passaggi successivi

Ecco alcuni dei possibili argomenti con cui proseguire:

* [Video introduttivo alle immagini Docker .NET](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker &amp; Azure Container Instances better together!](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae) (I vantaggi dell'integrazione di Visual Studio, Docker e Istanze di Azure Container)
* [Guide introduttive per Docker per Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Deploy your app on Docker for Azure](https://docs.docker.com/docker-for-azure/deploy/) (Distribuire l'app in Docker per Azure)

> [!Note]
> Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.

## <a name="docker-images-used-in-this-sample"></a>Immagini Docker usate in questo esempio

In questo esempio vengono usate le immagini Docker seguenti

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Risorse correlate

* [Esempi di Docker per .NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [Dockerfile on Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile) (Dockerfile in contenitori Windows)
* [Esempi di Docker per .NET Framework](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/) (ASP.NET Core in DockerHub)
* [Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/) (Usare i contenitori Docker per un'applicazione .NET Core) - Esercitazione per Docker
* [Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro Azure Container a Istanze di Azure Container)