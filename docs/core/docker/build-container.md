---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core con Docker.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5e6648539af45f3ce615bfc183e6f95a62b085a
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200028"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Esercitazione: distribuire un'app .NET Core

In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core con Docker. I contenitori offrono numerose funzionalità e vantaggi, ad esempio un'infrastruttura non modificabile, un'architettura portatile e l'abilitazione della scalabilità. L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.

In questa esercitazione:

> [!div class="checklist"]
>
> - Creare e pubblicare un'app .NET Core semplice
> - Creare e configurare un Dockerfile per .NET Core
> - Creare un'immagine Docker
> - Creare ed eseguire un contenitore Docker

L'esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core. La *piattaforma Docker* usa il *motore Docker* per compilare e creare pacchetti di app in modo rapido come *Immagini Docker*. Queste immagini vengono scritte nel formato *Dockerfile* per la distribuzione e l'esecuzione in un contenitore su più livelli.

> [!NOTE]
> Questa esercitazione **non è** destinata alle app ASP.NET Core. Se si usa ASP.NET Core, vedere l'esercitazione [informazioni su come distribuire un'applicazione ASP.NET Core](/aspnet/core/host-and-deploy/docker/building-net-docker-images) .

## <a name="prerequisites"></a>Prerequisiti

Installare i prerequisiti seguenti:

