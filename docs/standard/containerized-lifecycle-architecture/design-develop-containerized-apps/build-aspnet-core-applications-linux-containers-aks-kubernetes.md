---
title: Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux nel cluster AKS/Kubernetes
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221487"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a>Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux nel servizio contenitore di AZURE/Kubernetes orchestrator

Servizi di Kubernetes Azure (AKS) è managed Kubernetes orchestrazioni i servizi di Azure che semplificano la gestione e distribuzione di contenitori.

Funzionalità principali di servizio contenitore di AZURE sono:

- Un piano di controllo ospitato in Azure
- Aggiornamenti automatici
- Riparazione automatica
- Ridimensionamento configurabile utente
- Un'esperienza utente più semplice per gli sviluppatori e operatori di cluster.

Negli esempi seguenti esplorare la creazione di un'applicazione ASP.NET Core 2.1 che viene eseguito in Linux e distribuisce a un Cluster servizio contenitore di AZURE in Azure, mentre avviene lo sviluppo con Visual Studio 2017.

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a>Creazione progetto ASP.NET Core 2.1 con Visual Studio 2017

ASP.NET Core è una piattaforma di sviluppo generale gestita da Microsoft e dalla community .NET su GitHub. È multipiattaforma, supporta Windows, macOS e Linux e può essere usata su dispositivi, ambienti cloud e scenari IoT/incorporati.

Questo esempio Usa un progetto semplice che si basa basato su un modello API Web di Visual Studio, in modo non occorre alcuna conoscenza aggiuntiva per creare il codice di esempio. È sufficiente creare il progetto usando un modello standard che include tutti gli elementi per eseguire un progetto di piccole dimensioni con un'API REST, mediante la tecnologia di ASP.NET Core 2.1.

![Aggiungi finestra Nuovo progetto in Visual Studio, selezionare l'applicazione Web ASP.NET Core.](media/create-aspnet-core-application.png)

**Figura 4-36**. Creazione di applicazioni ASP.NET Core

Per creare il progetto di esempio, è necessario selezionare **File** > **New** > **progetto** su Visual Studio. Verrà visualizzato un elenco di modelli per diversi tipi di progetto, in cui è necessario cercare **Web** > **.NET Core** nel Pannello di sinistra. Per questo esempio selezionare **applicazione Web ASP.NET Core**.

Nella finestra di dialogo successiva, assicurarsi di aver selezionato .NET Core e ASP.NET Core 2.1 come framework di destinazione nel pulldowns superiore, come illustrato nella figura 4-37 e quindi selezionare l'opzione di API, creare un'applicazione API Web ASP.NET Core.

.NET Core 2.1 è inclusa in Visual Studio 2017 versione 15.7.0 o versione successiva e viene automaticamente installato e configurato automaticamente quando si seleziona il **sviluppo multipiattaforma .NET Core** carico di lavoro durante l'installazione.

![Finestra di Studio Visual per la selezione del tipo di un'applicazione Web ASP.NET Core con l'opzione API selezionata.](media/create-web-api-application.png)

**Figura 4-37**. Tipo di progetto API Web e selezionando ASP.NET CORE 2.1

Se si dispone di qualsiasi versione precedente di .NET Core, è possibile scaricare e installare la versione 2.1 dal <https://www.microsoft.com/net/download/core#/sdk>.

È possibile aggiungere supporto per Docker durante la creazione del progetto nel passaggio precedente, o versione successiva, in caso di necessità dopo l'avvio del progetto. Per aggiungere il supporto per Docker dopo la creazione del progetto, fare doppio clic sul file di progetto nel **Esplora soluzioni** e selezionare **Add** > **supporto Docker** su menu di scelta rapida.

![Opzione di menu di scelta rapida per aggiungere il supporto Docker a un progetto esistente: Fare clic con il pulsante destro (sul progetto) > Aggiungi > supporto Docker.](media/add-docker-support-to-project.png)

**Figura 4-38**. Aggiunta del supporto Docker al progetto esistente

Per completare l'aggiunta del supporto Docker, è possibile scegliere di Windows o Linux. In questo caso, selezionare **Linux**, in quanto servizio contenitore di AZURE non supporta i contenitori di Windows (come di ritardo 2018).

![Finestra di dialogo Opzioni selezionare sistema operativo di destinazione per Dockerfile.](media/select-linux-docker-support.png)

**Figura 4-39**. Se si seleziona contenitori Linux.

Con questi semplici passaggi, si avrà l'applicazione ASP.NET Core 2.1 in esecuzione in un contenitore Linux.

Come può notare, l'integrazione tra Visual Studio 2017 e Docker è totalmente orientato alla produttività dello sviluppatore.

A questo punto è possibile premere **F5** per compilare ed eseguire l'applicazione.

Dopo aver eseguito il progetto, è possibile elencare le immagini usando il `docker images` comando. Verrà visualizzato il `mssampleapplication` immagine creata con la distribuzione automatica del progetto con Visual Studio 2017.

```console
docker images
```

![Console di output del comando di immagini docker, viene visualizzato un elenco con: Repository, Tag, ID immagine, Created (date) e dimensioni.](media/docker-images-command.png)

**Figura 4-40**. Visualizzazione delle immagini Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registrare la soluzione nel registro contenitori di Azure

Caricare l'immagine in un registro Docker, ad esempio [registro contenitori di Azure (ACR)](https://azure.microsoft.com/services/container-registry/) o in Docker Hub in modo che le immagini possono essere distribuite nel cluster AKS da tale registro. In questo caso, si sta caricando l'immagine in Registro contenitori di Azure.

### <a name="create-the-image-in-release-mode"></a>Creare l'immagine in modalità di rilascio

Creare l'immagine nel **rilascio** (pronta per la produzione) in modalità di modifica alla versione come illustrato di seguito e premere F5 per eseguire nuovamente l'applicazione.

![Opzione della barra degli strumenti in Visual Studio per compilare in modalità di rilascio.](media/select-release-mode.png)

**Figura 4-41**. Se si seleziona la modalità di rilascio

Se si esegue il `docker image` comando, si noterà entrambe le immagini create. Uno per `debug` e l'altro per `release` modalità.

### <a name="create-a-new-tag-for-the-image"></a>Creare un nuovo Tag dell'immagine

Ogni immagine del contenitore deve essere contrassegnata con il `loginServer` nome del Registro di sistema. Questo tag viene usato per il routing quando si effettua il push delle immagini del contenitore nel registro delle immagini.

È possibile visualizzare il `loginServer` nome dal portale di Azure, tenuto le informazioni dal registro contenitori di Azure

![Visualizzazione di esplorazione del nome del Registro di sistema del contenitore di Azure, in alto a destra.](media/loginServer-name.png)

**Figura 4-42**. Visualizzazione del nome del Registro di sistema

O eseguendo il comando seguente:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Output del comando precedente della console.](media/az-cli-loginServer-name.png)

