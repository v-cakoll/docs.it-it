---
title: Aggregazioni di applicazioni cloud native
description: Architettura di app .NET cloud native per Azure | Bundle di applicazioni native cloud
ms.date: 05/13/2020
ms.openlocfilehash: fc6ee96078650dccd2ebeb3e65a0a00c4e05ecdb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614344"
---
# <a name="cloud-native-application-bundles"></a><span data-ttu-id="ecd6a-103">Aggregazioni di applicazioni cloud native</span><span class="sxs-lookup"><span data-stu-id="ecd6a-103">Cloud Native Application Bundles</span></span>

<span data-ttu-id="ecd6a-104">Una proprietà chiave delle applicazioni native del cloud è la possibilità di sfruttare le funzionalità del cloud per velocizzare lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-104">A key property of cloud-native applications is that they leverage the capabilities of the cloud to speed up development.</span></span> <span data-ttu-id="ecd6a-105">Questa progettazione spesso significa che un'applicazione completa utilizza diversi tipi di tecnologie.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-105">This design often means that a full application uses different kinds of technologies.</span></span> <span data-ttu-id="ecd6a-106">Le applicazioni possono essere fornite in contenitori Docker, alcuni servizi possono usare funzioni di Azure, mentre altre parti possono essere eseguite direttamente in macchine virtuali allocate su server metal di grandi dimensioni con accelerazione GPU hardware.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-106">Applications may be shipped in Docker containers, some services may use Azure Functions, while other parts may run directly on virtual machines allocated on large metal servers with hardware GPU acceleration.</span></span> <span data-ttu-id="ecd6a-107">Non esistono due applicazioni native del cloud, pertanto è difficile fornire un singolo meccanismo per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-107">No two cloud-native applications are the same, so it's been difficult to provide a single mechanism for shipping them.</span></span>

<span data-ttu-id="ecd6a-108">I contenitori Docker possono essere eseguiti in Kubernetes usando un grafico Helm per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-108">The Docker containers may run on Kubernetes using a Helm Chart for deployment.</span></span> <span data-ttu-id="ecd6a-109">Le funzioni di Azure possono essere allocate usando i modelli di bonifica.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-109">The Azure Functions may be allocated using Terraform templates.</span></span> <span data-ttu-id="ecd6a-110">Infine, le macchine virtuali possono essere allocate usando la funzionalità di bonifica, ma con Ansible.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-110">Finally, the virtual machines may be allocated using Terraform but built out using Ansible.</span></span> <span data-ttu-id="ecd6a-111">Si tratta di una vasta gamma di tecnologie e non è stato possibile comprimere tutti i pacchetti in un pacchetto ragionevole.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-111">This is a whole mess of technologies and there has been no way to package them all together into a reasonable package.</span></span> <span data-ttu-id="ecd6a-112">Fino ad ora.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-112">Until now.</span></span>

<span data-ttu-id="ecd6a-113">I bundle di applicazioni native cloud (CNABs) sono uno sforzo comune da parte di diverse società, ad esempio Microsoft, Docker e HashiCorp, per sviluppare una specifica per la creazione di pacchetti di applicazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-113">Cloud Native Application Bundles (CNABs) are a joint effort by a number of community-minded companies such as Microsoft, Docker, and HashiCorp to develop a specification to package distributed applications.</span></span>

<span data-ttu-id="ecd6a-114">Il lavoro richiesto è stato annunciato nel dicembre del 2018, pertanto c'è ancora un bel po' di lavoro da fare per esporre il lavoro richiesto alla maggior parte della community.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-114">The effort was announced in December of 2018, so there's still a fair bit of work to do to expose the effort to the greater community.</span></span> <span data-ttu-id="ecd6a-115">Tuttavia, esiste già una [specifica aperta](https://github.com/deislabs/cnab-spec) e un'implementazione di riferimento nota come [borsone](https://duffle.sh/).</span><span class="sxs-lookup"><span data-stu-id="ecd6a-115">However, there's already an [open specification](https://github.com/deislabs/cnab-spec) and a reference implementation known as [Duffle](https://duffle.sh/).</span></span> <span data-ttu-id="ecd6a-116">Questo strumento, scritto in go, è un lavoro comune tra Docker e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-116">This tool, which was written in Go, is a joint effort between Docker and Microsoft.</span></span>

<span data-ttu-id="ecd6a-117">CNABs può contenere diversi tipi di tecnologie di installazione.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-117">The CNABs can contain different kinds of installation technologies.</span></span> <span data-ttu-id="ecd6a-118">Ciò consente di coesistere nello stesso pacchetto elementi quali grafici Helm, modelli di bonifica e PlayBook Ansible.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-118">This allows things like Helm Charts, Terraform templates, and Ansible Playbooks to coexist in the same package.</span></span> <span data-ttu-id="ecd6a-119">Una volta creati, i pacchetti sono indipendenti e portabili; possono essere installati da una chiavetta USB.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-119">Once built, the packages are self-contained and portable; they can be installed from a USB stick.</span></span>  <span data-ttu-id="ecd6a-120">I pacchetti sono firmati in modo crittografico per assicurarsi che provengano dall'entità che attestano.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-120">The packages are cryptographically signed to ensure they originate from the party they claim.</span></span>

