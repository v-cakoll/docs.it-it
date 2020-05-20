---
title: Infrastructure as code
description: Adozione dell'infrastruttura come codice (IaC) con applicazioni native del cloud
ms.date: 05/13/2020
ms.openlocfilehash: cfc9e1f0b2733048d5921de5a0400998c282b1fa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613954"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="bf13b-103">Infrastructure as code</span><span class="sxs-lookup"><span data-stu-id="bf13b-103">Infrastructure as code</span></span>

<span data-ttu-id="bf13b-104">I sistemi nativi del cloud comprendono microservizi, contenitori e progettazione di sistemi moderni per ottenere velocità e agilità.</span><span class="sxs-lookup"><span data-stu-id="bf13b-104">Cloud-native systems embrace microservices, containers, and modern system design to achieve speed and agility.</span></span> <span data-ttu-id="bf13b-105">Forniscono fasi di compilazione e rilascio automatizzate per garantire codice coerente e di qualità.</span><span class="sxs-lookup"><span data-stu-id="bf13b-105">They provide automated build and release stages to ensure consistent and quality code.</span></span> <span data-ttu-id="bf13b-106">Ma questa è solo una parte della storia.</span><span class="sxs-lookup"><span data-stu-id="bf13b-106">But, that's only part of the story.</span></span> <span data-ttu-id="bf13b-107">Come si esegue il provisioning degli ambienti cloud su cui vengono eseguiti questi sistemi?</span><span class="sxs-lookup"><span data-stu-id="bf13b-107">How do you provision the cloud environments upon which these systems run?</span></span>

<span data-ttu-id="bf13b-108">Le moderne applicazioni native del cloud adottano la pratica ampiamente accettata dell' [infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)o `IaC` .</span><span class="sxs-lookup"><span data-stu-id="bf13b-108">Modern cloud-native applications embrace the widely accepted practice of [Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), or `IaC`.</span></span>  <span data-ttu-id="bf13b-109">Con IaC è possibile automatizzare il provisioning della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="bf13b-109">With IaC, you automate platform provisioning.</span></span> <span data-ttu-id="bf13b-110">Si applicano essenzialmente procedure di progettazione software come test e controllo delle versioni alle procedure DevOps.</span><span class="sxs-lookup"><span data-stu-id="bf13b-110">You essentially apply software engineering practices such as testing and versioning to your DevOps practices.</span></span> <span data-ttu-id="bf13b-111">L'infrastruttura e le distribuzioni sono automatiche, coerenti e ripetibili.</span><span class="sxs-lookup"><span data-stu-id="bf13b-111">Your infrastructure and deployments are automated, consistent, and repeatable.</span></span> <span data-ttu-id="bf13b-112">Proprio come il recapito continuo automatizzato il modello tradizionale di distribuzioni manuali, l'infrastruttura As code (IaC) sta evolvendo in che modo vengono gestiti gli ambienti applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf13b-112">Just as continuous delivery automated the traditional model of manual deployments, Infrastructure as Code (IaC) is evolving how application environments are managed.</span></span>

<span data-ttu-id="bf13b-113">Strumenti come Azure Resource Manager (ARM), bonifica e l'interfaccia della riga di comando di Azure consentono di creare script in modo dichiarativo dell'infrastruttura cloud necessaria.</span><span class="sxs-lookup"><span data-stu-id="bf13b-113">Tools like Azure Resource Manager (ARM), Terraform, and the Azure Command Line Interface (CLI) enable you to declaratively script the cloud infrastructure you require.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="bf13b-114">Modelli di Gestione risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="bf13b-114">Azure Resource Manager templates</span></span>