**Figura 4-43**. Ottenere il nome del Registro di sistema usando PowerShell

In entrambi i casi, è possibile ottenere il nome. In questo esempio, `mssampleacr.azurecr.io`.

A questo punto è possibile contrassegnare l'immagine, prendendo l'immagine più recente (versione immagine), con il comando seguente:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Dopo aver eseguito il `docker tag` comando, elencare le immagini con il `docker images` comando. Verrà visualizzata l'immagine con il nuovo tag.

![Console di output del comando di immagini docker.](media/tagged-docker-images-list.png)

**Figura 4-44**. Visualizzazione di immagini con tag

### <a name="push-the-image-into-the-azure-acr"></a>Eseguire il push dell'immagine in Registro contenitori di AZURE di Azure

Eseguire il push dell'immagine in Registro contenitori di AZURE Azure, usando il comando seguente:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Questo comando accetta un po' di tempo caricamento delle immagini, ma ti offre commenti e suggerimenti nel processo.

![Console di output del comando di push di docker: mostra un indicatore di stato basato su caratteri per ogni livello.](media/uploading-image-to-acr.png)

**Figura 4-45**. Caricare l'immagine per il registro contenitori di AZURE

È possibile vedere di seguito il risultato che dovrebbe essere visualizzata al termine del processo:

![Output del comando di push di docker, completato, che mostra tutti i livelli o i nodi della console.](media/uploading-docker-images-complete.png)

**Figura 4-46**. Visualizzazione dei nodi

Il passaggio successivo consiste nel distribuire il contenitore nel cluster AKS Kubernetes. Per cui è necessario un file (**yml distribuire file**), in questo caso, contenente:

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
        - mane: mssample-services-app
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

A questo punto è quasi pronti per eseguire la distribuzione usando **Kubectl**, ma prima di tutto è necessario ottenere le credenziali per il Cluster AKS con questo comando:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Console di output del comando precedente: Unito MSSampleK8Cluster"come contesto corrente in /root/.kube/config](media/getting-aks-credentials.png)

**Figura 4-47**. ottenere le credenziali

Usare quindi il `kubectl create` comando per avviare la distribuzione.

```console
kubectl create -f mssample-deploy.yml
```

![Console di output del comando precedente: distribuzione "mssamplesbook" creata. servizio "mssample-kub-app" creata.](media/kubectl-create-command.png)

**Figura 4-48**. Distribuisci in Kubernetes

Al termine della distribuzione, è possibile accedere alla console di Kubernetes con un proxy locale che è possibile accedere temporaneamente con questo comando:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

E l'accesso all'url `http://127.0.0.1:8001`.

![Visualizzazione di esplorazione del dashboard Kubernetes, che mostra le distribuzioni, i POD, set di repliche e i servizi.](media/kubernetes-cluster-information.png)

**Figura 4-49**. Visualizzare le informazioni del cluster Kubernetes

È ora disponibile un'applicazione distribuita in Azure, usando un contenitore Linux e un Kubernetes del Cluster servizio contenitore di AZURE. È possibile accedere all'app di esplorazione per l'indirizzo IP pubblico del servizio, che è possibile ottenere dal portale di Azure.

> [!NOTE]
> È possibile vedere come creare il Cluster AKS per questo esempio nella sezione [ **Distribuisci a Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in questa Guida.

>[!div class="step-by-step"]
>[Precedente](set-up-windows-containers-with-powershell.md)
>[Successivo](../docker-devops-workflow/index.md)
