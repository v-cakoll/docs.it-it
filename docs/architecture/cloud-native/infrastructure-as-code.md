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
# <a name="infrastructure-as-code"></a>Infrastruttura come codice

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le applicazioni native del cloud tendono a usare tutti i tipi di componenti di piattaforma distribuita come servizio (PaaS). In una piattaforma cloud come Azure, questi componenti possono includere elementi quali l'archiviazione, il bus di servizio e il servizio SignalR. Man mano che le applicazioni diventano più complesse, è probabile che il numero di questi servizi in uso aumenti. Analogamente al modo in cui il recapito continuo ha interrotto manualmente il modello tradizionale di distribuzione in un ambiente, il ritmo rapido delle modifiche ha interrotto anche il modello di gestione degli ambienti in un gruppo IT centralizzato.

Gli ambienti di compilazione possono anche essere automatizzati. È disponibile un'ampia gamma di strumenti ben congegnati che consentono di semplificare il processo.

## <a name="azure-resource-manager-templates"></a>Modelli di Azure Resource Manager

Azure Resource Manager modelli sono un linguaggio basato su JSON per la definizione di varie risorse in Azure. Lo schema di base ha un aspetto simile a quello illustrato nella figura 11-10.

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

**Figura 11-10** -schema per un modello di gestione risorse

All'interno di questo modello, è possibile definire un contenitore di archiviazione all'interno della sezione Resources, come indicato di seguito:
 
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

**Figura 11-11** -esempio di un account di archiviazione definito in un modello di gestione risorse

I modelli possono essere parametrizzati in modo che un modello possa essere riutilizzato con impostazioni diverse per definire gli ambienti di sviluppo, controllo di qualità e produzione. Questo consente di eliminare le sorprese quando si esegue la migrazione a un ambiente più elevato configurato in modo diverso dagli ambienti inferiori. Le risorse definite in un modello vengono in genere create all'interno di un singolo gruppo di risorse in Azure. è possibile definire più gruppi di risorse in un singolo modello di Gestione risorse ma insolito). In questo modo è molto semplice eliminare un ambiente semplicemente eliminando il gruppo di risorse nel suo complesso. L'analisi dei costi può essere eseguita anche a livello di gruppo di risorse, consentendo una rapida contabilità della quantità di costi di ogni ambiente.

Sono disponibili molti modelli di esempio definiti nel progetto di [modelli di avvio rapido di Azure](https://github.com/Azure/azure-quickstart-templates) su GitHub che conferiscono un piede quando si inizia con un nuovo modello o se ne aggiunge uno esistente.

I modelli di Gestione risorse possono essere eseguiti in diversi modi. Forse il modo più semplice è semplicemente incollarli nel portale di Azure. Per le distribuzioni sperimentali, questo metodo può essere molto rapido. Possono anche essere eseguiti come parte di un processo di compilazione o rilascio in Azure DevOps. Sono disponibili attività che utilizzeranno le connessioni in Azure per eseguire i modelli. Le modifiche apportate ai modelli Gestione risorse vengono applicate in modo incrementale, vale a dire che per aggiungere una nuova risorsa è sufficiente aggiungerla al modello. Gli strumenti gestiranno le differenze tra il gruppo di risorse corrente e il gruppo di risorse desiderato definito nel modello. Le risorse verranno quindi create o modificate in modo che corrispondano a quelle definite nel modello.  

## <a name="terraform"></a>Terraform

Uno svantaggio percepito dei modelli di Gestione risorse è che sono specifici del cloud di Azure. È insolito creare applicazioni che includono risorse da più di un cloud, ma nei casi in cui l'azienda si basa su tempi di attività spettacolari, potrebbe essere utile il costo del supporto di più cloud. Se era disponibile un linguaggio di modello che poteva essere usato in ogni cloud, le competenze degli sviluppatori sarebbero molto più portabili.

Sono disponibili diverse tecnologie. L'offerta più matura nello spazio è nota come [bonifica](https://www.terraform.io/). La bonifica supporta tutti i principali player cloud, ad esempio Azure, Google Cloud Platform, AWS e AliCloud, e supporta anche dozzine di giocatori secondari, ad esempio Heroku e DigitalOcean. Invece di usare JSON come linguaggio di definizione del modello, viene usato il formato YAML leggermente più conciso. 

Un esempio di file di bonifica che esegue la stessa operazione del modello di Gestione risorse precedente (Figura 11-11) è illustrato nella figura 11-12:

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

**Figura 11-12** -esempio di un modello di gestione risorse

La bonifica è un processo migliore per fornire messaggi di errore sensibili quando una risorsa non può essere distribuita a causa di un errore nel modello. Si tratta di un'area in cui i modelli di Gestione risorse presentano alcune problemi. È disponibile anche un'attività di convalida molto utile che può essere usata nella fase di compilazione per rilevare tempestivamente gli errori del modello.

Come per i modelli di Gestione risorse, sono disponibili strumenti da riga di comando che possono essere usati per distribuire modelli di bonifica. In Azure Pipelines sono inoltre presenti attività create dalla community che possono convalidare e applicare modelli di bonifica.

Nel caso in cui il modello di bonifica o Gestione risorse restituisca valori interessanti, ad esempio la stringa di connessione a un database appena creato, è possibile acquisirli nella pipeline di compilazione e usarli nelle attività successive.

>[!div class="step-by-step"]
>[Precedente](devops.md)
>[Successivo](application-bundles.md)
