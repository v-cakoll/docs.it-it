---
title: Docker-gRPC per sviluppatori WCF
description: Creazione di immagini Docker per ASP.NET Core applicazioni gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6e9d4956077286d133d09ab8e681ba5e82ab1aa4
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184477"
---
# <a name="docker"></a>Docker

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Questa sezione include la creazione di immagini Docker per ASP.NET Core applicazioni gRPC, pronte per l'esecuzione in Docker, Kubernetes o in altri ambienti contenitore. L'applicazione di esempio usata con un'app Web MVC ASP.NET Core e un servizio gRPC è disponibile nel repository [RendleLabs/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Immagini di base di Microsoft per applicazioni ASP.NET Core

Microsoft offre una gamma di immagini di base per la compilazione e l'esecuzione di applicazioni .NET Core. Per creare un'immagine di ASP.NET Core 3,0, vengono usate due immagini di base: un'immagine dell'SDK per compilare e pubblicare l'applicazione e un'immagine di runtime per la distribuzione.

| Image | Descrizione |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Per la compilazione di `docker build`applicazioni con. Che non deve essere utilizzato nell'ambiente di produzione. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Contiene le dipendenze di runtime e ASP.NET Core. Per la produzione. |

Per ogni immagine sono disponibili quattro varianti basate su distribuzioni diverse di Linux, distinte per i tag.

| Tag immagine | Linux | Note |
| --------- | ----- | ----- |
| 3,0-Buster, 3,0 | Debian 10 | Immagine predefinita se non è specificata alcuna variante del sistema operativo. |
| 3,0-alpino | Alpino 3,9 | Le immagini di base Alpine sono molto più piccole di quelle Debian o Ubuntu. |
| 3,0-disco | Ubuntu 19,04 | |
| 3,0-Bionic | Ubuntu 18.04 | |

L'immagine di base Alpina è di circa 100 MB, rispetto a 200 MB per le immagini Debian e Ubuntu, ma alcuni pacchetti software o librerie potrebbero non essere disponibili nella gestione dei pacchetti di Alpine. Se non si è certi dell'immagine da usare, è preferibile attenersi alla Debian predefinita, a meno che non sia necessario usare una distribuzione diversa.

> [!IMPORTANT]
> Assicurarsi di usare la stessa variante di Linux per la compilazione e il Runtime. Le applicazioni compilate e pubblicate in una variante potrebbero non funzionare in un'altra.

## <a name="create-a-docker-image"></a>Creare un'immagine Docker

Un'immagine Docker è definita da un *Dockerfile*, un file di testo che contiene tutti i comandi necessari per compilare l'applicazione e installare le dipendenze necessarie per la compilazione o l'esecuzione dell'applicazione. Nell'esempio seguente viene illustrato il Dockerfile più semplice per un'applicazione ASP.NET Core 3,0:

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

Il Dockerfile è costituito `sdk` `aspnet` da due parti: la prima usa l'immagine di base per compilare e pubblicare l'applicazione; il secondo crea un'immagine di runtime dalla base. Ciò è dovuto al `sdk` fatto che l'immagine è di circa 900 MB rispetto a circa 200 MB per l'immagine di runtime e la maggior parte del contenuto non è necessaria in fase di esecuzione.

### <a name="the-build-steps"></a>Procedura di compilazione

