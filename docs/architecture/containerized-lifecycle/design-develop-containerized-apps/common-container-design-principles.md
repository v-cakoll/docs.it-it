---
title: Principi comuni di progettazione dei contenitori
description: 'Informazioni su un principio fondamentale per la progettazione corretta di contenitori: un contenitore deve ospitare un unico processo.'
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672498"
---
# <a name="common-container-design-principles"></a>Principi comuni di progettazione dei contenitori

Prima di iniziare il processo di sviluppo, è necessario prendere in considerazione alcuni concetti di base relativi all'uso dei contenitori.

## <a name="container-equals-a-process"></a>Un contenitore corrisponde a un processo

Nel modello di contenitore, un contenitore rappresenta un singolo processo. Con la definizione di un contenitore come limite di processo, si iniziano a creare le primitive usate per ridimensionare i processi. Quando si esegue un contenitore Docker, viene visualizzata una definizione [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint). Questa definisce il processo e il ciclo di vita del contenitore. Quando il processo viene completato, il ciclo di vita del contenitore termina. Esistono processi a esecuzione prolungata, ad esempio i server Web, e processi di breve durata, ad esempio i processi batch, che possono essere stati implementati come [Processi Web](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/) di Microsoft Azure. Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se all'agente di orchestrazione è stato indicato di mantenere cinque istanze in esecuzione e una non riesce, l'agente crea un altro contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato.

In alcuni scenari è necessario che più processi vengano eseguiti in un singolo contenitore. Nei documenti relativi a qualsiasi architettura non vengono mai usati i termini "mai" e "sempre". Per gli scenari che richiedono più processi, un motivo ricorrente consiste nell'uso di [Supervisor](http://supervisord.org/).

>[!div class="step-by-step"]
>[Successivo](design-docker-applications.md)
>[precedente](monolithic-applications.md)
