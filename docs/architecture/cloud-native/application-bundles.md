---
title: Aggregazioni di applicazioni cloud native
description: Architettura di app .NET cloud native per Azure | Bundle di applicazioni native cloud
ms.date: 05/12/2020
ms.openlocfilehash: c16a9cba1fe31e025532ba98d644114a319bb9de
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395494"
---
# <a name="cloud-native-application-bundles"></a>Aggregazioni di applicazioni cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una proprietà chiave delle applicazioni native del cloud è la possibilità di sfruttare le funzionalità del cloud per velocizzare lo sviluppo. Questa progettazione spesso significa che un'applicazione completa utilizza diversi tipi di tecnologie. Le applicazioni possono essere fornite in contenitori Docker, alcuni servizi possono usare funzioni di Azure, mentre altre parti possono essere eseguite direttamente in macchine virtuali allocate su server metal di grandi dimensioni con accelerazione GPU hardware. Non esistono due applicazioni native del cloud, pertanto è difficile fornire un singolo meccanismo per la spedizione.

I contenitori Docker possono essere eseguiti in Kubernetes usando un grafico Helm per la distribuzione. Le funzioni di Azure possono essere allocate usando i modelli di bonifica. Infine, le macchine virtuali possono essere allocate usando la funzionalità di bonifica, ma con Ansible. Si tratta di una vasta gamma di tecnologie e non è stato possibile comprimere tutti i pacchetti in un pacchetto ragionevole. Fino ad ora.

I bundle di applicazioni native cloud (CNABs) sono uno sforzo comune da parte di diverse società, ad esempio Microsoft, Docker e HashiCorp, per sviluppare una specifica per la creazione di pacchetti di applicazioni distribuite.

Il lavoro richiesto è stato annunciato nel dicembre del 2018, pertanto c'è ancora un bel po' di lavoro da fare per esporre il lavoro richiesto alla maggior parte della community. Tuttavia, esiste già una [specifica aperta](https://github.com/deislabs/cnab-spec) e un'implementazione di riferimento nota come [borsone](https://duffle.sh/). Questo strumento, scritto in go, è un lavoro comune tra Docker e Microsoft.

CNABs può contenere diversi tipi di tecnologie di installazione. Ciò consente di coesistere nello stesso pacchetto elementi quali grafici Helm, modelli di bonifica e PlayBook Ansible. Una volta creati, i pacchetti sono indipendenti e portabili; possono essere installati da una chiavetta USB.  I pacchetti sono firmati in modo crittografico per assicurarsi che provengano dall'entità che attestano.

Il nucleo di un CNAB è un file denominato `bundle.json` . Questo file definisce il contenuto del bundle, ovvero le immagini o qualsiasi altro elemento. Nella figura 11-9 è definito un CNAB che richiama un po' di bonifica. Si noti, tuttavia, che definisce effettivamente un'immagine di chiamata usata per richiamare la bonifica. Quando si crea un pacchetto, il file Docker che si trova nella directory *CNAB* è incorporato in un'immagine Docker, che verrà inclusa nel bundle. Se la gestione dei contenitori è installata in un contenitore Docker nel bundle, non è necessario che gli utenti dispongano di un sistema di gestione delle risorse installato nel computer per eseguire il raggruppamento.

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

**Figura 10-18** -un file di esempio di bonifica

`bundle.json`Definisce anche un set di parametri che vengono passati nella bonifica. La parametrizzazione del bundle consente l'installazione in un'ampia gamma di ambienti diversi.

Anche il formato CNAB è flessibile e può essere usato in qualsiasi cloud. Può anche essere usato con soluzioni locali, ad esempio [OpenStack](https://www.openstack.org/).

## <a name="devops-decisions"></a>Decisioni DevOps

Ci sono così tanti strumenti eccezionali nello spazio DevOps di questi giorni, oltre a libri e documenti ancora più fantastici su come ottenere risultati positivi. Un libro preferito per iniziare a usare il percorso DevOps è [il progetto Phoenix](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), che segue la trasformazione di una società fittizia da NOOP a DevOps. Una cosa da fare è che DevOps non è più un "bello" quando si distribuiscono applicazioni native cloud complesse. È un requisito e deve essere pianificato e rioriginato all'inizio di qualsiasi progetto.

## <a name="references"></a>Riferimenti

- [Azure DevOps](https://azure.microsoft.com/services/devops/)
- [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/)
- [Terraform](https://www.terraform.io/)
- [Interfaccia della riga di comando di Azure](https://docs.microsoft.com/cli/azure/)

>[!div class="step-by-step"]
>[Precedente](infrastructure-as-code.md) 
> [Avanti](summary.md)
