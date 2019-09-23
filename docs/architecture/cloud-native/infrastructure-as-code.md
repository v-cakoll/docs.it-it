---
title: Infrastruttura come codice
description: Architettura di app .NET cloud native per Azure | Infrastruttura come codice
ms.date: 06/30/2019
ms.openlocfilehash: e395db28bdeff785251b91ed643f9920873d26e8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183014"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="bf29f-103">Infrastruttura come codice</span><span class="sxs-lookup"><span data-stu-id="bf29f-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bf29f-104">Le applicazioni native del cloud tendono a usare tutti i tipi di componenti di piattaforma distribuita come servizio (PaaS).</span><span class="sxs-lookup"><span data-stu-id="bf29f-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="bf29f-105">In una piattaforma cloud come Azure, questi componenti possono includere elementi quali l'archiviazione, il bus di servizio e il servizio SignalR.</span><span class="sxs-lookup"><span data-stu-id="bf29f-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="bf29f-106">Man mano che le applicazioni diventano più complesse, è probabile che il numero di questi servizi in uso aumenti.</span><span class="sxs-lookup"><span data-stu-id="bf29f-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="bf29f-107">Analogamente al modo in cui il recapito continuo ha interrotto manualmente il modello tradizionale di distribuzione in un ambiente, il ritmo rapido delle modifiche ha interrotto anche il modello di gestione degli ambienti in un gruppo IT centralizzato.</span><span class="sxs-lookup"><span data-stu-id="bf29f-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="bf29f-108">Gli ambienti di compilazione possono anche essere automatizzati.</span><span class="sxs-lookup"><span data-stu-id="bf29f-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="bf29f-109">È disponibile un'ampia gamma di strumenti ben congegnati che consentono di semplificare il processo.</span><span class="sxs-lookup"><span data-stu-id="bf29f-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="bf29f-110">Modelli di Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="bf29f-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="bf29f-111">Azure Resource Manager modelli sono un linguaggio basato su JSON per la definizione di varie risorse in Azure.</span><span class="sxs-lookup"><span data-stu-id="bf29f-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="bf29f-112">Lo schema di base ha un aspetto simile a quello illustrato nella figura 11-10.</span><span class="sxs-lookup"><span data-stu-id="bf29f-112">The basic schema looks something like Figure 11-10.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="bf29f-113">**Figura 11-10** -schema per un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf29f-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="bf29f-114">All'interno di questo modello, è possibile definire un contenitore di archiviazione all'interno della sezione Resources, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bf29f-114">Within this template, one might define a storage container inside the resources section like so:</span></span>
 
