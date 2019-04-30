---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Informazioni su come distribuire un'app usando Azure Kubernetes Service.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006543"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="53ea5-103">Distribuire nel servizio Azure Kubernetes</span><span class="sxs-lookup"><span data-stu-id="53ea5-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="53ea5-104">È possibile interagire con servizio contenitore di AZURE usando il sistema operativo client preferito, di seguito viene illustrato come farlo con Microsoft Windows e una versione incorporata di Ubuntu Linux in Windows, usando i comandi Bash.</span><span class="sxs-lookup"><span data-stu-id="53ea5-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="53ea5-105">Prerequisiti per poter prima di usare servizio contenitore di AZURE sono:</span><span class="sxs-lookup"><span data-stu-id="53ea5-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="53ea5-106">Computer di sviluppo Linux o Mac</span><span class="sxs-lookup"><span data-stu-id="53ea5-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="53ea5-107">Computer di sviluppo Windows</span><span class="sxs-lookup"><span data-stu-id="53ea5-107">Windows development machine</span></span>
  - <span data-ttu-id="53ea5-108">Abilitata in Windows la modalità sviluppatore</span><span class="sxs-lookup"><span data-stu-id="53ea5-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="53ea5-109">Sottosistema Windows per Linux</span><span class="sxs-lookup"><span data-stu-id="53ea5-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="53ea5-110">Azure-CLI installato in [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="53ea5-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="53ea5-111">Per informazioni complete su:</span><span class="sxs-lookup"><span data-stu-id="53ea5-111">To find complete information about:</span></span>
>
> <span data-ttu-id="53ea5-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="53ea5-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="53ea5-113">Sottosistema Windows per Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="53ea5-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="53ea5-114">Creare l'ambiente del servizio contenitore di AZURE in Azure</span><span class="sxs-lookup"><span data-stu-id="53ea5-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="53ea5-115">Esistono diversi modi per creare l'ambiente del servizio contenitore di AZURE.</span><span class="sxs-lookup"><span data-stu-id="53ea5-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="53ea5-116">Si può essere eseguito usando i comandi CLI di Azure o tramite il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="53ea5-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="53ea5-117">È possibile esaminare alcuni esempi tramite la CLI di Azure per creare il cluster e il portale di Azure per esaminare i risultati.</span><span class="sxs-lookup"><span data-stu-id="53ea5-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="53ea5-118">È anche necessario avere Kubectl e Docker nel computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="53ea5-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="53ea5-119">Creare il cluster AKS</span><span class="sxs-lookup"><span data-stu-id="53ea5-119">Create the AKS cluster</span></span>

<span data-ttu-id="53ea5-120">Creare il cluster AKS usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="53ea5-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="53ea5-121">Al termine del processo di creazione, è possibile visualizzare il servizio contenitore di AZURE creato nel portale di Azure:</span><span class="sxs-lookup"><span data-stu-id="53ea5-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="53ea5-122">Il gruppo di risorse:</span><span class="sxs-lookup"><span data-stu-id="53ea5-122">The resource group:</span></span>

![Visualizzazione di esplorazione del gruppo di risorse di Azure AKS.](media/aks-resource-group-view.png)

<span data-ttu-id="53ea5-124">**Figura 4-17**.</span><span class="sxs-lookup"><span data-stu-id="53ea5-124">**Figure 4-17**.</span></span> <span data-ttu-id="53ea5-125">Visualizzazione del gruppo di risorse AKS da Azure.</span><span class="sxs-lookup"><span data-stu-id="53ea5-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="53ea5-126">Il cluster AKS:</span><span class="sxs-lookup"><span data-stu-id="53ea5-126">The AKS cluster:</span></span>

![Visualizzazione di esplorazione di un gruppo di risorse del servizio contenitore di AZURE.](media/aks-cluster-view.png)

<span data-ttu-id="53ea5-128">**Figura 4-18**.</span><span class="sxs-lookup"><span data-stu-id="53ea5-128">**Figure 4-18**.</span></span> <span data-ttu-id="53ea5-129">Visualizzazione AKS da Azure.</span><span class="sxs-lookup"><span data-stu-id="53ea5-129">AKS view from Azure.</span></span>

<span data-ttu-id="53ea5-130">È anche possibile visualizzare il nodo creato usando `Azure-CLI` e `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="53ea5-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="53ea5-131">Innanzitutto, ottenere le credenziali:</span><span class="sxs-lookup"><span data-stu-id="53ea5-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Console di output del comando precedente: Unita "MsSampleK8Cluster come contesto corrente in /root/.kube/config.](media/get-credentials-command-result.png)

<span data-ttu-id="53ea5-133">**Figura 4-19**.</span><span class="sxs-lookup"><span data-stu-id="53ea5-133">**Figure 4-19**.</span></span> <span data-ttu-id="53ea5-134">`aks get-credentials` risultato di comando.</span><span class="sxs-lookup"><span data-stu-id="53ea5-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="53ea5-135">E allora, recupero di nodi da Kubectl:</span><span class="sxs-lookup"><span data-stu-id="53ea5-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Console di output dal comando precedente: Elenco di nodi con stato, l'età (tempo di esecuzione) e versione](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="53ea5-137">**Figura 4-20**.</span><span class="sxs-lookup"><span data-stu-id="53ea5-137">**Figure 4-20**.</span></span> <span data-ttu-id="53ea5-138">`kubectl get nodes` risultato di comando.</span><span class="sxs-lookup"><span data-stu-id="53ea5-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="53ea5-139">[Precedente](orchestrate-high-scalability-availability.md)
>[Successivo](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="53ea5-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
