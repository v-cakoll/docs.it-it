---
title: Principi di progettazione comuni contenitore
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d3ae0c05a7e94d739a3442ecdb11564a70567963
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071175"
---
# <a name="common-container-design-principles"></a>Principi di progettazione comuni contenitore

-Ahead di assuma il processo di sviluppo sono presenti alcuni concetti di base utile citare in relazione a come utilizzare i contenitori.

## <a name="container-equals-a-process"></a>Contenitore è uguale a un processo

Nel modello di contenitore, un contenitore rappresenta un singolo processo. Definendo un contenitore come limite di processo, iniziare a creare le primitive utilizzate per la scala, o batch-off, i processi. Quando si esegue un contenitore Docker, si noterà un [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definizione. Ciò consente di definire il processo e la durata del contenitore. Quando il processo viene completato, termina il ciclo di vita. Esistono processi con esecuzione prolungata, ad esempio server web e i processi di breve durati, ad esempio i processi batch, che potrebbe essere implementati come Microsoft Azure [processi Web](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/). Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se l'agente di orchestrazione è stata invitati a mantenere le cinque istanze in esecuzione e uno non riesce, l'agente di orchestrazione verrà creato un altro contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato.

È possibile trovare uno scenario in cui si desiderano più processi in esecuzione in un singolo contenitore. In qualsiasi documento di architettura, non riguarda mai un "," né esiste sempre un "sempre". Per scenari che richiedono più processi, un modello comune consiste nell'usare [Supervisore](http://supervisord.org/).


>[!div class="step-by-step"]
[Precedente](design-docker-applications.md)
[Successivo](monolithic-applications.md)