| Passaggio | Descrizione |
| ---- | ----------- |
| `FROM ...` | Dichiara l'immagine di base e assegna l'alias `builder` (vedere la sezione successiva per la spiegazione). |
| `WORKDIR /src` | Crea la `/src` directory e la imposta come directory di lavoro corrente. |
| `COPY . .` | Copia tutti gli elementi sotto la directory corrente nell'host nella directory corrente dell'immagine. |
| `RUN dotnet restore` | Ripristina tutti i pacchetti esterni (ASP.NET Core Framework 3,0 è preinstallato con l'SDK). |
| `RUN dotnet publish ...` | Compila e pubblica una build di rilascio. Si noti che `--runtime` il flag non è obbligatorio. |

### <a name="the-runtime-image-steps"></a>Passaggi dell'immagine di runtime

| Passaggio | Descrizione |
| ---- | ----------- |
| `FROM ...` | Dichiara una nuova immagine di base. |
| `WORKDIR /app` | Crea la `/app` directory e la imposta come directory di lavoro corrente. |
| `COPY --from=builder ...` | Copia l'applicazione pubblicata dall'immagine precedente, utilizzando l' `builder` alias dalla prima `FROM` riga. |
| `ENTRYPOINT [ ... ]` | Imposta il comando da eseguire all'avvio del contenitore. Il `dotnet` comando nell'immagine di runtime può eseguire solo file dll. |

### <a name="https-in-docker"></a>HTTPS in Docker

Le immagini di base di Microsoft per Docker `ASPNETCORE_URLS` impostano `http://+:80`la variabile di ambiente su. Ciò significa che il gheppio viene eseguito senza HTTPS su tale porta. Se si usa HTTPS con un certificato personalizzato (come descritto nella [sezione precedente](self-hosted.md)), è consigliabile eseguire l'override impostando la variabile di ambiente **nella parte relativa alla creazione dell'immagine di runtime** di Dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Il file con estensione dockerignore

Analogamente ai `.dockerignore` filecheescludonodeterminatifileedirectorydalcontrollodelcodicesorgente,ilfilepuòessereusatoperescluderefileedirectorydallacopianell'immagine`.gitignore` durante la compilazione. In questo modo non solo viene salvata la copia dell'ora, ma è anche possibile evitare alcuni errori di confusione `obj` che derivano dalla presenza (in particolare) della directory dal PC copiato nell'immagine. È necessario aggiungere almeno voci per `bin` e `obj` al `.dockerignore` file.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Creare l'immagine

Per una soluzione con una singola applicazione e quindi un singolo Dockerfile, è più semplice inserire il Dockerfile nella directory di base; ovvero la stessa directory in cui si trova `.sln` il file. In tal caso, per compilare l'immagine, usare il comando `docker build` seguente dalla directory che contiene Dockerfile.

```console
docker build --tag stockdata .
```

Il flag con nome `--tag` confuso, che può essere abbreviato `-t`in, specifica il nome completo dell'immagine, *incluso* il tag effettivo, se specificato. Alla fine specifica il *contesto* in cui verrà eseguita la compilazione; la directory di lavoro corrente per i `COPY` comandi in Dockerfile. `.`

Se si dispone di più applicazioni all'interno di una singola soluzione, è possibile mantenere il Dockerfile per ogni applicazione nella propria cartella, `.csproj` accanto al file, ma è comunque necessario `docker build` eseguire il comando dalla directory di base per assicurarsi che la soluzione e tutti i progetti vengono copiati nell'immagine. È possibile specificare un Dockerfile sotto la directory corrente usando il `--file` flag ( `-f`o).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Eseguire l'immagine in un contenitore del computer

Per eseguire l'immagine nell'istanza locale di Docker, usare il `docker run` comando.

```console
docker run -ti -p 5000:80 stockdata
```

Il `-ti` flag connette il terminale corrente al terminale del contenitore e viene eseguito in modalità interattiva. `-p 5000:80` Pubblica (collega) la porta 80 sul contenitore alla porta 80 sull'interfaccia di rete localhost.

## <a name="push-the-image-to-a-registry"></a>Eseguire il push dell'immagine in un registro

Dopo aver verificato il funzionamento dell'immagine, è necessario eseguirne il push in un registro Docker per renderlo disponibile in altri sistemi. Le reti interne dovranno eseguire il provisioning di un registro docker. Questa operazione può essere semplice quanto l'esecuzione dell' [ `registry` immagine di Docker](https://docs.docker.com/registry/deploying/) (a destra, il registro Docker viene eseguito in un contenitore Docker), ma sono disponibili diverse soluzioni più complete. Per la condivisione esterna e l'uso del cloud, sono disponibili diversi registri gestiti, ad esempio [Azure container Registry](https://docs.microsoft.com/azure/container-registry/) o [Hub Docker](https://docs.docker.com/docker-hub/repos/).

Per eseguire il push nell'hub Docker, anteporre al nome dell'utente o dell'organizzazione il nome dell'immagine.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Per eseguire il push in un registro privato, anteporre al nome dell'immagine il nome host del registro di sistema e il nome dell'organizzazione.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Quando l'immagine si trova in un registro, è possibile distribuirla nei singoli host Docker o in un motore di orchestrazione del contenitore come Kubernetes.

>[!div class="step-by-step"]
>[Precedente](self-hosted.md)
>[Successivo](kubernetes.md)
