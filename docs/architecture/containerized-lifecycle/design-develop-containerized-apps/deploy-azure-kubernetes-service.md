---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Informazioni su come distribuire un'app usando il servizio Azure Kubernetes.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182367"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="a5a3e-103">Distribuire nel servizio Azure Kubernetes</span><span class="sxs-lookup"><span data-stu-id="a5a3e-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="a5a3e-104">È possibile interagire con il servizio Azure Kubernetes usando il sistema operativo client preferito. Di seguito viene illustrato come eseguire tale interazione con Microsoft Windows e con una versione incorporata di Ubuntu Linux in Windows tramite comandi Bash.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="a5a3e-105">Prerequisiti per l'uso del servizio Azure Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="a5a3e-106">Computer di sviluppo Linux o Mac</span><span class="sxs-lookup"><span data-stu-id="a5a3e-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="a5a3e-107">Computer di sviluppo Windows</span><span class="sxs-lookup"><span data-stu-id="a5a3e-107">Windows development machine</span></span>
  - <span data-ttu-id="a5a3e-108">Modalità sviluppatore abilitata in Windows</span><span class="sxs-lookup"><span data-stu-id="a5a3e-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="a5a3e-109">Sottosistema Windows per Linux</span><span class="sxs-lookup"><span data-stu-id="a5a3e-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="a5a3e-110">Interfaccia della riga di comando di Azure installata in [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span><span class="sxs-lookup"><span data-stu-id="a5a3e-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span></span>

> [!NOTE]
> <span data-ttu-id="a5a3e-111">Per informazioni complete su:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-111">To find complete information about:</span></span>
>
> <span data-ttu-id="a5a3e-112">Interfaccia della riga di comando di Azure: <https://docs.microsoft.com/cli/azure/index></span><span class="sxs-lookup"><span data-stu-id="a5a3e-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span></span>
>
> <span data-ttu-id="a5a3e-113">Sottosistema Windows per Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="a5a3e-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="a5a3e-114">Creare l'ambiente del servizio Azure Kubernetes in Azure</span><span class="sxs-lookup"><span data-stu-id="a5a3e-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="a5a3e-115">Esistono diversi modi per creare l'ambiente del servizio Azure Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="a5a3e-116">È possibile usare comandi dell'interfaccia della riga di comando di Azure o il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="a5a3e-117">In questo articolo sono disponibili alcuni esempi di uso dell'interfaccia della riga di comando di Azure per creare il cluster e del portale di Azure per esaminare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="a5a3e-118">È anche necessario avere Kubectl e Docker nel computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="a5a3e-119">Creare il cluster del servizio Azure Kubernetes</span><span class="sxs-lookup"><span data-stu-id="a5a3e-119">Create the AKS cluster</span></span>

<span data-ttu-id="a5a3e-120">Creare il cluster del servizio Azure Kubernetes usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="a5a3e-121">Al termine del processo di creazione, è possibile visualizzare il servizio Azure Kubernetes nel portale di Azure:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="a5a3e-122">Gruppo di risorse:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-122">The resource group:</span></span>

![Visualizzazione nel browser del gruppo di risorse del servizio Azure Kubernetes.](media/aks-resource-group-view.png)

<span data-ttu-id="a5a3e-124">**Figura 4-17**.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-124">**Figure 4-17**.</span></span> <span data-ttu-id="a5a3e-125">Visualizzazione del gruppo di risorse del servizio Azure Kubernetes da Azure.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="a5a3e-126">Cluster del servizio Azure Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-126">The AKS cluster:</span></span>

![Visualizzazione nel browser di un gruppo di risorse del servizio Azure Kubernetes.](media/aks-cluster-view.png)

<span data-ttu-id="a5a3e-128">**Figura 4-18**.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-128">**Figure 4-18**.</span></span> <span data-ttu-id="a5a3e-129">Visualizzazione del servizio Azure Kubernetes da Azure.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-129">AKS view from Azure.</span></span>

<span data-ttu-id="a5a3e-130">È anche possibile visualizzare il nodo creato usando `Azure-CLI` e `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="a5a3e-131">Ottenere prima di tutto le credenziali:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Output della console del comando precedente: Merged "MsSampleK8Cluster as current context in /root/.kube/config.](media/get-credentials-command-result.png)

<span data-ttu-id="a5a3e-133">**Figura 4-19**.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-133">**Figure 4-19**.</span></span> <span data-ttu-id="a5a3e-134">Risultato del comando `aks get-credentials`.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="a5a3e-135">E quindi recupero dei nodi da Kubectl:</span><span class="sxs-lookup"><span data-stu-id="a5a3e-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Output della console del comando precedente: Elenco di nodi con stato, età (tempo di esecuzione) e versione](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="a5a3e-137">**Figura 4-20**.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-137">**Figure 4-20**.</span></span> <span data-ttu-id="a5a3e-138">Risultato del comando `kubectl get nodes`.</span><span class="sxs-lookup"><span data-stu-id="a5a3e-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a5a3e-139">[Precedente](orchestrate-high-scalability-availability.md)
>[Successivo](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a5a3e-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
