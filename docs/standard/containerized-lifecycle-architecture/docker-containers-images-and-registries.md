---
title: I registri, immagini e i contenitori di docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0cccead8833c63f19b359f830f555e7ff31daa1a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="docker-containers-images-and-registries"></a>I registri, immagini e i contenitori di docker

Quando si usa Docker, creerai un'app o un servizio e un pacchetto e le relative dipendenze in un'immagine contenitore. Un'immagine è una rappresentazione statica della app o servizio e la relativa configurazione e le dipendenze.

Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un ambiente di sviluppo o un PC.

Archiviare le immagini in un registro di sistema, che funziona come una libreria di immagini. È necessario un registro di sistema durante la distribuzione in orchestrators di produzione. Docker gestisce un registro di sistema pubblico tramite [Hub Docker](https://hub.docker.com/); altri fornitori offrono i registri per le diverse raccolte di immagini. In alternativa, le aziende possono avere un privato del Registro di sistema locale per le proprie immagini Docker.

Figura 1-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti. Vengono inoltre mostrate le offerte del Registro di sistema più fornitori.

![](./media/image4.png)

Figura 1-4: tassonomia di concetti e termini di Docker

Inserendo le immagini in un registro di sistema, è possibile archiviare i bit di applicazione statico e non modificabile, incluse tutte le relative dipendenze, un livello di framework. È quindi possibile modificare la versione e distribuire le immagini in più ambienti e pertanto costituiscono un'unità di distribuzione uniforme.

Registri di immagine privata ospitata in locale o nel cloud, sono consigliate per le situazioni seguenti:

-   Le immagini non devono essere condiviso pubblicamente a causa di riservatezza.

-   Si desidera la latenza di rete minime tra le immagini e l'ambiente di distribuzione scelto. Ad esempio, se l'ambiente di produzione Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima. In modo analogo, se l'ambiente di produzione è locale, è possibile impostare un locale registro attendibile Docker disponibili all'interno della stessa rete locale.

>[!div class="step-by-step"]
[Precedente] (docker-terminology.md) [Avanti] (Docker-applicazione-del ciclo di vita/index.md)
