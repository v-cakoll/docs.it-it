---
title: Distribuzione di contenitori in Azure
description: Distribuzione di contenitori in Azure con Azure Container Registry, servizio Azure Kubernetes e Azure Dev Spaces.
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183266"
---
# <a name="deploying-containers-in-azure"></a>Distribuzione di contenitori in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

I contenitori offrono molti vantaggi, uno dei quali è la portabilità. È possibile usare facilmente lo stesso contenitore sviluppato e testato localmente e distribuirlo in Azure, dove è possibile eseguire l'app negli ambienti di gestione temporanea e di produzione. Azure offre una serie di opzioni per l'hosting di app basate su contenitori e supporta in modo analogo diversi metodi di distribuzione. L'approccio più comune e flessibile consiste nel distribuire i contenitori in Azure Container Registry (ACR), in cui sono accessibili dai servizi che si desidera utilizzare per ospitarli. Azure app Web per contenitori, i servizi Kubernetes di Azure e l'istanza di contenitore di Azure (ACI) possono accedere alle immagini del contenitore di cui è stato effettuato il push in ACR.

## <a name="azure-container-registry"></a>Registro Azure Container

Azure Container Registry (ACR) consente di creare, archiviare e gestire le immagini per tutte le distribuzioni di contenitori. Sono presenti altri registri contenitori, sia pubblici che privati, a cui è possibile distribuire i contenitori. Il vantaggio di ACR rispetto ad altre opzioni è che è possibile lasciare le immagini vicine all'ambiente di produzione, migliorando i tempi di compilazione e distribuzione. È anche possibile proteggerli usando le stesse procedure di sicurezza usate per le altre risorse di Azure, migliorando la sicurezza e riducendo il lavoro di gestione degli asset.

