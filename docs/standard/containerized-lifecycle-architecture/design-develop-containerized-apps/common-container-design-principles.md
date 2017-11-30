---
title: Principi di progettazione comuni contenitore
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7186ae3b768384fe5c6b269578de8db5ef6064c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="common-container-design-principles"></a>Principi di progettazione comuni contenitore

Avanti di recupero nel processo di sviluppo sono presenti alcuni concetti di base utile citare per quanto riguarda l'utilizzo di contenitori.

## <a name="container-equals-a-process"></a>Contenitore è uguale a un processo

Nel modello di contenitore, un contenitore rappresenta un singolo processo. Definisce un contenitore come limite di processo, si inizia a creare le primitive utilizzate per la scala, o batch-off, i processi. Quando si esegue un contenitore Docker, si noterà un [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definizione. Definisce il processo e la durata del contenitore. Al termine del processo, termina il ciclo di vita del contenitore. Esistono processi a esecuzione prolungata, ad esempio server web e i processi di breve durati, ad esempio i processi batch, che potrebbe essere implementati in Microsoft Azure [processi Web](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/). Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se l'agente di orchestrazione è stata invitati a mantenere le cinque istanze in esecuzione e uno non riesce, l'agente di orchestrazione verrà creato un altro contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato.

È possibile trovare uno scenario in cui si desiderano più processi in esecuzione in un singolo contenitore. In qualsiasi documento di architettura, non è mai un "mai" non è sempre un "sempre". Per scenari che richiedono più processi, un modello comune consiste nell'usare [Supervisore](http://supervisord.org/).


>[!div class="step-by-step"]
[Precedente] (applications.md-docker-progettazione) [Avanti] (monolitico applications.md)