<span data-ttu-id="bf13b-115">ARM sta per [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span><span class="sxs-lookup"><span data-stu-id="bf13b-115">ARM stands for [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span></span> <span data-ttu-id="bf13b-116">Si tratta di un motore di provisioning API incorporato in Azure ed esposto come un servizio API.</span><span class="sxs-lookup"><span data-stu-id="bf13b-116">It's an API provisioning engine that is built into Azure and exposed as an API service.</span></span> <span data-ttu-id="bf13b-117">ARM ti permette di distribuire, aggiornare, eliminare e gestire le risorse contenute nel gruppo di risorse di Azure in un'unica operazione coordinata.</span><span class="sxs-lookup"><span data-stu-id="bf13b-117">ARM enables you to deploy, update, delete, and manage the resources contained in Azure resource group in a single, coordinated operation.</span></span> <span data-ttu-id="bf13b-118">Fornire al motore un modello basato su JSON che specifica le risorse necessarie e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf13b-118">You provide the engine with a JSON-based template that specifies the resources you require and their configuration.</span></span> <span data-ttu-id="bf13b-119">ARM Orchestra automaticamente la distribuzione nell'ordine corretto rispettando le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="bf13b-119">ARM automatically orchestrates the deployment in the correct order respecting dependencies.</span></span> <span data-ttu-id="bf13b-120">Il motore garantisce idempotenza.</span><span class="sxs-lookup"><span data-stu-id="bf13b-120">The engine ensures idempotency.</span></span> <span data-ttu-id="bf13b-121">Se una risorsa desiderata esiste già con la stessa configurazione, il provisioning verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="bf13b-121">If a desired resource already exists with the same configuration, provisioning will be ignored.</span></span>

<span data-ttu-id="bf13b-122">Azure Resource Manager modelli sono un linguaggio basato su JSON per la definizione di varie risorse in Azure.</span><span class="sxs-lookup"><span data-stu-id="bf13b-122">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="bf13b-123">Lo schema di base ha un aspetto simile a quello illustrato nella figura 10-14.</span><span class="sxs-lookup"><span data-stu-id="bf13b-123">The basic schema looks something like Figure 10-14.</span></span>

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

<span data-ttu-id="bf13b-124">**Figura 10-14** -schema per un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf13b-124">**Figure 10-14** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="bf13b-125">All'interno di questo modello, è possibile definire un contenitore di archiviazione all'interno della sezione Resources, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bf13b-125">Within this template, one might define a storage container inside the resources section like so:</span></span>

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

<span data-ttu-id="bf13b-126">**Figura 10-15** -esempio di un account di archiviazione definito in un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf13b-126">**Figure 10-15** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="bf13b-127">Un modello ARM può essere parametrizzato con le informazioni di configurazione e l'ambiente dinamico.</span><span class="sxs-lookup"><span data-stu-id="bf13b-127">An ARM template can be parameterized with dynamic environment and configuration information.</span></span> <span data-ttu-id="bf13b-128">In questo modo è possibile riutilizzarlo per definire ambienti diversi, ad esempio sviluppo, controllo di qualità o produzione.</span><span class="sxs-lookup"><span data-stu-id="bf13b-128">Doing so enables it to be reused to define different environments, such as development, QA, or production.</span></span> <span data-ttu-id="bf13b-129">In genere, il modello crea tutte le risorse all'interno di un singolo gruppo di risorse di Azure.</span><span class="sxs-lookup"><span data-stu-id="bf13b-129">Normally, the template creates all resources within a single Azure resource group.</span></span> <span data-ttu-id="bf13b-130">Se necessario, è possibile definire più gruppi di risorse in un singolo modello di Gestione risorse.</span><span class="sxs-lookup"><span data-stu-id="bf13b-130">It's possible to define multiple resource groups in a single Resource Manager template, if needed.</span></span> <span data-ttu-id="bf13b-131">È possibile eliminare tutte le risorse in un ambiente eliminando il gruppo di risorse stesso.</span><span class="sxs-lookup"><span data-stu-id="bf13b-131">You can delete all resources in an environment by deleting the resource group itself.</span></span> <span data-ttu-id="bf13b-132">L'analisi dei costi può essere eseguita anche a livello di gruppo di risorse, consentendo una rapida contabilità della quantità di costi di ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="bf13b-132">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="bf13b-133">Sono disponibili molti esempi o modelli ARM nel progetto di [modelli di avvio rapido di Azure](https://github.com/Azure/azure-quickstart-templates) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="bf13b-133">There are many examples or ARM templates available in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub.</span></span> <span data-ttu-id="bf13b-134">Consentono di accelerare la creazione di un nuovo modello o di modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="bf13b-134">They can help accelerate creating a new template or modifying an existing one.</span></span>

<span data-ttu-id="bf13b-135">I modelli di Gestione risorse possono essere eseguiti in molti modi.</span><span class="sxs-lookup"><span data-stu-id="bf13b-135">Resource Manager templates can be run in many of ways.</span></span> <span data-ttu-id="bf13b-136">Forse il modo più semplice è semplicemente incollarli nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="bf13b-136">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="bf13b-137">Per le distribuzioni sperimentali, questo metodo può essere rapido.</span><span class="sxs-lookup"><span data-stu-id="bf13b-137">For experimental deployments, this method can be quick.</span></span> <span data-ttu-id="bf13b-138">Possono anche essere eseguiti come parte di un processo di compilazione o rilascio in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="bf13b-138">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="bf13b-139">Sono disponibili attività che utilizzeranno le connessioni in Azure per eseguire i modelli.</span><span class="sxs-lookup"><span data-stu-id="bf13b-139">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="bf13b-140">Le modifiche apportate ai modelli Gestione risorse vengono applicate in modo incrementale, vale a dire che per aggiungere una nuova risorsa è sufficiente aggiungerla al modello.</span><span class="sxs-lookup"><span data-stu-id="bf13b-140">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="bf13b-141">Gli strumenti risolveranno le differenze tra le risorse correnti e quelle definite nel modello.</span><span class="sxs-lookup"><span data-stu-id="bf13b-141">The tooling will reconcile differences between the current resources and those defined in the template.</span></span> <span data-ttu-id="bf13b-142">Le risorse verranno quindi create o modificate in modo che corrispondano a quelle definite nel modello.</span><span class="sxs-lookup"><span data-stu-id="bf13b-142">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="bf13b-143">Terraform</span><span class="sxs-lookup"><span data-stu-id="bf13b-143">Terraform</span></span>

<span data-ttu-id="bf13b-144">Le applicazioni native del cloud sono spesso costruite come `cloud agnostic` .</span><span class="sxs-lookup"><span data-stu-id="bf13b-144">Cloud-native applications are often constructed to be `cloud agnostic`.</span></span> <span data-ttu-id="bf13b-145">Il che significa che l'applicazione non è strettamente associata a un particolare fornitore di cloud e può essere distribuita in qualsiasi cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="bf13b-145">Being so means the application isn't tightly coupled to a particular cloud vendor and can be deployed to any public cloud.</span></span>

<span data-ttu-id="bf13b-146">La [bonifica](https://www.terraform.io/) è uno strumento per la creazione di modelli commerciali che consente di effettuare il provisioning di applicazioni native del cloud in tutti i principali lettori cloud: Azure, Google Cloud Platform, AWS e AliCloud.</span><span class="sxs-lookup"><span data-stu-id="bf13b-146">[Terraform](https://www.terraform.io/) is commercial templating tool that can provision cloud-native applications across all the major cloud players: Azure, Google Cloud Platform, AWS, and AliCloud.</span></span> <span data-ttu-id="bf13b-147">Invece di usare JSON come linguaggio di definizione del modello, viene usato il formato YAML leggermente più conciso.</span><span class="sxs-lookup"><span data-stu-id="bf13b-147">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="bf13b-148">Un esempio di file di bonifica che esegue la stessa operazione del modello di Gestione risorse precedente (figura 10-15) è illustrato nella figura 10-16:</span><span class="sxs-lookup"><span data-stu-id="bf13b-148">An example Terraform file that does the same as the previous Resource Manager template (Figure 10-15) is shown in Figure 10-16:</span></span>

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

<span data-ttu-id="bf13b-149">**Figura 10-16** -esempio di un modello di gestione risorse</span><span class="sxs-lookup"><span data-stu-id="bf13b-149">**Figure 10-16** - An example of a Resource Manager template</span></span>

<span data-ttu-id="bf13b-150">La bonifica fornisce anche messaggi di errore intuitivi per i modelli di problema.</span><span class="sxs-lookup"><span data-stu-id="bf13b-150">Terraform also provides intuitive error messages for problem templates.</span></span> <span data-ttu-id="bf13b-151">È disponibile anche un'attività di convalida utile che può essere usata nella fase di compilazione per rilevare tempestivamente gli errori del modello.</span><span class="sxs-lookup"><span data-stu-id="bf13b-151">There's also a handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="bf13b-152">Come per i modelli di Gestione risorse, gli strumenti da riga di comando sono disponibili per la distribuzione di modelli di bonifica.</span><span class="sxs-lookup"><span data-stu-id="bf13b-152">As with Resource Manager templates, command-line tools are available to deploy Terraform templates.</span></span> <span data-ttu-id="bf13b-153">In Azure Pipelines sono inoltre presenti attività create dalla community che possono convalidare e applicare modelli di bonifica.</span><span class="sxs-lookup"><span data-stu-id="bf13b-153">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="bf13b-154">A volte i modelli di bonifica e ARM restituiscono valori significativi, ad esempio una stringa di connessione a un database appena creato.</span><span class="sxs-lookup"><span data-stu-id="bf13b-154">Sometimes Terraform and ARM templates output meaningful values, such as a connection string to a newly created database.</span></span> <span data-ttu-id="bf13b-155">Queste informazioni possono essere acquisite nella pipeline di compilazione e utilizzate nelle attività successive.</span><span class="sxs-lookup"><span data-stu-id="bf13b-155">This information can be captured in the build pipeline and used in subsequent tasks.</span></span>

## <a name="azure-cli-scripts-and-tasks"></a><span data-ttu-id="bf13b-156">Script e attività dell'interfaccia della riga di comando di Azure</span><span class="sxs-lookup"><span data-stu-id="bf13b-156">Azure CLI Scripts and Tasks</span></span>

<span data-ttu-id="bf13b-157">Infine, è possibile usare l' [interfaccia](https://docs.microsoft.com/cli/azure/) della riga di comando di Azure per eseguire lo script dichiarativo dell'infrastruttura cloud.</span><span class="sxs-lookup"><span data-stu-id="bf13b-157">Finally, you can leverage [Azure CLI](https://docs.microsoft.com/cli/azure/) to declaratively script your cloud infrastructure.</span></span> <span data-ttu-id="bf13b-158">È possibile creare, trovare e condividere script dell'interfaccia della riga di comando di Azure per eseguire il provisioning e configurare quasi tutte le risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="bf13b-158">Azure CLI scripts can be created, found, and shared to provision and configure almost any Azure resource.</span></span> <span data-ttu-id="bf13b-159">L'interfaccia della riga di comando è semplice da usare con una curva di apprendimento delicata.</span><span class="sxs-lookup"><span data-stu-id="bf13b-159">The CLI is simple to use with a gentle learning curve.</span></span> <span data-ttu-id="bf13b-160">Gli script vengono eseguiti in PowerShell o bash.</span><span class="sxs-lookup"><span data-stu-id="bf13b-160">Scripts are executed within either PowerShell or Bash.</span></span> <span data-ttu-id="bf13b-161">Sono anche semplici da sottomettere a debug, soprattutto quando vengono confrontati con i modelli ARM.</span><span class="sxs-lookup"><span data-stu-id="bf13b-161">They're also straightforward to debug, especially when compared with ARM templates.</span></span>

<span data-ttu-id="bf13b-162">Gli script dell'interfaccia della riga di comando di Azure funzionano correttamente quando è necessario eliminare e ridistribuire l'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="bf13b-162">Azure CLI scripts work well when you need to tear down and redeploy your infrastructure.</span></span> <span data-ttu-id="bf13b-163">L'aggiornamento di un ambiente esistente può risultare complesso.</span><span class="sxs-lookup"><span data-stu-id="bf13b-163">Updating an existing environment can be tricky.</span></span> <span data-ttu-id="bf13b-164">Molti comandi dell'interfaccia della riga di comando non sono idempotente.</span><span class="sxs-lookup"><span data-stu-id="bf13b-164">Many CLI commands aren't idempotent.</span></span> <span data-ttu-id="bf13b-165">Ciò significa che la risorsa verrà ricreata ogni volta che viene eseguita, anche se la risorsa esiste già.</span><span class="sxs-lookup"><span data-stu-id="bf13b-165">That means they'll recreate the resource each time they're run, even if the resource already exists.</span></span> <span data-ttu-id="bf13b-166">È sempre possibile aggiungere codice che controlla l'esistenza di ogni risorsa prima di crearla.</span><span class="sxs-lookup"><span data-stu-id="bf13b-166">It's always possible to add code that checks for the existence of each resource before creating it.</span></span> <span data-ttu-id="bf13b-167">Tuttavia, in questo modo lo script può diventare gonfio e difficile da gestire.</span><span class="sxs-lookup"><span data-stu-id="bf13b-167">But, doing so, your script can become bloated and difficult to manage.</span></span>

<span data-ttu-id="bf13b-168">Questi script possono essere incorporati anche nelle pipeline DevOps di Azure `Azure CLI tasks` .</span><span class="sxs-lookup"><span data-stu-id="bf13b-168">These scripts can also be embedded in Azure DevOps pipelines as `Azure CLI tasks`.</span></span> <span data-ttu-id="bf13b-169">L'esecuzione della pipeline richiama lo script.</span><span class="sxs-lookup"><span data-stu-id="bf13b-169">Executing the pipeline invokes the script.</span></span>

<span data-ttu-id="bf13b-170">La figura 10-17 Mostra un frammento YAML che elenca la versione dell'interfaccia della riga di comando di Azure e i dettagli della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="bf13b-170">Figure 10-17 shows a YAML snippet that lists the version of Azure CLI and the details of the subscription.</span></span> <span data-ttu-id="bf13b-171">Si noti come i comandi dell'interfaccia della riga di comando di Azure siano inclusi in uno script inline.</span><span class="sxs-lookup"><span data-stu-id="bf13b-171">Note how Azure CLI commands are included in an inline script.</span></span>

```yaml
- task: AzureCLI@2
  displayName: Azure CLI
  inputs:
    azureSubscription: <Name of the Azure Resource Manager service connection>
    scriptType: ps
    scriptLocation: inlineScript
    inlineScript: |
      az --version
      az account show
```

<span data-ttu-id="bf13b-172">**Figura 10-17** -script dell'interfaccia della riga di comando di Azure</span><span class="sxs-lookup"><span data-stu-id="bf13b-172">**Figure 10-17** - Azure CLI script</span></span>

<span data-ttu-id="bf13b-173">In questo articolo, [che cos'è l'infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), l'autore di Sam Guckenheimer descrive in che modo i team che implementano IaC possono fornire ambienti stabili in modo rapido e scalabile.</span><span class="sxs-lookup"><span data-stu-id="bf13b-173">In the article, [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), Author Sam Guckenheimer describes how, "Teams who implement IaC can deliver stable environments rapidly and at scale.</span></span> <span data-ttu-id="bf13b-174">I team evitano la configurazione manuale degli ambienti e impongono la coerenza rappresentando lo stato desiderato dei propri ambienti tramite codice.</span><span class="sxs-lookup"><span data-stu-id="bf13b-174">Teams avoid manual configuration of environments and enforce consistency by representing the desired state of their environments via code.</span></span> <span data-ttu-id="bf13b-175">Le distribuzioni dell'infrastruttura con IaC sono ripetibili ed evitano problemi di runtime causati dalla mancata configurazione o dalle dipendenze mancanti.</span><span class="sxs-lookup"><span data-stu-id="bf13b-175">Infrastructure deployments with IaC are repeatable and prevent runtime issues caused by configuration drift or missing dependencies.</span></span> <span data-ttu-id="bf13b-176">I team DevOps possono collaborare con una serie unificata di procedure e strumenti per distribuire applicazioni e la loro infrastruttura di supporto in modo rapido, affidabile e scalabile ".</span><span class="sxs-lookup"><span data-stu-id="bf13b-176">DevOps teams can work together with a unified set of practices and tools to deliver applications and their supporting infrastructure rapidly, reliably, and at scale."</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bf13b-177">[Precedente](feature-flags.md) 
> [Avanti](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="bf13b-177">[Previous](feature-flags.md)
[Next](application-bundles.md)</span></span>
