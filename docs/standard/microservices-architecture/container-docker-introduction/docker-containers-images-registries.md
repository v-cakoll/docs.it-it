---
title: I registri, immagini e i contenitori di docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | I registri, immagini e i contenitori di docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a>I registri, immagini e i contenitori di docker

Quando si usa Docker, uno sviluppatore crea un'applicazione o servizio e i pacchetti e le relative dipendenze in un'immagine contenitore. Un'immagine è una rappresentazione statica della app o servizio e la relativa configurazione e le dipendenze.

Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un ambiente di sviluppo o un PC.

Gli sviluppatori devono archiviare immagini in un registro di sistema, che funziona come una libreria di immagini ed è necessario per la distribuzione in orchestrators di produzione. Docker gestisce un registro di sistema pubblico tramite [Hub Docker](https://hub.docker.com/); altri fornitori offrono i registri per le diverse raccolte di immagini. In alternativa, le aziende possono avere un privato del Registro di sistema locale per le proprie immagini Docker.

Figura 2-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti. Vengono inoltre mostrate le offerte del Registro di sistema più fornitori.

![](./media/image5.PNG)

**Figura 2-4**. Tassonomia di concetti e termini di Docker

Inserimento di immagini in un registro di sistema consente di archiviare bit applicazione statici e non modificabile, incluse tutte le relative dipendenze a livello di framework. Queste immagini possono quindi essere distribuiti in più ambienti e con controllo delle versioni e pertanto fornire un'unità di distribuzione uniforme.

I registri di immagine privata, ospitato in locale o nel cloud, sono consigliati quando:

-   Le immagini non devono essere condiviso pubblicamente a causa di riservatezza.

-   Si desidera la latenza di rete minime tra le immagini e l'ambiente di distribuzione scelto. Ad esempio, se l'ambiente di produzione è cloud di Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima. In modo analogo, se l'ambiente di produzione è locale, è possibile impostare un locale registro attendibile Docker disponibili all'interno della stessa rete locale.

>[!div class="step-by-step"]
[Precedente] (docker-terminology.md) [Avanti] (... /NET-core-NET-Framework-Containers/index.MD)
