---
title: Altre opzioni di distribuzione del contenitore
description: Altre opzioni di distribuzione del contenitore con Azure
ms.date: 05/13/2020
ms.openlocfilehash: acb022e3d4fd4862c592fa571894e1b8ce17f465
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613759"
---
# <a name="other-container-deployment-options"></a>Altre opzioni di distribuzione del contenitore

Oltre al servizio Azure Kubernetes, è anche possibile distribuire contenitori per app Azure servizio per contenitori e istanze di contenitore di Azure.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>Quando è opportuno eseguire la distribuzione nel servizio app per i contenitori?

Le applicazioni di produzione semplici che non richiedono l'orchestrazione sono particolarmente adatte per app Azure servizio per i contenitori.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Come eseguire la distribuzione nel servizio app per i contenitori

Per eseguire la distribuzione nel [servizio app Azure per i contenitori](https://azure.microsoft.com/services/app-service/containers/), è necessario disporre di un'istanza di Azure container Registry (ACR) e delle credenziali per accedervi. Eseguire il push dell'immagine del contenitore nel repository ACR, in modo che possa essere trascinata nel servizio app Azure. Al termine dell'operazione, è possibile configurare l'app per la distribuzione continua. In questo modo verranno automaticamente distribuiti gli aggiornamenti ogni volta che l'immagine cambia in ACR.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Quando è opportuno eseguire la distribuzione in istanze di contenitore di Azure?

[Istanze di contenitore di Azure (ACI)](https://azure.microsoft.com/services/container-instances/) consente di eseguire contenitori Docker in un ambiente cloud gestito senza server, senza dover configurare macchine virtuali o cluster. Si tratta di un'ottima soluzione per i carichi di lavoro a esecuzione breve che possono essere eseguiti in un contenitore isolato. Prendere in considerazione ACI per servizi semplici, scenari di test, automazione delle attività e processi di compilazione. ACI ruota un'istanza del contenitore, esegue l'attività e quindi la gira verso il basso.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Come distribuire un'app in istanze di contenitore di Azure

Per eseguire la distribuzione in [istanze di contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/), sono necessari un container Registry di Azure e le credenziali per l'accesso. Quando si esegue il push dell'immagine del contenitore nel repository, è possibile effettuare il pull in ACI. È possibile utilizzare ACI usando l'interfaccia della riga di comando portale di Azure o. ACR offre una stretta integrazione con ACI. La figura 3-14 illustra come effettuare il push di una singola immagine del contenitore in ACR.

![Istanza di esecuzione Container Registry di Azure](./media/acr-runinstance-contextmenu.png)

**Figura 3-14**. Istanza di esecuzione Container Registry di Azure

La creazione di un'istanza in ACI può essere eseguita rapidamente. Specificare il registro immagini, le informazioni sul gruppo di risorse di Azure, la quantità di memoria da allocare e la porta su cui restare in ascolto. Questa [Guida introduttiva illustra come distribuire un'istanza del contenitore in ACI usando il portale di Azure](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

Al termine della distribuzione, trovare l'indirizzo IP del contenitore appena distribuito e comunicarlo tramite la porta specificata.

Istanze di contenitore di Azure offre il modo più rapido per eseguire semplici carichi di lavoro dei contenitori in Azure. Non è necessario configurare un servizio app, un agente di orchestrazione o una macchina virtuale. Per gli scenari in cui è necessaria l'orchestrazione completa del contenitore, l'individuazione dei servizi, il ridimensionamento automatico o gli aggiornamenti coordinati, è consigliabile usare Azure Kubernetes Service (AKS).

## <a name="references"></a>Riferimenti

- [Cos'è Kubernetes](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Installazione di Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube rispetto al desktop Docker](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools per Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [Informazioni sull'avvio a freddo senza server](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Istanze di funzioni di Azure pre-surriscaldate](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Creare una funzione in Linux tramite un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Eseguire funzioni di Azure in un contenitore Docker](https://markheath.net/post/azure-functions-docker)
- [Creare una funzione in Linux tramite un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Funzioni di Azure con scalabilità automatica basata su eventi Kubernetes](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)
- [Versione Canary](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces con VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure Dev Spaces con Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)
- [Più pool di nodi AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [Scalabilità automatica del cluster AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Esercitazione: ridimensionare le applicazioni in AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Ridimensionamento e hosting di Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-scale)
- [Documentazione di istanze di contenitore di Azure](https://docs.microsoft.com/azure/container-instances/)
- [Distribuire un'istanza del contenitore da ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Precedente](scale-containers-serverless.md) 
> [Avanti](communication-patterns.md)
