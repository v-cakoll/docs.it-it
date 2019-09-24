---
title: Altre opzioni di distribuzione del contenitore
description: Altre opzioni di distribuzione del contenitore con Azure
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214450"
---
# <a name="other-container-deployment-options"></a>Altre opzioni di distribuzione del contenitore

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Oltre a eseguire la distribuzione in AKS, è anche possibile distribuire i contenitori per app Azure servizio per contenitori e istanze di contenitore di Azure.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>Quando è opportuno eseguire la distribuzione nel servizio app per i contenitori?

Le applicazioni di produzione semplici che non richiedono l'orchestrazione sono particolarmente adatte per app Azure servizio per i contenitori.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Come eseguire la distribuzione nel servizio app per i contenitori

Per eseguire la distribuzione nel [servizio app Azure per i contenitori](https://azure.microsoft.com/services/app-service/containers/), è necessario aver configurato una container Registry di Azure (ACR) e le credenziali per l'accesso. Eseguire il push del contenitore che si intende ospitare nel registro di sistema in modo che sia disponibile per il pull nel servizio app Azure. Una volta creata, è possibile configurare l'app per la distribuzione continua, che distribuirà automaticamente gli aggiornamenti all'app ogni volta che si aggiorna l'immagine corrispondente in ACR.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Quando è opportuno eseguire la distribuzione in istanze di contenitore di Azure?

Le istanze di contenitore di Azure sono ideali per gli scenari di test. Forniscono un modo semplice e veloce per distribuire un'applicazione in un'istanza di contenitore ospitata nel cloud. È possibile usarli per testare o demo le applicazioni quando non sono richieste funzionalità di scalabilità e orchestrazione offerte dal servizio Azure Kubernetes.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Come distribuire un'app in istanze di contenitore di Azure

Per eseguire la distribuzione in [istanze di contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/), è necessario aver configurato un container Registry di Azure e le credenziali per l'accesso. È anche necessario che in precedenza sia stato eseguito il push dell'immagine del contenitore nel registro di sistema, in modo che sia disponibile per il pull in ACI. È possibile lavorare con ACI usando l'interfaccia della riga di comando di Azure o tramite il portale. I registri contenitori di Azure semplificano la distribuzione di singole istanze di contenitore in ACI direttamente dall'interno del registro di sistema, come illustrato nella figura 3-14.

![Istanza di esecuzione Container Registry di Azure](./media/acr-runinstance-contextmenu.png)

**Figura 3-14**. Istanza di esecuzione Container Registry di Azure

Per creare un'istanza di contenitore dal registro di sistema è sufficiente specificare le normali impostazioni di Azure (nome, sottoscrizione, gruppo di risorse e località), la quantità di memoria da allocare al contenitore e la porta su cui deve essere in ascolto. Questa [Guida introduttiva illustra come distribuire un'istanza del contenitore in ACI usando il portale di Azure](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

Al termine della distribuzione, trovare l'indirizzo IP del contenitore appena distribuito e comunicarlo tramite la porta specificata.

Istanze di contenitore di Azure offre il modo più semplice e rapido per eseguire un contenitore in Azure. Non è necessario configurare un servizio app o un agente di orchestrazione o per gestire le macchine virtuali. Tuttavia, a causa della relativa semplicità, ACI deve essere usato principalmente a scopo di test. Se l'applicazione richiede la scalabilità automatica, più contenitori configurati per funzionare insieme o altre funzionalità complesse sono disponibili altri servizi di Azure più appropriati per ospitare l'app.

## <a name="references"></a>Riferimenti

- [Documentazione di istanze di contenitore di Azure](https://docs.microsoft.com/azure/container-instances/)
- [Distribuire un'istanza del contenitore da ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Precedente](scale-containers-serverless.md)
>[Successivo](communication-patterns.md)
