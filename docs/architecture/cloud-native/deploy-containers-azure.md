---
title: Distribuzione di contenitori in Azure
description: Distribuzione di contenitori in Azure con Azure Container Registry, servizio Azure Kubernetes e Azure Dev Spaces.
ms.date: 04/13/2020
ms.openlocfilehash: ba2854323ee0f1394a3cff0dd3756cb3c7c32d5b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614149"
---
# <a name="deploying-containers-in-azure"></a>Distribuzione di contenitori in Azure

I contenitori sono stati discussi in questo capitolo e nel capitolo 1. Abbiamo visto che i contenitori offrono molti vantaggi alle applicazioni native del cloud, inclusa la portabilità. Nel cloud di Azure è possibile distribuire gli stessi servizi in contenitori in ambienti di gestione temporanea e di produzione. Azure offre diverse opzioni per ospitare i carichi di lavoro in contenitori:

- Servizio Azure Kubernetes (AKS)
- Istanze di Azure Container (ACI)
- App Web di Azure per contenitori

## <a name="azure-container-registry"></a>Registro Azure Container

Quando si inserimento un microservizio, è necessario prima di tutto un contenitore di compilazione "image". L'immagine è una rappresentazione binaria del codice del servizio, delle dipendenze e del runtime. Sebbene sia possibile creare manualmente un'immagine usando il `Docker Build` comando dell'API Docker, un approccio migliore consiste nel crearlo come parte di un processo di compilazione automatizzato.

Una volta create, le immagini del contenitore vengono archiviate in registri contenitori. Consentono di compilare, archiviare e gestire le immagini del contenitore. Sono disponibili molti registri, sia pubblici che privati. Azure Container Registry (ACR) è un servizio di registro contenitori completamente gestito nel cloud di Azure. Salva in modo permanente le immagini all'interno della rete di Azure, riducendo il tempo necessario per distribuirle negli host contenitore di Azure. È anche possibile proteggerli usando le stesse procedure di sicurezza e identità usate per le altre risorse di Azure.

Si crea un Container Registry di Azure usando l' [portale di Azure](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), l' [interfaccia](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)della riga di comando di Azure o [gli strumenti di PowerShell](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). La creazione di un registro in Azure è semplice. Richiede una sottoscrizione di Azure, un gruppo di risorse e un nome univoco. La figura 3-11 illustra le opzioni di base per la creazione di un registro, che verrà ospitato in `registryname.azurecr.io` .

![Creare un registro contenitori](./media/create-container-registry.png)

**Figura 3-11**. Creare un registro contenitori

Dopo aver creato il registro di sistema, sarà necessario eseguire l'autenticazione prima di poterlo usare. In genere, si accede al registro di sistema usando il comando dell'interfaccia della riga di comando di Azure:

```azurecli
az acr login --name *registryname*
```

Una volta autenticato, è possibile usare i comandi di Docker per eseguire il push delle immagini del contenitore. Prima di poter eseguire questa operazione, è tuttavia necessario contrassegnare l'immagine con il nome completo (URL) del server di accesso di ACR. Il formato sarà *RegistryName*. azurecr.io.

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

Come procedura consigliata, gli sviluppatori non devono eseguire manualmente il push delle immagini in un registro contenitori. Una pipeline di compilazione definita in uno strumento come GitHub o Azure DevOps deve invece essere responsabile di questo processo. Scopri di più nel [capitolo DevOps nativo del cloud](devops.md).

## <a name="acr-tasks"></a>Attività di Registro Azure Container

Le [attività ACR](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) sono un set di funzionalità disponibili nel container Registry di Azure. Estende il [ciclo di sviluppo a ciclo interno](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) compilando e gestendo le immagini del contenitore nel cloud di Azure. Anziché richiamare un `docker build` e localmente nel `docker push` computer di sviluppo, vengono gestiti automaticamente dalle attività ACR nel cloud.

Il seguente comando AZ CLI compila un'immagine del contenitore e la inserisce in ACR:

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

Come si può notare dal blocco di comandi precedente, non è necessario installare Docker desktop nel computer di sviluppo. Inoltre, è possibile configurare i trigger di attività ACR per ricompilare le immagini dei contenitori sia nel codice sorgente che negli aggiornamenti di immagini di base.

## <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Il servizio Azure Kubernetes (AKS) è stato discusso a lungo in questo capitolo. Si è notato che si tratta dell'agente di orchestrazione del contenitore che gestisce le applicazioni native del cloud in contenitori.

Quando si distribuisce un'immagine in un registro, ad esempio ACR, è possibile configurare AKS per eseguirne il pull e la distribuzione automatica. Con una pipeline di integrazione continua/recapito continuo, è possibile configurare una strategia di [rilascio Canary](https://martinfowler.com/bliki/CanaryRelease.html) per ridurre al minimo i rischi correlati alla distribuzione rapida degli aggiornamenti. La nuova versione dell'app viene inizialmente configurata in produzione senza traffico instradato. Il sistema instraderà quindi una piccola percentuale di utenti alla versione appena distribuita. Man mano che il team acquisisce confidenza nella nuova versione, può implementare più istanze e ritirare il vecchio. AKS supporta facilmente questo tipo di distribuzione.

