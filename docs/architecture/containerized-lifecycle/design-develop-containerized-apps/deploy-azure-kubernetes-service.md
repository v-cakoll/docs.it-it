---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Informazioni su come distribuire un'app usando il servizio Azure Kubernetes.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71182367"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Distribuire nel servizio Azure Kubernetes

È possibile interagire con il servizio Azure Kubernetes usando il sistema operativo client preferito. Di seguito viene illustrato come eseguire tale interazione con Microsoft Windows e con una versione incorporata di Ubuntu Linux in Windows tramite comandi Bash.

Prerequisiti per l'uso del servizio Azure Kubernetes:

- Computer di sviluppo Linux o Mac
- Computer di sviluppo Windows
  - Modalità sviluppatore abilitata in Windows
  - Sottosistema di Windows per Linux
- Interfaccia della riga di comando di Azure installata in [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)

> [!NOTE]
> Per informazioni complete su:
>
> Interfaccia della riga di comando di Azure: <https://docs.microsoft.com/cli/azure/index>
>
> Sottosistema Windows per Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Creare l'ambiente del servizio Azure Kubernetes in Azure

Esistono diversi modi per creare l'ambiente del servizio Azure Kubernetes. È possibile usare comandi dell'interfaccia della riga di comando di Azure o il portale di Azure.

In questo articolo sono disponibili alcuni esempi di uso dell'interfaccia della riga di comando di Azure per creare il cluster e del portale di Azure per esaminare i risultati. È anche necessario avere Kubectl e Docker nel computer di sviluppo.  

## <a name="create-the-aks-cluster"></a>Creare il cluster del servizio Azure Kubernetes

Creare il cluster del servizio Azure Kubernetes usando questo comando:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Al termine del processo di creazione, è possibile visualizzare il servizio Azure Kubernetes nel portale di Azure:

Gruppo di risorse:

![Visualizzazione nel browser del gruppo di risorse del servizio Azure Kubernetes.](media/aks-resource-group-view.png)

**Figura 4-17**. Visualizzazione del gruppo di risorse del servizio Azure Kubernetes da Azure.

Cluster del servizio Azure Kubernetes:

![Visualizzazione nel browser di un gruppo di risorse del servizio Azure Kubernetes.](media/aks-cluster-view.png)

**Figura 4-18**. Visualizzazione del servizio Azure Kubernetes da Azure.

È anche possibile visualizzare il nodo creato usando `Azure-CLI` e `Kubectl`.

Ottenere prima di tutto le credenziali:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Output della console dal comando precedente: Merged "MsSampleK8Cluster as current context in /root/.kube/config.](media/get-credentials-command-result.png)

**Figura 4-19**. Risultato del comando `aks get-credentials`.

E quindi recupero dei nodi da Kubectl:

```console
kubectl get nodes
```

![Comando Output della console dall'alto: elenco di nodi con stato, età (tempo di esecuzione) e versione](media/kubectl-get-nodes-command-result.png)

**Figura 4-20**. Risultato del comando `kubectl get nodes`.

>[!div class="step-by-step"]
>[Successivo](orchestrate-high-scalability-availability.md)
>[precedente](docker-apps-development-environment.md)