<span data-ttu-id="ecd6a-121">Il nucleo di un CNAB è un file denominato `bundle.json` .</span><span class="sxs-lookup"><span data-stu-id="ecd6a-121">The core of a CNAB is a file called `bundle.json`.</span></span> <span data-ttu-id="ecd6a-122">Questo file definisce il contenuto del bundle, ovvero le immagini o qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-122">This file defines the contents of the bundle, be they Terraform or images or anything else.</span></span> <span data-ttu-id="ecd6a-123">Nella figura 11-9 è definito un CNAB che richiama un po' di bonifica.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-123">Figure 11-9 defines a CNAB that invokes some Terraform.</span></span> <span data-ttu-id="ecd6a-124">Si noti, tuttavia, che definisce effettivamente un'immagine di chiamata usata per richiamare la bonifica.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-124">Notice, however, that it actually defines an invocation image that is used to invoke the Terraform.</span></span> <span data-ttu-id="ecd6a-125">Quando si crea un pacchetto, il file Docker che si trova nella directory *CNAB* è incorporato in un'immagine Docker, che verrà inclusa nel bundle.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-125">When packaged up, the Docker file that is located in the *cnab* directory is built into a Docker image, which will be included in the bundle.</span></span> <span data-ttu-id="ecd6a-126">Se la gestione dei contenitori è installata in un contenitore Docker nel bundle, non è necessario che gli utenti dispongano di un sistema di gestione delle risorse installato nel computer per eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-126">Having Terraform installed inside a Docker container in the bundle means that users don't need to have Terraform installed on their machine to run the bundling.</span></span>

```json
{
    "name": "terraform",
    "version": "0.1.0",
    "schemaVersion": "v1.0.0-WD",
    "parameters": {
        "backend": {
            "type": "boolean",
            "defaultValue": false,
            "destination": {
                "env": "TF_VAR_backend"
            }
        }
    },
    "invocationImages": [
        {
        "imageType": "docker",
        "image": "cnab/terraform:latest"
        }
    ],
    "credentials": {
        "tenant_id": {
            "env": "TF_VAR_tenant_id"
        },
        "client_id": {
            "env": "TF_VAR_client_id"
        },
        "client_secret": {
            "env": "TF_VAR_client_secret"
        },
        "subscription_id": {
            "env": "TF_VAR_subscription_id"
        },
        "ssh_authorized_key": {
            "env": "TF_VAR_ssh_authorized_key"
        }
    },
    "actions": {
        "status": {
            "modifies": true
        }
    }
}
```

<span data-ttu-id="ecd6a-127">**Figura 10-18** -un file di esempio di bonifica</span><span class="sxs-lookup"><span data-stu-id="ecd6a-127">**Figure 10-18** - An example Terraform file</span></span>

<span data-ttu-id="ecd6a-128">`bundle.json`Definisce anche un set di parametri che vengono passati nella bonifica.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-128">The `bundle.json` also defines a set of parameters that are passed down into the Terraform.</span></span> <span data-ttu-id="ecd6a-129">La parametrizzazione del bundle consente l'installazione in un'ampia gamma di ambienti diversi.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-129">Parameterization of the bundle allows for installation in a variety of different environments.</span></span>

<span data-ttu-id="ecd6a-130">Anche il formato CNAB è flessibile e può essere usato in qualsiasi cloud.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-130">The CNAB format is also flexible, allowing it to be used against any cloud.</span></span> <span data-ttu-id="ecd6a-131">Può anche essere usato con soluzioni locali, ad esempio [OpenStack](https://www.openstack.org/).</span><span class="sxs-lookup"><span data-stu-id="ecd6a-131">It can even be used against on-premises solutions such as [OpenStack](https://www.openstack.org/).</span></span>

## <a name="devops-decisions"></a><span data-ttu-id="ecd6a-132">Decisioni DevOps</span><span class="sxs-lookup"><span data-stu-id="ecd6a-132">DevOps Decisions</span></span>

<span data-ttu-id="ecd6a-133">Ci sono così tanti strumenti eccezionali nello spazio DevOps di questi giorni, oltre a libri e documenti ancora più fantastici su come ottenere risultati positivi.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-133">There are so many great tools in the DevOps space these days and even more fantastic books and papers on how to succeed.</span></span> <span data-ttu-id="ecd6a-134">Un libro preferito per iniziare a usare il percorso DevOps è [il progetto Phoenix](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), che segue la trasformazione di una società fittizia da NOOP a DevOps.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-134">A favorite book to get started on the DevOps journey is [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), which follows the transformation of a fictional company from NoOps to DevOps.</span></span> <span data-ttu-id="ecd6a-135">Una cosa da fare è che DevOps non è più un "bello" quando si distribuiscono applicazioni native cloud complesse.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-135">One thing is for certain: DevOps is no longer a "nice to have" when deploying complex, Cloud Native Applications.</span></span> <span data-ttu-id="ecd6a-136">È un requisito e deve essere pianificato e rioriginato all'inizio di qualsiasi progetto.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-136">It's a requirement and should be planned for and resourced at the start of any project.</span></span>

## <a name="references"></a><span data-ttu-id="ecd6a-137">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ecd6a-137">References</span></span>

- [<span data-ttu-id="ecd6a-138">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ecd6a-138">Azure DevOps</span></span>](https://azure.microsoft.com/services/devops/)
- [<span data-ttu-id="ecd6a-139">Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="ecd6a-139">Azure Resource Manager</span></span>](https://azure.microsoft.com/documentation/articles/resource-group-overview/)
- [<span data-ttu-id="ecd6a-140">Terraform</span><span class="sxs-lookup"><span data-stu-id="ecd6a-140">Terraform</span></span>](https://www.terraform.io/)
- [<span data-ttu-id="ecd6a-141">Interfaccia della riga di comando di Azure</span><span class="sxs-lookup"><span data-stu-id="ecd6a-141">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/)

>[!div class="step-by-step"]
><span data-ttu-id="ecd6a-142">[Precedente](infrastructure-as-code.md) 
> [Avanti](summary.md)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-142">[Previous](infrastructure-as-code.md)
[Next](summary.md)</span></span>
