---
title: Compilare applicazioni ASP.NET Core 2.2 distribuite come contenitori Linux nell'agente nei cluster del servizio Azure Kubernetes
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.date: 02/25/2019
ms.openlocfilehash: ab64a0423ceceb8285c159af276d6d97e12379d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70848750"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Compilare applicazioni ASP.NET Core 2.2 distribuite come contenitori Linux in un agente di orchestrazione del servizio Azure Kubernetes

Servizio Azure Kubernetes (AKS) include i servizi di orchestrazione Kubernetes gestiti di Azure che semplificano la gestione e la distribuzione dei contenitori.

Le funzionalità principali del servizio Azure Kubernetes sono:

- Un piano di controllo ospitato in Azure
- Aggiornamenti automatici
- Riparazione automatica
- Ridimensionamento configurabile dall'utente
- Un'esperienza utente più semplice sia per gli sviluppatori che per gli operatori di cluster.

Negli esempi seguenti viene illustrata la creazione di un'applicazione ASP.NET Core 2.2 che viene eseguita in Linux e distribuita in un cluster del servizio Azure Kubernetes in Azure, mentre lo sviluppo avviene con Visual Studio 2017.

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a>Creazione del progetto ASP.NET Core 2.2 con Visual Studio 2017

ASP.NET Core è una piattaforma di sviluppo generale gestita da Microsoft e dalla community .NET su GitHub. È multipiattaforma, supporta Windows, macOS e Linux e può essere usata in dispositivi, ambienti cloud e scenari IoT/incorporati.

Questo esempio usa un semplice progetto che si basa su un modello API Web di Visual Studio, quindi non occorre alcuna conoscenza aggiuntiva per creare il codice di esempio. È sufficiente creare il progetto usando un modello standard che include tutti gli elementi per eseguire un progetto di piccole dimensioni con un'API REST, con la tecnologia ASP.NET Core 2.2.

