---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Informazioni su come distribuire un'app usando Azure Kubernetes Service.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664965"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Distribuire in Azure Kubernetes Service (AKS)

È possibile interagire con servizio contenitore di AZURE usando il sistema operativo client preferito, di seguito viene illustrato come farlo con Microsoft Windows e una versione incorporata di Ubuntu Linux in Windows, usando i comandi Bash.

Prerequisiti per poter prima di usare servizio contenitore di AZURE sono:

- Computer di sviluppo Linux o Mac
- Computer di sviluppo Windows
  - Abilitata in Windows la modalità sviluppatore
  - Sottosistema Windows per Linux
- Azure-CLI installato in [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> Per informazioni complete su:
>
> Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Sottosistema Windows per Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Creare l'ambiente del servizio contenitore di AZURE in Azure

Esistono diversi modi per creare l'ambiente del servizio contenitore di AZURE. Si può essere eseguito usando i comandi CLI di Azure o tramite il portale di Azure.

È possibile esaminare alcuni esempi tramite la CLI di Azure per creare il cluster e il portale di Azure per esaminare i risultati. È anche necessario avere Kubectl e Docker nel computer di sviluppo.  

## <a name="create-the-aks-cluster"></a>Creare il cluster AKS

Creare il cluster AKS usando questo comando:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Al termine del processo di creazione, è possibile visualizzare il servizio contenitore di AZURE creato nel portale di Azure:

Il gruppo di risorse:

![Visualizzazione di esplorazione del gruppo di risorse di Azure AKS.](media/aks-resource-group-view.png)

**Figura 4-17**. Visualizzazione del gruppo di risorse AKS da Azure.

Il cluster AKS:

![Visualizzazione di esplorazione di un gruppo di risorse del servizio contenitore di AZURE.](media/aks-cluster-view.png)

**Figura 4-18**. Visualizzazione AKS da Azure.

È anche possibile visualizzare il nodo creato usando `Azure-CLI` e `Kubectl`.

Innanzitutto, ottenere le credenziali:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Console di output del comando precedente: Unita "MsSampleK8Cluster come contesto corrente in /root/.kube/config.](media/get-credentials-command-result.png)

**Figura 4-19**. `aks get-credentials` risultato di comando.

E allora, recupero di nodi da Kubectl:

```console
kubectl get nodes
```

![Console di output dal comando precedente: Elenco di nodi con stato, l'età (tempo di esecuzione) e versione](media/kubectl-get-nodes-command-result.png)

**Figura 4-20**. `kubectl get nodes` risultato di comando.

>[!div class="step-by-step"]
>[Precedente](orchestrate-high-scalability-availability.md)
>[Successivo](docker-apps-development-environment.md)
