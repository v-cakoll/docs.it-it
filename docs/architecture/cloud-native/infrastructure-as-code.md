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
# <a name="infrastructure-as-code"></a>Infrastructure as code

I sistemi nativi del cloud comprendono microservizi, contenitori e progettazione di sistemi moderni per ottenere velocità e agilità. Forniscono fasi di compilazione e rilascio automatizzate per garantire codice coerente e di qualità. Ma questa è solo una parte della storia. Come si esegue il provisioning degli ambienti cloud su cui vengono eseguiti questi sistemi?

Le moderne applicazioni native del cloud adottano la pratica ampiamente accettata dell' [infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)o `IaC` .  Con IaC è possibile automatizzare il provisioning della piattaforma. Si applicano essenzialmente procedure di progettazione software come test e controllo delle versioni alle procedure DevOps. L'infrastruttura e le distribuzioni sono automatiche, coerenti e ripetibili. Proprio come il recapito continuo automatizzato il modello tradizionale di distribuzioni manuali, l'infrastruttura As code (IaC) sta evolvendo in che modo vengono gestiti gli ambienti applicazione.

Strumenti come Azure Resource Manager (ARM), bonifica e l'interfaccia della riga di comando di Azure consentono di creare script in modo dichiarativo dell'infrastruttura cloud necessaria.

## <a name="azure-resource-manager-templates"></a>Modelli di Gestione risorse di Azure

ARM sta per [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/). Si tratta di un motore di provisioning API incorporato in Azure ed esposto come un servizio API. ARM ti permette di distribuire, aggiornare, eliminare e gestire le risorse contenute nel gruppo di risorse di Azure in un'unica operazione coordinata. Fornire al motore un modello basato su JSON che specifica le risorse necessarie e la relativa configurazione. ARM Orchestra automaticamente la distribuzione nell'ordine corretto rispettando le dipendenze. Il motore garantisce idempotenza. Se una risorsa desiderata esiste già con la stessa configurazione, il provisioning verrà ignorato.

Azure Resource Manager modelli sono un linguaggio basato su JSON per la definizione di varie risorse in Azure. Lo schema di base ha un aspetto simile a quello illustrato nella figura 10-14.

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

**Figura 10-14** -schema per un modello di gestione risorse

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

**Figura 10-15** -esempio di un account di archiviazione definito in un modello di gestione risorse

Un modello ARM può essere parametrizzato con le informazioni di configurazione e l'ambiente dinamico. In questo modo è possibile riutilizzarlo per definire ambienti diversi, ad esempio sviluppo, controllo di qualità o produzione. In genere, il modello crea tutte le risorse all'interno di un singolo gruppo di risorse di Azure. Se necessario, è possibile definire più gruppi di risorse in un singolo modello di Gestione risorse. È possibile eliminare tutte le risorse in un ambiente eliminando il gruppo di risorse stesso. L'analisi dei costi può essere eseguita anche a livello di gruppo di risorse, consentendo una rapida contabilità della quantità di costi di ogni ambiente.