Si [Crea un registro contenitori con il portale di Azure](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) o [tramite l'interfaccia della](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) riga di comando di Azure o gli [strumenti di PowerShell](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). La creazione di un nuovo registro contenitori richiede solo una sottoscrizione di Azure, un gruppo di risorse e un nome univoco. La figura 3-11 illustra le opzioni di base per la creazione di un registro, che verrà ospitato in *RegistryName*. azurecr.io.

![Creare il registro](./media/create-container-registry.png)
contenitori**Figura 3-11**. Crea registro contenitori

Dopo aver creato un registro, è necessario eseguire l'autenticazione prima di poterlo usare. In genere, si accede al registro di sistema usando il comando dell'interfaccia della riga di comando di Azure:

```azurecli
az acr login --name *registryname*
```

Dopo aver creato un registro di sistema in Azure Container Registry, è possibile usare i comandi di Docker per eseguire il push delle immagini del contenitore. Prima di poter eseguire questa operazione, è tuttavia necessario contrassegnare prima l'immagine con il nome completo (URL) del server di accesso di ACR. Il formato sarà *RegistryName*. azurecr.io.

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

Dopo aver contrassegnato l'immagine, usare il `docker push` comando per eseguire il push dell'immagine nell'istanza di ACR.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

Dopo aver eseguito il push di un'immagine nel registro, è consigliabile rimuovere l'immagine dall'ambiente Docker locale usando questo comando:

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

Gli sviluppatori devono raramente effettuare il push direttamente dai computer a un registro contenitori. Una pipeline di compilazione definita in uno strumento come Azure DevOps deve invece essere responsabile di questo processo. Scopri di più nel [capitolo DevOps nativo del cloud](devops.md).

## <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Se l'applicazione basata su contenitori include più contenitori, è probabile che si desideri definire e gestire le interazioni tra i contenitori usando un agente di *orchestrazione* come Kubernetes. Una volta distribuite le immagini del contenitore in ACR, è possibile configurare facilmente i servizi Kubernetes di Azure per distribuire automaticamente le immagini aggiornate da ACR. Grazie a una pipeline di integrazione continua/recapito continuo completa, è possibile configurare una strategia di [rilascio Canary](https://martinfowler.com/bliki/CanaryRelease.html) per ridurre al minimo i rischi correlati alla distribuzione rapida degli aggiornamenti. La nuova versione dell'app viene inizialmente configurata in produzione senza traffico indirizzato a tale applicazione e quindi un numero ridotto di utenti viene indirizzato alla versione appena distribuita dell'app. Man mano che il team acquisisce confidenza nella nuova versione del software, vengono implementate più istanze della nuova versione e le istanze della versione precedente vengono ritirate. AKS supporta facilmente questo tipo di distribuzione.

Come per la maggior parte delle risorse in Azure, è possibile creare cluster Kubernetes di Azure usando il portale o strumenti della riga di comando o strumenti di automazione dell'infrastruttura come Helm o bonifica. Per iniziare a usare un nuovo cluster, è necessario fornire le seguenti informazioni:

- Sottoscrizione di Azure
- Gruppo di risorse
- Nome del cluster Kubernetes
- Region
- Versione di Kubernetes
- Prefisso nome DNS
- Dimensioni del nodo
- Numero di nodi

Queste informazioni sono sufficienti per iniziare. Come parte del processo di creazione nel portale di Azure, è anche possibile configurare le opzioni per le seguenti funzionalità del cluster:

- Scala
- Autenticazione
- Servizi di rete
- Monitoraggio
- Tag

Questa [Guida introduttiva illustra come distribuire un cluster AKS usando il portale di Azure](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

I cluster Kubernetes complessi possono richiedere risorse significative per ospitare, che rendono difficile per gli sviluppatori eseguire l'intera applicazione in un singolo computer, soprattutto in un computer portatile. Azure Dev Spaces offre una soluzione che consente agli sviluppatori di usare le proprie versioni dei cluster Kubernetes di Azure ospitati in Azure. Azure Dev Spaces è progettato per semplificare lo sviluppo di applicazioni basate su microservizi usando AKS.

Per comprendere il valore di Azure Dev Spaces, è possibile condividere questa citazione da Gabe Monroy, lead PM dei contenitori all'Microsoft Azure:

"Immaginiamo di essere un nuovo dipendente che tenta di correggere un bug in un'applicazione di microservizi complessa costituita da dozzine di componenti, ognuno con la propria configurazione e servizi di supporto. Per iniziare, è necessario configurare l'ambiente di sviluppo locale in modo che possa simulare la produzione, inclusa la configurazione dell'IDE, la creazione della catena di strumenti, le dipendenze dei servizi in contenitori, un ambiente Kubernetes locale, simulazioni per i servizi di supporto e altro ancora. Con il tempo necessario per configurare l'ambiente di sviluppo, la correzione del primo bug potrebbe richiedere giorni.

> In alternativa, è possibile usare gli spazi di sviluppo e AKS ".

Il processo per lavorare con Azure Dev Spaces prevede i passaggi seguenti:

1. Creare lo spazio di sviluppo.
2. Configurare lo spazio di sviluppo radice.
3. Configurare uno spazio di sviluppo figlio (per la propria versione del sistema).
4. Connettersi allo spazio di sviluppo.

Tutti questi passaggi possono essere eseguiti usando l'interfaccia della riga di comando `azds` di Azure e i nuovi strumenti da riga di comando. Ad esempio, per creare un nuovo spazio di sviluppo di Azure per un determinato cluster Kubernetes, usare un comando simile al seguente:

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

Successivamente, è possibile usare il `azds prep` comando per generare le risorse del grafico Docker e Helm necessarie per l'esecuzione dell'applicazione. Eseguire quindi il codice in AKS usando `azds up`. La prima volta che si esegue questo comando, il grafico Helm verrà installato e il contenitore o i contenitori verranno compilati e distribuiti in base alle istruzioni. Questa operazione potrebbe richiedere alcuni minuti la prima volta che viene eseguita. Tuttavia, dopo avere apportato le modifiche, è possibile connettersi allo spazio di sviluppo `azds space select` figlio usando e quindi distribuire ed eseguire il debug degli aggiornamenti nello spazio di sviluppo figlio isolato. Quando lo spazio di sviluppo è attivo e in esecuzione, è possibile inviare gli aggiornamenti eseguendo di nuovo il comando oppure `azds up` è possibile usare gli strumenti incorporati in Visual Studio o Visual Studio Code. Con VS Code, è possibile usare il riquadro comandi per connettersi allo spazio di sviluppo. La figura 3-12 illustra come avviare l'applicazione Web usando Azure Dev Spaces in Visual Studio.

![Connettersi a Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figura 3-12**. Connettersi a Azure Dev Spaces in Visual Studio

## <a name="references"></a>Riferimenti

- [Versione Canary](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces con VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure Dev Spaces con Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
>[Precedente](combine-containers-serverless-approaches.md)
>[Successivo](scale-containers-serverless.md)
