---
title: Docker - gRPC for WCF Developers
description: Creazione di immagini Docker per applicazioni ASP.NET Core gRPC
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148114"
---
# <a name="create-docker-images"></a>Creare immagini Docker

Questa sezione illustra la creazione di immagini Docker per ASP.NET applicazioni gRPC Core, pronte per l'esecuzione in Docker, Kubernetes o altri ambienti contenitore. L'applicazione di esempio utilizzata, con un'app Web MVC di ASP.NET core e un servizio gRPC, è disponibile nel repository [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Immagini di base Microsoft per applicazioni ASP.NET Core

Microsoft fornisce una gamma di immagini di base per la creazione e l'esecuzione di applicazioni .NET Core. Per creare un'immagine ASP.NET Core 3.0, si utilizzano due immagini di base:To create an ASP.NET Core 3.0 image, you use two base images:

- Immagine SDK per compilare e pubblicare l'applicazione.
- Immagine di runtime per la distribuzione.

| Immagine | Descrizione |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Per la `docker build`creazione di applicazioni con . Non deve essere utilizzato in produzione. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Contiene le dipendenze runtime e ASP.NET Core. Per la produzione. |

Per ogni immagine, ci sono quattro varianti basate su diverse distribuzioni Linux, distinte dai tag.

| Tag immagine | Linux | Note |
| --------- | ----- | ----- |
| 3.0-buster, 3.0 | Debian 10 | L'immagine predefinita se non viene specificata alcuna variante del sistema operativo. |
| 3.0 alpino | Alpi 3.9 | Le immagini di base alpine sono molto più piccole di quelle di Debian o Ubuntu. |
| 3.0-discoteca | Ubuntu 19.04 | |
| 3.0-bionic | Ubuntu 18.04 | |

L'immagine di base alpina è di circa 100 MB, rispetto ai 200 MB per le immagini Debian e Ubuntu. Alcuni pacchetti software o librerie potrebbero non essere disponibili nella gestione dei pacchetti di Alpine. Se non sei sicuro di quale immagine usare, probabilmente dovresti scegliere il Debian predefinito.

> [!IMPORTANT]
> Assicurarsi di utilizzare la stessa variante di Linux per la compilazione e il runtime. Le applicazioni create e pubblicate su una variante potrebbero non funzionare su un'altra.

## <a name="create-a-docker-image"></a>Creare un'immagine Docker

Un'immagine Docker è definita da un *file Dockerfile*. Si tratta di un file di testo che contiene tutti i comandi necessari per compilare l'applicazione e installare le dipendenze necessarie per la compilazione o l'esecuzione dell'applicazione. L'esempio seguente mostra il Dockerfile più semplice per un'applicazione ASP.NET Core 3.0:The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Il Dockerfile ha due parti: `sdk` il primo utilizza l'immagine di base per compilare e pubblicare l'applicazione; il secondo crea un'immagine di runtime dalla `aspnet` base. Questo perché `sdk` l'immagine è di circa 900 MB, rispetto a circa 200 MB per l'immagine di runtime e la maggior parte del suo contenuto non sono necessari in fase di esecuzione.

### <a name="the-build-steps"></a>Le istruzioni di compilazione