![Finestra di aggiunta di un nuovo progetto in Visual Studio, con selezione di un'applicazione Web ASP.NET Core.](media/create-aspnet-core-application.png)

**Figura 4-36**. Creazione di un'applicazione ASP.NET Core

Per creare il progetto di esempio in Visual Studio, selezionare **File** > **nuovo** > **progetto**, selezionare i tipi di progetto **Web** nel riquadro sinistro e **ASP.NETApplicazione Web principale**.

Visual Studio elenca i modelli per i progetti Web. Per questo esempio, selezionare **API** per creare un'applicazione API Web ASP.NET.

Verificare di avere selezionato come framework ASP.NET Core 2.2. .NET core 2.2 è incluso nell'ultima versione di Visual Studio 2017 e viene installato e configurato automaticamente quando si installa Visual Studio 2017.

![Finestra di dialogo di Visual Studio per selezionare il tipo di applicazione Web ASP.NET Core con l'opzione API selezionata.](media/create-web-api-application.png)

**Figura 4-37**. Selezione di ASP.NET CORE 2.2 e del tipo di progetto API Web

Se si ha una versione precedente di .NET Core, è possibile scaricare e installare la versione 2.2 da <https://dotnet.microsoft.com/download>.

È possibile aggiungere il supporto per Docker al momento della creazione del progetto o in seguito, in qualsiasi momento. Per aggiungere il supporto Docker dopo la creazione del progetto, fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e scegliere **Aggiungi** > **supporto Docker** dal menu di scelta rapida.

![Opzione del menu di scelta rapida per aggiungere il supporto Docker a un progetto esistente: fare clic con il pulsante destro del mouse (sul progetto) > Aggiungi > supporto Docker.](media/add-docker-support-to-project.png)

**Figura 4-38**. Aggiunta del supporto per Docker a un progetto esistente

Per completare l'aggiunta del supporto per Docker, è possibile scegliere Windows o Linux. In questo caso, selezionare **Linux**, in quanto il servizio Azure Kubernetes non supporta i contenitori Windows (a partire da fine 2018).

![Finestra di dialogo delle opzioni per selezionare il sistema operativo di destinazione per Dockerfile.](media/select-linux-docker-support.png)

**Figura 4-39**. Selezione dei contenitori Linux.

Bastano questi semplici passaggi per avere un'applicazione ASP.NET Core 2.2 in esecuzione in un contenitore Linux.

Si noti come l'integrazione tra Visual Studio 2017 e Docker è totalmente orientata alla produttività dello sviluppatore.

A questo punto è possibile eseguire l'applicazione premendo **F5** o il pulsante **Esegui**.

Dopo aver eseguito il progetto, è possibile elencare le immagini usando il comando `docker images`. Verrà visualizzata l'immagine `mssampleapplication` creata dalla distribuzione automatica del progetto con Visual Studio 2017.

```console
docker images
```

![L'output della console dal comando docker images mostra un elenco con: Repository, Tag, ID immagine, Creato (data) e Dimensione.](media/docker-images-command.png)

**Figura 4-40**. Visualizzazione immagini Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registrare la soluzione nel Registro Azure Container

Caricare l'immagine in un registro Docker, ad esempio [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) o in Docker Hub, in modo che le immagini possano essere distribuite nel cluster del servizio Azure Kubernetes dal registro. In questo caso l'immagine viene caricata nel Registro Azure Container.

### <a name="create-the-image-in-release-mode"></a>Creare l'immagine in modalità Rilascio

A questo punto viene creata l'immagine in modalità **Rilascio** (pronta per la produzione) modificando l'opzione relativa in **Rilascio**, come illustrato nella figura 4-41, ed eseguendo l'applicazione come in precedenza.

![Opzione della barra degli strumenti in Visual Studio per compilare in modalità di rilascio.](media/select-release-mode.png)

**Figura 4-41**. Selezione della modalità Rilascio

Se si esegue il comando `docker image`, vengono visualizzate entrambe le immagini create, una per la modalità `debug` e l'altra per la modalità `release`.

### <a name="create-a-new-tag-for-the-image"></a>Creare un nuovo tag per l'immagine

Ogni immagine del contenitore deve essere contrassegnata con il nome `loginServer` del registro. Questo tag viene usato per il routing quando si esegue il push delle immagini del contenitore nel registro delle immagini.

È possibile visualizzare il nome `loginServer` dal portale di Azure. L'informazione deriva dal Registro Azure Container.

![Visualizzazione di esplorazione del nome del registro contenitori, in alto a destra.](media/loginServer-name.png)

**Figura 4-42**. Visualizzazione del nome del registro

In alternativa, è possibile eseguire il comando seguente:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Output della console del comando riportato sopra.](media/az-cli-loginServer-name.png)

**Figura 4-43**. Ottenere il nome del registro usando PowerShell

In entrambi i casi, si ottiene il nome. Nell'esempio il nome è `mssampleacr.azurecr.io`.

A questo punto è possibile contrassegnare l'immagine, prendendo l'immagine più recente (modalità Rilascio), con il comando:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Dopo aver eseguito il comando `docker tag`, elencare le immagini con il comando `docker images` che dovrebbe visualizzare l'immagine con il nuovo tag.

![Output della console del comando delle immagini Docker.](media/tagged-docker-images-list.png)

**Figura 4-44**. Visualizzazione di immagini con tag

### <a name="push-the-image-into-the-azure-acr"></a>Eseguire il push dell'immagine nel Registro Azure Container

Accedere al Registro Azure Container

```console
az acr login --name mssampleacr
```

Eseguire il push dell'immagine nel Registro Azure Container usando il comando seguente:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Questo comando richiede un po' di tempo per caricare le immagini, ma offre feedback durante il processo.

![Output della console del comando di push di Docker: visualizza una barra di avanzamento basata su caratteri per ogni livello.](media/uploading-image-to-acr.png)

**Figura 4-45**. Caricamento dell'immagine nel Registro Azure Container

È possibile visualizzare di seguito il risultato che dovrebbe essere visualizzato al termine del processo:

![Output della console del comando di push di Docker, completato, che visualizza tutti i livelli o i nodi.](media/uploading-docker-images-complete.png)

**Figura 4-46**. Visualizzazione dei nodi

Il passaggio successivo consiste nel distribuire il contenitore nel cluster del servizio Azure Kubernetes. A tale scopo, è necessario un file (**file di distribuzione con estensione yml**) che contiene gli elementi seguenti:

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> Per altre informazioni sulla distribuzione con Kubernetes, vedere: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

A questo punto si è quasi pronti per eseguire la distribuzione usando **Kubectl**, ma prima di tutto è necessario ottenere le credenziali per il cluster del servizio Azure Kubernetes con il comando seguente:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Output della console dal comando precedente: Merged "MSSampleK8Cluster as current context in /root/.kube/config](media/getting-aks-credentials.png)

**Figura 4-47**. Ottenere le credenziali

Usare quindi il comando `kubectl create` per avviare la distribuzione.

```console
kubectl create -f mssample-deploy.yml
```

![Output della console del comando riportato sopra: deployment "mssamplesbook" created. service "mssample-kub-app" created.](media/kubectl-create-command.png)

**Figura 4-48**. Eseguire la distribuzione in Kubernetes

Al termine della distribuzione, è possibile accedere alla console di Kubernetes con un proxy locale cui è possibile accedere temporaneamente con il comando seguente:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

In seguito, accedere all'URL `http://127.0.0.1:8001`.

![Visualizzazione di esplorazione del dashboard Kubernetes, che visualizza le distribuzioni, i pod, i set di repliche e i servizi.](media/kubernetes-cluster-information.png)

**Figura 4-49**. Visualizzazione delle informazioni del cluster Kubernetes

L'applicazione è stata distribuita in Azure usando un contenitore Linux e un cluster del servizio Azure Kubernetes. È possibile accedere all'app passando all'indirizzo IP pubblico del servizio, che può essere ottenuto dal portale di Azure.

> [!NOTE]
> Per informazioni su come creare il cluster AKS per questo esempio, vedere la sezione [**Distribuire in servizio Azure Kubernetes**](deploy-azure-kubernetes-service.md) in questa Guida.

>[!div class="step-by-step"]
>[Successivo](set-up-windows-containers-with-powershell.md)
>[precedente](../docker-devops-workflow/index.md)