```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="bf29f-115">**Figura 11-11** -esempio di un account di archiviazione definito in un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf29f-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="bf29f-116">I modelli possono essere parametrizzati in modo che un modello possa essere riutilizzato con impostazioni diverse per definire gli ambienti di sviluppo, controllo di qualità e produzione.</span><span class="sxs-lookup"><span data-stu-id="bf29f-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="bf29f-117">Questo consente di eliminare le sorprese quando si esegue la migrazione a un ambiente più elevato configurato in modo diverso dagli ambienti inferiori.</span><span class="sxs-lookup"><span data-stu-id="bf29f-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="bf29f-118">Le risorse definite in un modello vengono in genere create all'interno di un singolo gruppo di risorse in Azure. è possibile definire più gruppi di risorse in un singolo modello di Gestione risorse ma insolito).</span><span class="sxs-lookup"><span data-stu-id="bf29f-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="bf29f-119">In questo modo è molto semplice eliminare un ambiente semplicemente eliminando il gruppo di risorse nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="bf29f-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="bf29f-120">L'analisi dei costi può essere eseguita anche a livello di gruppo di risorse, consentendo una rapida contabilità della quantità di costi di ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="bf29f-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="bf29f-121">Sono disponibili molti modelli di esempio definiti nel progetto di [modelli di avvio rapido di Azure](https://github.com/Azure/azure-quickstart-templates) su GitHub che conferiscono un piede quando si inizia con un nuovo modello o se ne aggiunge uno esistente.</span><span class="sxs-lookup"><span data-stu-id="bf29f-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="bf29f-122">I modelli di Gestione risorse possono essere eseguiti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="bf29f-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="bf29f-123">Forse il modo più semplice è semplicemente incollarli nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="bf29f-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="bf29f-124">Per le distribuzioni sperimentali, questo metodo può essere molto rapido.</span><span class="sxs-lookup"><span data-stu-id="bf29f-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="bf29f-125">Possono anche essere eseguiti come parte di un processo di compilazione o rilascio in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="bf29f-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="bf29f-126">Sono disponibili attività che utilizzeranno le connessioni in Azure per eseguire i modelli.</span><span class="sxs-lookup"><span data-stu-id="bf29f-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="bf29f-127">Le modifiche apportate ai modelli Gestione risorse vengono applicate in modo incrementale, vale a dire che per aggiungere una nuova risorsa è sufficiente aggiungerla al modello.</span><span class="sxs-lookup"><span data-stu-id="bf29f-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="bf29f-128">Gli strumenti gestiranno le differenze tra il gruppo di risorse corrente e il gruppo di risorse desiderato definito nel modello.</span><span class="sxs-lookup"><span data-stu-id="bf29f-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="bf29f-129">Le risorse verranno quindi create o modificate in modo che corrispondano a quelle definite nel modello.</span><span class="sxs-lookup"><span data-stu-id="bf29f-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="bf29f-130">Terraform</span><span class="sxs-lookup"><span data-stu-id="bf29f-130">Terraform</span></span>

<span data-ttu-id="bf29f-131">Uno svantaggio percepito dei modelli di Gestione risorse è che sono specifici del cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="bf29f-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="bf29f-132">È insolito creare applicazioni che includono risorse da più di un cloud, ma nei casi in cui l'azienda si basa su tempi di attività spettacolari, potrebbe essere utile il costo del supporto di più cloud.</span><span class="sxs-lookup"><span data-stu-id="bf29f-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="bf29f-133">Se era disponibile un linguaggio di modello che poteva essere usato in ogni cloud, le competenze degli sviluppatori sarebbero molto più portabili.</span><span class="sxs-lookup"><span data-stu-id="bf29f-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="bf29f-134">Sono disponibili diverse tecnologie.</span><span class="sxs-lookup"><span data-stu-id="bf29f-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="bf29f-135">L'offerta più matura nello spazio è nota come [bonifica](https://www.terraform.io/).</span><span class="sxs-lookup"><span data-stu-id="bf29f-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="bf29f-136">La bonifica supporta tutti i principali player cloud, ad esempio Azure, Google Cloud Platform, AWS e AliCloud, e supporta anche dozzine di giocatori secondari, ad esempio Heroku e DigitalOcean.</span><span class="sxs-lookup"><span data-stu-id="bf29f-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="bf29f-137">Invece di usare JSON come linguaggio di definizione del modello, viene usato il formato YAML leggermente più conciso.</span><span class="sxs-lookup"><span data-stu-id="bf29f-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span> 

<span data-ttu-id="bf29f-138">Un esempio di file di bonifica che esegue la stessa operazione del modello di Gestione risorse precedente (Figura 11-11) è illustrato nella figura 11-12:</span><span class="sxs-lookup"><span data-stu-id="bf29f-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="bf29f-139">**Figura 11-12** -esempio di un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf29f-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="bf29f-140">La bonifica è un processo migliore per fornire messaggi di errore sensibili quando una risorsa non può essere distribuita a causa di un errore nel modello.</span><span class="sxs-lookup"><span data-stu-id="bf29f-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="bf29f-141">Si tratta di un'area in cui i modelli di Gestione risorse presentano alcune problemi.</span><span class="sxs-lookup"><span data-stu-id="bf29f-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="bf29f-142">È disponibile anche un'attività di convalida molto utile che può essere usata nella fase di compilazione per rilevare tempestivamente gli errori del modello.</span><span class="sxs-lookup"><span data-stu-id="bf29f-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="bf29f-143">Come per i modelli di Gestione risorse, sono disponibili strumenti da riga di comando che possono essere usati per distribuire modelli di bonifica.</span><span class="sxs-lookup"><span data-stu-id="bf29f-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="bf29f-144">In Azure Pipelines sono inoltre presenti attività create dalla community che possono convalidare e applicare modelli di bonifica.</span><span class="sxs-lookup"><span data-stu-id="bf29f-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="bf29f-145">Nel caso in cui il modello di bonifica o Gestione risorse restituisca valori interessanti, ad esempio la stringa di connessione a un database appena creato, è possibile acquisirli nella pipeline di compilazione e usarli nelle attività successive.</span><span class="sxs-lookup"><span data-stu-id="bf29f-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bf29f-146">[Precedente](devops.md)
>[Successivo](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="bf29f-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>
