---
title: Principi di progettazione comuni di contenitore
description: Informazioni su un principio fondamentale della progettazione di contenitore valido, è che un contenitore deve ospitare un unico processo.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: ce51eb296591490fba2d37e753be7881a55ea556
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220335"
---
# <a name="common-container-design-principles"></a>Principi di progettazione comuni di contenitore

-Ahead di introduzione nel processo di sviluppo sono disponibili alcuni concetti di base che è opportuno menzionare per quanto riguarda l'utilizzo di contenitori.

## <a name="container-equals-a-process"></a>Contenitore è uguale a un processo

Nel modello di contenitore, un contenitore rappresenta un singolo processo. Con la definizione di un contenitore come limite di processo, si inizia a creare le primitive utilizzate per scalabilità, o batch-off, i processi. Quando si esegue un contenitore Docker, si noterà un' [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definizione. Questa impostazione definisce il processo e la durata del contenitore. Al termine del processo, termina il ciclo di vita del contenitore. Esistono processi a esecuzione prolungata, ad esempio server web e processi di breve durati, ad esempio i processi di batch, che potrebbero essere stati implementati come Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se è stato richiesto l'agente di orchestrazione per mantenere cinque istanze in esecuzione e uno ha esito negativo, l'agente di orchestrazione verrà creato un altro contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato.

È possibile trovare uno scenario in cui si desidera più processi in esecuzione in un singolo contenitore. In qualsiasi documento di architettura, non riguarda mai un "," né è sempre disponibile un' "sempre". Per gli scenari che richiedono più processi, un modello comune consiste nell'usare [Supervisore](http://supervisord.org/).

>[!div class="step-by-step"]
>[Precedente](design-docker-applications.md)
>[Successivo](monolithic-applications.md)