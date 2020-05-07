---
title: Combinazione di contenitori e approcci senza server per i servizi nativi del cloud
description: Combinazione di contenitori e Kubernetes con approcci senza server
ms.date: 04/23/2020
ms.openlocfilehash: a6ae17543c9075ca84126a4c19f9f51887f7fe9a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895642"
---
# <a name="combining-containers-and-serverless-approaches"></a>Combinazione degli approcci con contenitori e serverless

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le applicazioni native del cloud implementano in genere servizi che sfruttano contenitori e orchestrazione. Spesso è possibile esporre alcuni dei servizi dell'applicazione come funzioni di Azure. Tuttavia, con un'app nativa del cloud distribuita in Kubernetes, sarebbe bello sfruttare le funzioni di Azure all'interno di questo stesso set di strumenti. Fortunatamente, è possibile eseguire il wrapping di funzioni di Azure all'interno di contenitori Docker e distribuirle usando gli stessi processi e gli stessi strumenti del resto dell'app basata su Kubernetes.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>Quando è consigliabile usare i contenitori senza server?

La funzione di Azure non conosce la piattaforma in cui viene distribuita. Per alcuni scenari, è possibile che si disponga di requisiti specifici e che sia necessario personalizzare l'ambiente in cui viene eseguito il codice di funzione. È necessaria un'immagine personalizzata che supporti le dipendenze o una configurazione non supportata dall'immagine predefinita. In questi casi, è opportuno distribuire la funzione in un contenitore Docker personalizzato.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Quando è consigliabile evitare di usare i contenitori con funzioni di Azure?

Se si vuole usare la fatturazione a consumo, non sarà possibile eseguire la funzione in un contenitore. Se si distribuisce la funzione in un cluster Kubernetes, non sarà più possibile trarre vantaggio dal ridimensionamento incorporato fornito da funzioni di Azure. È necessario usare le funzionalità di scalabilità di Kubernetes, descritte in precedenza in questo capitolo.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Come combinare contenitori senza server e Docker

Per eseguire il wrapping di una funzione di Azure in un contenitore Docker, installare il [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) e quindi eseguire il comando seguente:

```console
func init ProjectName --worker-runtime dotnet --docker
```

Quando il progetto viene creato, includerà un Dockerfile e il runtime del ruolo di lavoro `dotnet`configurato per. A questo punto, è possibile creare e testare la funzione localmente. Compilare ed eseguire il comando con `docker build` i `docker run` comandi e. Per i passaggi dettagliati per iniziare a compilare funzioni di Azure con il supporto per Docker, vedere l'esercitazione [creare una funzione in Linux tramite un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Come combinare senza server e Kubernetes con KEDA

In questo capitolo si è notato che la piattaforma funzioni di Azure viene scalata automaticamente per soddisfare la domanda. Quando si distribuiscono funzioni in contenitori in AKS, tuttavia, si perde la funzionalità di scalabilità incorporata. Per il salvataggio viene visualizzato [Kubernetes basato su eventi (Keda)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda). Consente la scalabilità automatica con granularità fine `event-driven Kubernetes workloads,` per includere funzioni in contenitori.

KEDA fornisce la funzionalità di scalabilità guidata dagli eventi per il runtime delle funzioni in un contenitore docker. KEDA può essere scalato da zero istanze (se non si verificano eventi) `n instances`a, in base al carico. Consente la scalabilità automatica esponendo metriche personalizzate a Kubernetes AutoScaler (Horizontal Pod AutoScaler). L'uso di contenitori di funzioni con KEDA consente di replicare le funzionalità della funzione senza server in qualsiasi cluster Kubernetes.

Vale la pena notare che il progetto KEDA è ora gestito da cloud native Computing Foundation (CNCF).

>[!div class="step-by-step"]
>[Precedente](leverage-serverless-functions.md)
>[successivo](deploy-containers-azure.md)