Sono disponibili molti esempi o modelli ARM nel progetto di [modelli di avvio rapido di Azure](https://github.com/Azure/azure-quickstart-templates) su GitHub. Consentono di accelerare la creazione di un nuovo modello o di modificarne uno esistente.

I modelli di Gestione risorse possono essere eseguiti in molti modi. Forse il modo più semplice è semplicemente incollarli nel portale di Azure. Per le distribuzioni sperimentali, questo metodo può essere rapido. Possono anche essere eseguiti come parte di un processo di compilazione o rilascio in Azure DevOps. Sono disponibili attività che utilizzeranno le connessioni in Azure per eseguire i modelli. Le modifiche apportate ai modelli Gestione risorse vengono applicate in modo incrementale, vale a dire che per aggiungere una nuova risorsa è sufficiente aggiungerla al modello. Gli strumenti risolveranno le differenze tra le risorse correnti e quelle definite nel modello. Le risorse verranno quindi create o modificate in modo che corrispondano a quelle definite nel modello.  

## <a name="terraform"></a>Terraform

Le applicazioni native del cloud sono spesso costruite come `cloud agnostic` . Il che significa che l'applicazione non è strettamente associata a un particolare fornitore di cloud e può essere distribuita in qualsiasi cloud pubblico.

La [bonifica](https://www.terraform.io/) è uno strumento per la creazione di modelli commerciali che consente di effettuare il provisioning di applicazioni native del cloud in tutti i principali lettori cloud: Azure, Google Cloud Platform, AWS e AliCloud. Invece di usare JSON come linguaggio di definizione del modello, viene usato il formato YAML leggermente più conciso.

Un esempio di file di bonifica che esegue la stessa operazione del modello di Gestione risorse precedente (figura 10-15) è illustrato nella figura 10-16:

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

**Figura 10-16** -esempio di un modello di gestione risorse

La bonifica fornisce anche messaggi di errore intuitivi per i modelli di problema. È disponibile anche un'attività di convalida utile che può essere usata nella fase di compilazione per rilevare tempestivamente gli errori del modello.

Come per i modelli di Gestione risorse, gli strumenti da riga di comando sono disponibili per la distribuzione di modelli di bonifica. In Azure Pipelines sono inoltre presenti attività create dalla community che possono convalidare e applicare modelli di bonifica.

A volte i modelli di bonifica e ARM restituiscono valori significativi, ad esempio una stringa di connessione a un database appena creato. Queste informazioni possono essere acquisite nella pipeline di compilazione e utilizzate nelle attività successive.

## <a name="azure-cli-scripts-and-tasks"></a>Script e attività dell'interfaccia della riga di comando di Azure

Infine, è possibile usare l' [interfaccia](https://docs.microsoft.com/cli/azure/) della riga di comando di Azure per eseguire lo script dichiarativo dell'infrastruttura cloud. È possibile creare, trovare e condividere script dell'interfaccia della riga di comando di Azure per eseguire il provisioning e configurare quasi tutte le risorse di Azure L'interfaccia della riga di comando è semplice da usare con una curva di apprendimento delicata. Gli script vengono eseguiti in PowerShell o bash. Sono anche semplici da sottomettere a debug, soprattutto quando vengono confrontati con i modelli ARM.

Gli script dell'interfaccia della riga di comando di Azure funzionano correttamente quando è necessario eliminare e ridistribuire l'infrastruttura. L'aggiornamento di un ambiente esistente può risultare complesso. Molti comandi dell'interfaccia della riga di comando non sono idempotente. Ciò significa che la risorsa verrà ricreata ogni volta che viene eseguita, anche se la risorsa esiste già. È sempre possibile aggiungere codice che controlla l'esistenza di ogni risorsa prima di crearla. Tuttavia, in questo modo lo script può diventare gonfio e difficile da gestire.

Questi script possono essere incorporati anche nelle pipeline DevOps di Azure `Azure CLI tasks` . L'esecuzione della pipeline richiama lo script.

La figura 10-17 Mostra un frammento YAML che elenca la versione dell'interfaccia della riga di comando di Azure e i dettagli della sottoscrizione. Si noti come i comandi dell'interfaccia della riga di comando di Azure siano inclusi in uno script inline.

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

**Figura 10-17** -script dell'interfaccia della riga di comando di Azure

In questo articolo, [che cos'è l'infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), l'autore di Sam Guckenheimer descrive in che modo i team che implementano IaC possono fornire ambienti stabili in modo rapido e scalabile. I team evitano la configurazione manuale degli ambienti e impongono la coerenza rappresentando lo stato desiderato dei propri ambienti tramite codice. Le distribuzioni dell'infrastruttura con IaC sono ripetibili ed evitano problemi di runtime causati dalla mancata configurazione o dalle dipendenze mancanti. I team DevOps possono collaborare con una serie unificata di procedure e strumenti per distribuire applicazioni e la loro infrastruttura di supporto in modo rapido, affidabile e scalabile ".

>[!div class="step-by-step"]
>[Precedente](feature-flags.md) 
> [Avanti](application-bundles.md)
