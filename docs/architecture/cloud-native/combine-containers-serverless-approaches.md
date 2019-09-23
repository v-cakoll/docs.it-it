---
title: Combinazione di contenitori e approcci senza server
description: Combinazione di contenitori e Kubernetes con approcci senza server
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183434"
---
# <a name="combining-containers-and-serverless-approaches"></a>Combinazione di contenitori e approcci senza server

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Spesso, le applicazioni basate su microservizi si basano molto sui contenitori, l'orchestrazione e il passaggio di messaggi per la comunicazione tra i nodi. Questa messaggistica è un'attività ideale per funzioni di Azure, ma con il resto dell'applicazione configurata e distribuita con Kubernetes e gli strumenti correlati, sarebbe bello poter sfruttare le funzioni di Azure all'interno dello stesso set di strumenti. Fortunatamente, è possibile eseguire il wrapping di funzioni di Azure nei contenitori Docker e distribuirle usando gli stessi processi e gli stessi strumenti del resto dell'app basata su Kubernetes.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>Quando è consigliabile usare i contenitori senza server?

Per impostazione predefinita, le funzioni senza server non conoscono la piattaforma in cui verranno eseguite. Tuttavia, in alcuni casi è possibile che si disponga di requisiti specifici che rendono importante personalizzare l'immagine del contenitore in cui verrà eseguito il codice. Si consiglia di usare un'immagine personalizzata perché la funzione si basa su una versione specifica del linguaggio o presenta dipendenze o requisiti di configurazione che non sono supportati dall'immagine predefinita. In questi casi, può essere utile personalizzare il proprio contenitore e distribuire la funzione in un contenitore Docker personalizzato.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Quando è consigliabile evitare di usare i contenitori con funzioni di Azure?

Se si prevede di trarre vantaggio dalla fatturazione del piano a consumo per la funzione, non sarà possibile eseguire questa operazione se si usa il proprio contenitore. Se si supera semplicemente l'uso di un contenitore Docker e si distribuiscono le funzioni nel cluster Kubernetes, non sarà più possibile trarre vantaggio dal ridimensionamento incorporato fornito da funzioni di Azure. È necessario usare le funzionalità di scalabilità di Kubernetes, descritte di seguito.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Come combinare contenitori senza server e Docker

Per eseguire il wrapping di una funzione di Azure in un contenitore Docker, installare il Azure Functions Core Tools e quindi eseguire il comando seguente:

```console
func init ProjectName --docker
```

Scegliere il runtime del ruolo di lavoro desiderato dalle opzioni seguenti:

- `dotnet` (C#)
- `node` (JavaScript)
- `python`

Quando viene creato il progetto, verrà incluso un Dockerfile. A questo punto, è possibile creare e testare la funzione localmente. Compilare ed eseguire il comando con `docker build` i `docker run` comandi e. Per i passaggi dettagliati per iniziare a compilare funzioni di Azure con il supporto per Docker, vedere l'esercitazione [creare una funzione in Linux tramite un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Come combinare senza server e Kubernetes con KEDA

Le funzioni di Azure vengono ridimensionate automaticamente per soddisfare la domanda in base alla frequenza degli eventi destinati a una determinata funzione. Inoltre, è possibile sfruttare Kubernetes per ospitare le funzioni e usare la scalabilità automatica basata su eventi basata su Kubernetes o KEDA. Quando non si verificano eventi, KEDA è in grado di ridurre le istanze di 0 e quindi, in risposta agli eventi, può aumentare il numero di contenitori per soddisfare la richiesta usando il relativo ridimensionamento automatico del Pod orizzontale. [Altre informazioni sul ridimensionamento delle funzioni di Azure con Keda](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

## <a name="references"></a>Riferimenti

- [Eseguire funzioni di Azure in un contenitore Docker](https://markheath.net/post/azure-functions-docker)
- [Creare una funzione in Linux usando un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Funzioni di Azure con scalabilità automatica basata su eventi Kubernetes](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
>[Precedente](leverage-serverless-functions.md)
>[Successivo](deploy-containers-azure.md)