Come per la maggior parte delle risorse in Azure, è possibile creare un cluster di servizi Kubernetes di Azure usando il portale, la riga di comando o strumenti di automazione come Helm o bonifica. Per iniziare a usare un nuovo cluster, è necessario fornire le seguenti informazioni:

- Sottoscrizione di Azure
- Resource group
- Nome del cluster Kubernetes
- Region
- Versione di Kubernetes
- Prefisso nome DNS
- Dimensioni nodo
- Numero di nodi

Queste informazioni sono sufficienti per iniziare. Come parte del processo di creazione nella portale di Azure, è anche possibile configurare le opzioni per le seguenti funzionalità del cluster:

- Scalabilità
- Autenticazione
- Rete
- Monitoraggio
- Tag

Questa [Guida introduttiva illustra come distribuire un cluster AKS usando il portale di Azure](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Le applicazioni native del cloud possono diventare rapidamente grandi e complesse, con la necessità di eseguire risorse di calcolo significative. In questi scenari, l'intera applicazione non può essere ospitata in un computer di sviluppo, soprattutto in un computer portatile. Azure Dev Spaces è progettato per risolvere questo problema usando AKS. Consente agli sviluppatori di usare una versione locale dei servizi mentre ospita il resto dell'applicazione in un cluster di sviluppo AKS.

Gli sviluppatori condividono un'istanza in esecuzione (sviluppo) in un cluster AKS che contiene l'intera applicazione in contenitori. Ma usano gli spazi personali configurati nel computer per lo sviluppo locale dei servizi. Quando si è pronti, viene testato da end-to-end nel cluster AKS senza replicare le dipendenze. Azure Dev Spaces unisce il codice del computer locale con i servizi in AKS. Gli sviluppatori possono eseguire rapidamente l'iterazione e il debug del codice direttamente in Kubernetes usando Visual Studio o Visual Studio Code.

Per comprendere il valore di Azure Dev Spaces, è possibile condividere questa citazione da Gabe Monroy, lead PM dei contenitori all'Microsoft Azure:

> "Immaginiamo di essere un nuovo dipendente che tenta di correggere un bug in un'applicazione di microservizi complessa costituita da dozzine di componenti, ognuno con la propria configurazione e servizi di supporto. Per iniziare, è necessario configurare l'ambiente di sviluppo locale in modo che possa simulare la produzione, inclusa la configurazione dell'IDE, la creazione della catena di strumenti, le dipendenze dei servizi in contenitori, un ambiente Kubernetes locale, simulazioni per i servizi di supporto e altro ancora. Con il tempo necessario per configurare l'ambiente di sviluppo, la correzione del primo bug potrebbe richiedere giorni.
> In alternativa, è possibile usare gli spazi di sviluppo e AKS ".

Il processo per lavorare con Azure Dev Spaces prevede i passaggi seguenti:

1. Creare lo spazio di sviluppo.
2. Configurare lo spazio di sviluppo radice.
3. Configurare uno spazio di sviluppo figlio (per la propria versione del sistema).
4. Connettersi allo spazio di sviluppo.

Tutti questi passaggi possono essere eseguiti usando l'interfaccia della riga di comando di Azure e i nuovi `azds` strumenti da riga di comando. Ad esempio, per creare un nuovo spazio di sviluppo di Azure per un determinato cluster Kubernetes, usare un comando simile al seguente:

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

Successivamente, è possibile usare il `azds prep` comando per generare le risorse del grafico Docker e Helm necessarie per l'esecuzione dell'applicazione. Eseguire quindi il codice in AKS usando `azds up` . La prima volta che si esegue questo comando, il grafico Helm verrà installato. I contenitori verranno compilati e distribuiti in base alle istruzioni. Questa attività può richiedere alcuni minuti la prima volta che viene eseguita. Tuttavia, dopo avere apportato le modifiche, è possibile connettersi allo spazio di sviluppo figlio usando `azds space select` e quindi distribuire ed eseguire il debug degli aggiornamenti nello spazio di sviluppo figlio isolato. Quando lo spazio di sviluppo è attivo e in esecuzione, è possibile inviare gli aggiornamenti rilasciando il `azds up` comando oppure è possibile usare gli strumenti incorporati in Visual Studio o Visual Studio Code. Con VS Code, è possibile usare il riquadro comandi per connettersi allo spazio di sviluppo. La figura 3-12 illustra come avviare l'applicazione Web usando Azure Dev Spaces in Visual Studio.

![Connettersi a Azure Dev Spaces in Visual Studio ](./media/azure-dev-spaces-visual-studio-launchsettings.png)
 **Figura 3-12**. Connettersi a Azure Dev Spaces in Visual Studio

>[!div class="step-by-step"]
>[Precedente](combine-containers-serverless-approaches.md) 
> [Avanti](scale-containers-serverless.md)