| Passaggio | Descrizione |
| ---- | ----------- |
| `FROM ...` | Dichiara l'immagine di base `builder` e assegna l'alias. |
| `WORKDIR /src` | Crea `/src` la directory e la imposta come directory di lavoro corrente. |
| `COPY . .` | Copia tutti gli elementi al di sotto della directory corrente nell'host nella directory corrente sull'immagine. |
| `RUN dotnet restore` | Ripristina tutti i pacchetti esterni (ASP.NET framework Core 3.0 è preinstallato con l'SDK). |
| `RUN dotnet publish ...` | Compila e pubblica una build di rilascio. Si noti che il `--runtime` flag non è obbligatorio. |

### <a name="the-runtime-image-steps"></a>Passaggi dell'immagine di runtimeThe runtime image steps

| Passaggio | Descrizione |
| ---- | ----------- |
| `FROM ...` | Dichiara una nuova immagine di base. |
| `WORKDIR /app` | Crea `/app` la directory e la imposta come directory di lavoro corrente. |
| `COPY --from=builder ...` | Copia l'applicazione pubblicata dall'immagine `builder` precedente, utilizzando `FROM` l'alias dalla prima riga. |
| `ENTRYPOINT [ ... ]` | Imposta il comando da eseguire all'avvio del contenitore. Il `dotnet` comando nell'immagine di runtime può eseguire solo file DLL. |

### <a name="https-in-docker"></a>HTTPS in Docker

Le immagini di base `ASPNETCORE_URLS` Microsoft per `http://+:80`Docker impostano la variabile di ambiente su , il che significa che Kestrel viene eseguito senza HTTPS su tale porta. Se si utilizza HTTPS con un certificato personalizzato (come descritto in [Applicazioni gRPC self-hosted](self-hosted.md)), è necessario eseguire l'override di questo. Impostare la variabile di ambiente nella parte di creazione dell'immagine di runtime del file Dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Il file .dockerignore

`.gitignore` Analogamente ai file che escludono determinati file e directory dal controllo del codice sorgente, il `.dockerignore` file può essere utilizzato per escludere file e directory dalla copia nell'immagine durante la compilazione. Questo non solo consente di risparmiare tempo di copia, ma `obj` può anche evitare alcuni errori che derivano da avere la directory dal PC copiata nell'immagine. Come minimo, è necessario aggiungere `bin` `obj` voci `.dockerignore` per e al file.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Compilare l'immagine

Per una soluzione con una singola applicazione e quindi un singolo Dockerfile, è più semplice inserire il Dockerfile nella directory di base. In altre parole, metterlo nella stessa `.sln` directory del file. In tal caso, per compilare `docker build` l'immagine, utilizzare il comando seguente dalla directory contenente il Dockerfile.

```console
docker build --tag stockdata .
```

Il flag `--tag` confuso denominato (che `-t`può essere abbreviato in ) specifica l'intero nome dell'immagine, incluso il tag effettivo, se specificato. L'oggetto `.` alla fine specifica il contesto in cui verrà eseguita la compilazione. la directory di `COPY` lavoro corrente per i comandi nel dockerfile.

Se si dispone di più applicazioni all'interno di una singola soluzione, è `.csproj` possibile mantenere il Dockerfile per ogni applicazione nella propria cartella, accanto al file. È comunque `docker build` necessario eseguire il comando dalla directory di base per assicurarsi che la soluzione e tutti i progetti vengano copiati nell'immagine. È possibile specificare un Dockerfile sotto `--file` la `-f`directory corrente utilizzando il flag (o ).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Eseguire l'immagine in un contenitore nel computerRun the image in a container on your machine

Per eseguire l'immagine nell'istanza Docker locale, utilizzare il `docker run` comando .

```console
docker run -ti -p 5000:80 stockdata
```

Il `-ti` flag collega il terminale corrente al terminale del contenitore e viene eseguito in modalità interattiva. La `-p 5000:80` porta pubblica (collegamenti) 80 sul contenitore alla porta 5000 sull'interfaccia di rete localhost.

## <a name="push-the-image-to-a-registry"></a>Eseguire il push dell'immagine in un registro

Dopo aver verificato il funzionamento dell'immagine, eseguirne il push in un Registro di sistema di Docker per renderla disponibile in altri sistemi. Le reti interne dovranno eseguire il provisioning di un registro Docker. Questo può essere semplice come [ `registry` l'esecuzione dell'immagine di Docker](https://docs.docker.com/registry/deploying/) (il Registro di sistema Docker viene eseguito in un contenitore Docker), ma sono disponibili varie soluzioni più complete. Per la condivisione esterna e l'uso nel cloud, sono disponibili vari registri gestiti, ad esempio [Registro contenitori](https://docs.microsoft.com/azure/container-registry/) di Azure o [Docker Hub](https://docs.docker.com/docker-hub/repos/).

Per eseguire il push a Docker Hub, anteporre all'utente o all'organizzazione il nome dell'utente o dell'organizzazione.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Per eseguire il push in un registro privato, anteporre al nome dell'immagine il nome host del Registro di sistema e il nome dell'organizzazione.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Dopo che l'immagine è in un Registro di sistema, è possibile distribuirla a singoli host Docker o a un motore di orchestrazione contenitore come Kubernetes.After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.

>[!div class="step-by-step"]
>[Successivo](self-hosted.md)
>[precedente](kubernetes.md)