- [SDK di .NET Core 3,1](https://dotnet.microsoft.com/download)\
Se .NET Core è già installato, usare il comando `dotnet --info` per determinare quale SDK è in uso.
- [Docker Community Edition](https://www.docker.com/products/docker-desktop)
- Una cartella di lavoro temporanea per il *Dockerfile* e l'app .NET Core di esempio. In questa esercitazione il nome *Docker-working* viene usato come cartella di lavoro.

## <a name="create-net-core-app"></a>Creare un'app .NET Core

È necessario creare un'app .NET Core che verrà eseguita dal contenitore Docker. Aprire il terminale in uso, creare una cartella di lavoro se non è già stata creata e passare alla cartella. Nella cartella di lavoro, eseguire il comando seguente per creare un nuovo progetto in una sottodirectory denominata *app*:

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

La struttura di cartelle sarà simile all'esempio seguente:

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

Il `dotnet new` comando crea una nuova cartella denominata *app* e genera un'applicazione console "Hello World". Cambiare directory e passare alla cartella dell' *app* , dalla sessione del terminale. Usare il `dotnet run` comando per avviare l'app. L'applicazione viene eseguita e viene stampata `Hello World!` sotto il comando:

```dotnetcli
dotnet run
Hello World!
```

Il modello predefinito crea un'app che stampa nel terminale e quindi termina immediatamente. Per questa esercitazione si userà un'app che viene eseguita a ciclo continuo. Aprire il file *Program.cs* in un editor di testo.

> [!TIP]
> Se si usa Visual Studio Code, nella sessione terminal precedente digitare il comando seguente:
>
> ```
> code .
> ```
>
> Verrà aperta la cartella dell' *app* che contiene il progetto in Visual Studio Code.

Il *Program.cs* dovrebbe essere simile al codice C# seguente:

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Sostituirlo con il codice seguente che conta i numeri ogni secondo:

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

Salvare il file e testare di nuovo il programma con `dotnet run`. Tenere presente che l'app viene eseguita per un tempo illimitato. Usare il comando Annulla <kbd>CTRL + C</kbd> per arrestarlo. Di seguito è riportato un esempio di output:

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Se si passa un numero all'app nella riga di comando, verrà eseguito il conteggio fino a quel numero e quindi l'app verrà chiusa. Provare con `dotnet run -- 5` per contare fino a cinque.

> [!IMPORTANT]
> I parametri dopo `--` non vengono passati al comando `dotnet run` e vengono invece passati all'applicazione.

## <a name="publish-net-core-app"></a>Pubblicare l'app .NET Core

Prima di aggiungere l'app .NET Core all'immagine Docker, è prima necessario pubblicarla. È consigliabile fare in modo che il contenitore esegua la versione pubblicata dell'app. Per pubblicare l'app, eseguire il comando seguente:

```dotnetcli
dotnet publish -c Release
```

Questo comando compila l'app nella cartella *publish*. Il percorso della cartella *publish* dalla cartella di lavoro deve essere `.\App\bin\Release\netcoreapp3.1\publish\`

#### <a name="windows"></a>[Windows](#tab/windows)

Dalla cartella dell' *app* , ottenere un elenco di directory della cartella di pubblicazione per verificare che sia stato creato il file *Netcore. docker. dll* .

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[Linux](#tab/linux)

Usare il `ls` comando per ottenere un elenco di directory e verificare che sia stato creato il file *Netcore. docker. dll* .

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a>Creare il Dockerfile

Il file *Dockerfile* viene usato dal comando `docker build` per creare un'immagine del contenitore. Si tratta di un file di testo denominato *Dockerfile* che non dispone di un'estensione.

Creare un file denominato *Dockerfile* nella directory contenente il file con *estensione csproj* e aprirlo in un editor di testo. Questa esercitazione userà l'immagine di runtime ASP.NET Core (che contiene l'immagine di runtime di .NET Core) e corrisponde all'applicazione console .NET Core.

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
```

> [!NOTE]
> L'immagine di runtime ASP.NET Core viene utilizzata intenzionalmente, sebbene `mcr.microsoft.com/dotnet/core/runtime:3.1` sia possibile utilizzarla.

La `FROM` parola chiave richiede un nome completo dell'immagine del contenitore docker. Microsoft Container Registry (mcr.microsoft.com) è un consorzio di Docker Hub, che ospita i contenitori accessibili pubblicamente. Il `dotnet/core` segmento è il repository del contenitore, dove come `aspnet` segmento è il nome dell'immagine del contenitore. L'immagine è contrassegnata `3.1`con, che viene usata per il controllo delle versioni. Quindi, `mcr.microsoft.com/dotnet/core/aspnet:3.1` è il runtime di .net core 3,1. Assicurarsi di eseguire il pull della versione runtime corrispondente al runtime di destinazione dell'SDK. Ad esempio, l'app creata nella sezione precedente usava .NET Core 3,1 SDK e l'immagine di base a cui si fa riferimento in *Dockerfile* è contrassegnata con **3,1**.

Salvare il file *Dockerfile*. La struttura directory della cartella di lavoro deve avere un aspetto simile al seguente. Alcuni file e cartelle di livello più profondo sono stati omessi per risparmiare spazio nell'articolo:

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

Dal terminale eseguire il comando seguente:

```Docker
docker build -t counter-image -f Dockerfile .
```

Docker elaborerà ogni riga nel *Dockerfile*. `.` Nel `docker build` comando indica a Docker di usare la cartella corrente per trovare un *Dockerfile*. Questo comando compila l'immagine e crea un repository locale denominato **Counter-image** che punta a tale immagine. Dopo l'esecuzione del comando, eseguire `docker images` per visualizzare un elenco delle immagini installate:

```Docker
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

Come si può notare, le due immagini condividono lo stesso valore di **IMAGE ID**. Il valore delle due immagini è lo stesso perché l'unico comando nel *Dockerfile* indicava di basare la nuova immagine su un'immagine esistente. Si aggiungono tre comandi a *Dockerfile*. Ogni comando crea un nuovo livello immagine con il comando finale che rappresenta i punti di ingresso del repository di **Immagini contatore** a.

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

Il comando `COPY` indica a Docker di copiare la cartella specificata nel computer in una cartella nel contenitore. In questo esempio, la cartella di *pubblicazione* viene copiata in una cartella denominata *app* nel contenitore.

Il `WORKDIR` comando modifica la **directory corrente** all'interno del contenitore in *app*.

Il comando successivo, `ENTRYPOINT`, indica a Docker di configurare il contenitore in modo che venga eseguito come un eseguibile. All'avvio del contenitore viene eseguito il comando `ENTRYPOINT`. Al termine del comando, il contenitore si arresta automaticamente.

Dal terminale eseguire `docker build -t counter-image -f Dockerfile .`, quindi dopo il completamento del comando eseguire `docker images`.

```Docker
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

Ogni comando nel *Dockerfile* ha generato un livello e ha creato un **IMAGE ID**. L' **ID immagine** finale (il valore sarà diverso) è **cd11c3df9b19** e successivamente verrà creato un contenitore basato su questa immagine.

## <a name="create-a-container"></a>Creare un contenitore

Ora che si dispone di un'immagine che contiene l'app, è possibile creare un contenitore. Lo si può fare in due modi. Prima di tutto, creare un nuovo contenitore arrestato.

```Docker
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

Il `docker create` comando precedente creerà un contenitore in base all'immagine del **contatore** . L'output del comando mostra il **CONTAINER ID** (diverso da quello visualizzato dall'utente) del contenitore creato. Per visualizzare un elenco di *tutti* i contenitori, usare il comando `docker ps -a`:

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a>Gestire il contenitore

Il contenitore è stato creato con un nome `core-counter`specifico, questo nome viene usato per gestire il contenitore. L'esempio seguente usa il comando `docker start` per avviare il contenitore e quindi usa il comando `docker ps` per visualizzare solo i contenitori in esecuzione:

```Docker
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

Analogamente, il comando `docker stop` arresta il contenitore. Nell'esempio seguente viene usato `docker stop` il comando per arrestare il contenitore e quindi viene usato `docker ps` il comando per indicare che non è in esecuzione alcun contenitore:

```Docker
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a>Connettersi a un contenitore

Quando un contenitore è in esecuzione, è possibile connettersi ad esso per visualizzare l'output. Usare i comandi `docker start` e `docker attach` per avviare il contenitore e osservare il flusso di output. In questo esempio, la sequenza di tasti <kbd>CTRL + C</kbd> viene usata per scollegare il contenitore in esecuzione. Questa sequenza di tasti termina il processo nel contenitore se non diversamente specificato, in modo da arrestare il contenitore. Il `--sig-proxy=false` parametro garantisce che la <kbd>combinazione di tasti CTRL + C</kbd> non arresterà il processo nel contenitore.

Dopo essersi scollegati dal contenitore, collegarsi di nuovo per verificare che sia ancora in esecuzione e continui a eseguire il conteggio.

```Docker
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Eliminare un contenitore

Ai fini di questo articolo, i contenitori che non servono più possono essere eliminati. Eliminare il contenitore creato in precedenza. Se è in esecuzione, arrestarlo.

```Docker
docker stop core-counter
```

L'esempio seguente elenca tutti i contenitori. Usa poi il comando `docker rm` per eliminare il contenitore e quindi controlla una seconda volta che non ci siano contenitori in esecuzione.

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a>Esecuzione singola

Docker fornisce il comando `docker run` per creare ed eseguire il contenitore con un unico comando. Questo comando elimina la necessità di eseguire `docker create` e quindi `docker start`. È anche possibile impostare il comando in modo che elimini automaticamente il contenitore quando viene arrestato. Ad esempio, usare `docker run -it --rm` per eseguire due operazioni, ossia usare automaticamente il terminale corrente per connettersi al contenitore e quindi, al termine dell'esecuzione, rimuovere il contenitore:

```Docker
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Il contenitore passa anche i parametri nell'esecuzione dell'app .NET Core. Per indicare all'app .NET Core di contare solo su 3, passare 3.

```Docker
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

Con `docker run -it`, il comando <kbd>CTRL + C</kbd> arresterà il processo in esecuzione nel contenitore, che a sua volta interrompe il contenitore. Poiché è stato specificato il parametro `--rm`, il contenitore viene eliminato automaticamente quando viene arrestato il processo. Verificare che non esista:

```Docker
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a>Modificare il comando ENTRYPOINT

Il comando `docker run` consente anche di modificare il comando `ENTRYPOINT` dal *Dockerfile* e di eseguire qualcosa di diverso, ma solo per il contenitore in questione. Ad esempio, usare il comando seguente per eseguire `bash` o `cmd.exe`. Modificare il comando in base alle esigenze.

#### <a name="windows"></a>[Windows](#tab/windows)

In questo esempio `ENTRYPOINT` viene sostituito con `cmd.exe`. Premere <kbd>CTRL + C</kbd> per terminare il processo e arrestare il contenitore.

```Docker
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[Linux](#tab/linux)

In questo esempio `ENTRYPOINT` viene sostituito con `bash`. Viene quindi eseguito il comando `exit` che termina il processo e arresta il contenitore.

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a>Comandi essenziali

Docker dispone di diversi comandi che consentono di creare, gestire e interagire con contenitori e immagini. I comandi Docker seguenti sono essenziali per la gestione dei contenitori:

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [immagine Docker](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>Pulizia delle risorse

Durante questa esercitazione sono stati creati contenitori e immagini. Se si preferisce, è possibile eliminare queste risorse. Usare i comandi seguenti per

01. Elencare tutti i contenitori

    ```Docker
    docker ps -a
    ```

02. Arrestare i contenitori in esecuzione con il nome.

    ```Docker
    docker stop counter-image
    ```

03. Eliminare il contenitore

    ```Docker
    docker rm counter-image
    ```

Eliminare quindi le immagini che non si desidera conservare nel computer. Eliminare l'immagine creata dal *Dockerfile* e quindi eliminare l'immagine .NET Core su cui è stato basato il *Dockerfile*. È possibile usare l'**IMAGE ID** o la stringa formattata come **REPOSITORY:TAG**.

```Docker
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

Usare il comando `docker images` per visualizzare un elenco delle immagini installate.

> [!TIP]
> I file di immagine possono essere di grandi dimensioni. In genere è consigliabile rimuovere i contenitori temporanei creati durante il test e lo sviluppo dell'app. Conservare invece le immagini di base con il runtime installato se si prevede di compilare altre immagini basate su quel runtime.

## <a name="next-steps"></a>Passaggi successivi

- [Vedere le informazioni su come distribuire un'applicazione ASP.NET Core in un contenitore.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Esaminare i servizi di Azure che supportano i contenitori.](https://azure.microsoft.com/overview/containers/)
- [Leggere le informazioni sui comandi del Dockerfile.](https://docs.docker.com/engine/reference/builder/)
- [Esplorare gli strumenti per contenitori di Visual Studio](/visualstudio/containers/overview)
