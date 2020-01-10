---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core in un contenitore con Docker.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e012fcf78c88e7f64f6ee205cd69b69683bed9c3
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740767"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Esercitazione: distribuire un'app .NET Core

Questa esercitazione illustra come compilare un'immagine Docker che contiene un'applicazione .NET Core. L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.

Si imparerà a:

> [!div class="checklist"]
>
> - Creare e pubblicare un'app .NET Core semplice
> - Creare e configurare un Dockerfile per .NET Core
> - Creare un'immagine Docker
> - Creare ed eseguire un contenitore Docker

L'esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core. La *piattaforma Docker* usa il *motore Docker* per compilare rapidamente app e inserirle in pacchetti come *immagini Docker*. Queste immagini vengono scritte nel formato *Dockerfile* per la distribuzione e l'esecuzione in un contenitore su più livelli.

## <a name="prerequisites"></a>Prerequisiti

Installare i prerequisiti seguenti:

- [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\
Se .NET Core è già installato, usare il comando `dotnet --info` per determinare quale SDK è in uso.

- [Docker Community Edition](https://www.docker.com/products/docker-desktop)

- Una cartella di lavoro temporanea per il *Dockerfile* e l'app .NET Core di esempio. In questa esercitazione, il nome `docker-working` viene usato come cartella di lavoro.

### <a name="use-sdk-version-22"></a>Usare la versione 2.2 dell'SDK

Se si usa un SDK più recente, ad esempio la versione 3.0, assicurarsi che nell'app venga forzato l'uso della versione 2.2 dell'SDK. Creare un file denominato *Global. JSON* nella cartella di lavoro e incollare il codice JSON seguente:

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

Salvare il file. La presenza del file forzerà .NET Core a usare la versione 2.2 per qualsiasi comando `dotnet` chiamato da questa cartella e dalle relative sottocartelle.

## <a name="create-net-core-app"></a>Creare l'app .NET Core

È necessario creare un'app .NET Core che verrà eseguita dal contenitore Docker. Aprire il terminale in uso, creare una cartella di lavoro se non è già stata creata e passare alla cartella. Nella cartella di lavoro, eseguire il comando seguente per creare un nuovo progetto in una sottodirectory denominata *app*:

```dotnetcli
dotnet new console -o app -n myapp
```

La struttura di cartelle sarà simile all'esempio seguente:

```
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

Il comando `dotnet new` crea una nuova directory denominata *app* e genera un'app "Hello World". Passare alla cartella *app* ed eseguire il comando `dotnet run`. Verrà visualizzato l'output seguente:

```console
> dotnet run
Hello World!
```

Il modello predefinito crea un'app che viene visualizzata sul terminale e quindi viene chiusa. Per questa esercitazione si userà un'app che viene eseguita a ciclo continuo. Aprire il file *Program.cs* in un editor di testo. Attualmente il file dovrebbe essere simile al codice seguente:

```csharp
using System;

namespace myapp
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

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

Salvare il file e testare di nuovo il programma con `dotnet run`. Tenere presente che l'app viene eseguita per un tempo illimitato. Usare il comando Annulla <kbd>CTRL</kbd>+<kbd>C</kbd> per arrestarlo. Verrà visualizzato l'output seguente:

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Se si passa un numero all'app nella riga di comando, verrà eseguito il conteggio fino a quel numero e quindi l'app verrà chiusa. Provare con `dotnet run -- 5` per contare fino a cinque.

> [!NOTE]
> I parametri dopo `--` non vengono passati al comando `dotnet run` e vengono invece passati all'applicazione.

## <a name="publish-net-core-app"></a>Pubblicare l'app .NET Core

Prima di aggiungere l'app .NET Core all'immagine Docker occorre pubblicarla. Si vuole garantire che il contenitore esegua la versione pubblicata dell'app all'avvio.

Dalla cartella di lavoro accedere alla cartella *app* nel codice sorgente di esempio ed eseguire il comando seguente:

```dotnetcli
dotnet publish -c Release
```

Questo comando compila l'app nella cartella *publish*. Il percorso della cartella *publish* dalla cartella di lavoro deve essere `.\app\bin\Release\netcoreapp2.2\publish\`

Ottenere una visualizzazione directory della cartella publish per verificare che *myapp.dll* sia stato creato. Dalla cartella *app* eseguire uno dei comandi seguenti:

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a>Creare il Dockerfile

Il file *Dockerfile* viene usato dal comando `docker build` per creare un'immagine del contenitore. È un file di testo non crittografato denominato *Dockerfile*, senza estensione.

Nel terminale passare alla cartella di lavoro creata all'inizio. Creare un file con nome *Dockerfile* nella cartella di lavoro e aprirlo in un editor di testo. Aggiungere il comando seguente come prima riga del file:

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

Il comando `FROM` indica a Docker di scaricare l'immagine con tag **2.2** dal repository **mcr.microsoft.com/dotnet/core/runtime**. Assicurarsi di scaricare il runtime di .NET Core corrispondente al runtime dell'SDK in uso. Ad esempio, l'app creata nella sezione precedente usava .NET Core 2.2 SDK e ha creato un'app destinata a .NET Core 2.2. L'immagine di base a cui viene fatto riferimento nel *Dockerfile* è quindi indentificata dal tag **2.2**.

Salvare il file *Dockerfile*. La struttura directory della cartella di lavoro deve avere un aspetto simile al seguente. Alcuni file e directory nei livelli più profondi sono stati tagliati per risparmiare spazio nell'articolo:

```
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

Dal terminale eseguire il comando seguente:

```console
docker build -t myimage -f Dockerfile .
```

Docker elaborerà ogni riga nel *Dockerfile*. Il punto `.` nel comando `docker build` indica a Docker di usare la cartella corrente per trovare un *Dockerfile*. Questo comando compila un'immagine e crea un repository locale denominato **myimage** che punta a tale immagine. Dopo l'esecuzione del comando, eseguire `docker images` per visualizzare un elenco delle immagini installate:

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

Come si può notare, le due immagini condividono lo stesso valore di **IMAGE ID**. Il valore delle due immagini è lo stesso perché l'unico comando nel *Dockerfile* indicava di basare la nuova immagine su un'immagine esistente. Ora si aggiungeranno due comandi al *Dockerfile*. Ogni comando crea un nuovo livello di immagine con il comando finale che rappresenta l'immagine a cui il repository **myimage** punterà.

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

Il comando `COPY` indica a Docker di copiare la cartella specificata nel computer in una cartella nel contenitore. In questo esempio la cartella *publish* viene copiata in una cartella denominata *app* nel contenitore.

Il comando successivo, `ENTRYPOINT`, indica a Docker di configurare il contenitore in modo che venga eseguito come un eseguibile. All'avvio del contenitore viene eseguito il comando `ENTRYPOINT`. Al termine del comando, il contenitore si arresta automaticamente.

Dal terminale eseguire `docker build -t myimage -f Dockerfile .`, quindi dopo il completamento del comando eseguire `docker images`.

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

Ogni comando nel *Dockerfile* ha generato un livello e ha creato un **IMAGE ID**. L'**IMAGE ID** finale è **ddcc6646461b** (l'utente ne vedrà uno diverso) e successivamente si creerà un contenitore basato su questa immagine.

## <a name="create-a-container"></a>Creare un contenitore

Ora che si dispone di un'immagine che contiene l'app, è possibile creare un contenitore. Lo si può fare in due modi. Prima di tutto, creare un nuovo contenitore arrestato.

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

Il comando `docker create` precedente creerà un contenitore basato sull'immagine **myimage**. L'output del comando mostra il **CONTAINER ID** (diverso da quello visualizzato dall'utente) del contenitore creato. Per visualizzare un elenco di *tutti* i contenitori, usare il comando `docker ps -a`:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a>Gestire il contenitore

A ogni contenitore è assegnato un nome casuale che può essere usato per fare riferimento a tale istanza di contenitore. Ad esempio, per il contenitore creato automaticamente è stato scelto il nome **boring_matsumoto** (l'utente vedrà un nome diverso) e quel nome può essere usato per avviare il contenitore. Per sostituire il nome automatico con un nome specifico occorre usare il parametro `docker create --name`.

L'esempio seguente usa il comando `docker start` per avviare il contenitore e quindi usa il comando `docker ps` per visualizzare solo i contenitori in esecuzione:

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

Analogamente, il comando `docker stop` arresta il contenitore. Nell'esempio seguente viene usato il comando `docker stop` per arrestare il contenitore, quindi viene usato il comando `docker ps` per indicare che non è in esecuzione alcun contenitore:

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>Connettersi a un contenitore

Quando un contenitore è in esecuzione, è possibile connettersi ad esso per visualizzare l'output. Usare i comandi `docker start` e `docker attach` per avviare il contenitore e osservare il flusso di output. In questo esempio viene usato il comando <kbd>CTRL + C</kbd> per scollegarsi dal contenitore in esecuzione. Questo comando può effettivamente terminare il processo nel contenitore, arrestando il contenitore stesso. Il parametro `--sig-proxy=false` assicura che <kbd>CTRL+C</kbd> non arresti il processo nel contenitore.

Dopo essersi scollegati dal contenitore, collegarsi di nuovo per verificare che sia ancora in esecuzione e continui a eseguire il conteggio.

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Eliminare un contenitore

Ai fini di questo articolo, i contenitori che non servono più possono essere eliminati. Eliminare il contenitore creato in precedenza. Se è in esecuzione, arrestarlo.

```console
> docker stop boring_matsumoto
```

L'esempio seguente elenca tutti i contenitori. Usa poi il comando `docker rm` per eliminare il contenitore e quindi controlla una seconda volta che non ci siano contenitori in esecuzione.

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>Esecuzione singola

Docker fornisce il comando `docker run` per creare ed eseguire il contenitore con un unico comando. Questo comando elimina la necessità di eseguire `docker create` e quindi `docker start`. È anche possibile impostare il comando in modo che elimini automaticamente il contenitore quando viene arrestato. Ad esempio, usare `docker run -it --rm` per eseguire due operazioni, ossia usare automaticamente il terminale corrente per connettersi al contenitore e quindi, al termine dell'esecuzione, rimuovere il contenitore:

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Con `docker run -it`, il comando <kbd>CTRL + C</kbd> arresta il processo in esecuzione nel contenitore, cosa che a sua volta arresta il contenitore. Poiché è stato specificato il parametro `--rm`, il contenitore viene eliminato automaticamente quando viene arrestato il processo. Verificare che non esista:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>Modificare il comando ENTRYPOINT

Il comando `docker run` consente anche di modificare il comando `ENTRYPOINT` dal *Dockerfile* e di eseguire qualcosa di diverso, ma solo per il contenitore in questione. Ad esempio, usare il comando seguente per eseguire `bash` o `cmd.exe`. Modificare il comando in base alle esigenze.

#### <a name="windows"></a>Portale di

In questo esempio `ENTRYPOINT` viene sostituito con `cmd.exe`. Premere <kbd>CTRL</kbd>+<kbd>C</kbd> per terminare il processo e arrestare il contenitore.

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

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

#### <a name="linux"></a>Linux

In questo esempio `ENTRYPOINT` viene sostituito con `bash`. Viene quindi eseguito il comando `quit` che termina il processo e arresta il contenitore.

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a>Comandi essenziali

Docker offre numerosi comandi che consentono di eseguire operazioni diverse sul contenitore e sulle immagini. I comandi Docker seguenti sono essenziali per la gestione dei contenitori:

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>Pulire le risorse

Durante questa esercitazione sono stati creati contenitori e immagini. Se si preferisce, è possibile eliminare queste risorse. Usare i comandi seguenti per

01. Elencare tutti i contenitori

    ```console
    > docker ps -a
    ```

02. Arrestare i contenitori in esecuzione. `CONTAINER_NAME` rappresenta il nome assegnato automaticamente al contenitore.

    ```console
    > docker stop CONTAINER_NAME
    ```

03. Eliminare il contenitore

    ```console
    > docker rm CONTAINER_NAME
    ```

Eliminare quindi le immagini che non si desidera conservare nel computer. Eliminare l'immagine creata dal *Dockerfile* e quindi eliminare l'immagine .NET Core su cui è stato basato il *Dockerfile*. È possibile usare l'**IMAGE ID** o la stringa formattata come **REPOSITORY:TAG**.

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

Usare il comando `docker images` per visualizzare un elenco delle immagini installate.

> [!NOTE]
> I file di immagine possono essere di grandi dimensioni. In genere è consigliabile rimuovere i contenitori temporanei creati durante il test e lo sviluppo dell'app. Conservare invece le immagini di base con il runtime installato se si prevede di compilare altre immagini basate su quel runtime.

## <a name="next-steps"></a>Passaggi successivi

- [Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Esaminare i servizi di Azure che supportano i contenitori.](https://azure.microsoft.com/overview/containers/)
- [Leggere le informazioni sui comandi del Dockerfile.](https://docs.docker.com/engine/reference/builder/)
- [Esplorare gli strumenti per contenitori di Visual Studio](/visualstudio/containers/overview)
