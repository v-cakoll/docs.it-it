---
title: Distribuzione di eShopOnContainers in Azure
description: Distribuzione dell'applicazione eShopOnContainers tramite il servizio Kubernetes di Azure, Helm e DevSpaces.
ms.date: 06/30/2019
ms.openlocfilehash: 21033cc904dc595193c69f3452ce2522740f8ff6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183273"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Distribuzione di eShopOnContainers in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La logica che supporta l'applicazione eShopOnContainers può essere supportata da Azure usando un'ampia gamma di servizi. L'approccio consigliato consiste nell'usare Kubernetes con il servizio Azure Kubernetes (AKS). Questo può essere combinato con la distribuzione Helm per garantire una configurazione dell'infrastruttura facilmente ripetuta. Facoltativamente, gli sviluppatori possono sfruttare Azure Dev Spaces per Kubernetes come parte del processo di sviluppo. Un'altra opzione consiste nell'ospitare la funzionalità dell'app usando funzionalità senza server di Azure, ad esempio funzioni di Azure e app per la logica di Azure.

## <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Se si vuole ospitare l'applicazione eShopOnContainers nel proprio cluster AKS, il primo passaggio consiste nel creare il cluster. A tale scopo, è possibile usare la portale di Azure, che illustra i passaggi necessari oppure è possibile usare l'interfaccia della riga di comando di Azure per assicurarsi di abilitare il controllo degli accessi in base al ruolo (RBAC) e il routing delle applicazioni. La documentazione di eShopOnContainers descrive i passaggi necessari per la creazione di un cluster AKS. Una volta creato il cluster, è necessario abilitare l'accesso al dashboard di Kubernetes. a questo punto, è possibile passare al dashboard di Kubernetes per gestire il cluster.

Una volta che il cluster è stato creato e configurato, è possibile distribuirvi l'applicazione usando Helm e Tiller.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Distribuzione nel servizio Azure Kubernetes tramite Helm

Le distribuzioni di base a AKS possono usare script CLI personalizzati o semplici file di distribuzione, ma le applicazioni più complesse devono usare uno strumento di gestione delle dipendenze come Helm. Helm è gestito da cloud-native Computing Foundation e consente di definire, installare e aggiornare le applicazioni Kubernetes. Helm è costituito da un client della riga di comando, Helm, che usa i grafici Helm e un componente in cluster, Tiller. I grafici Helm usano file con formato YAML standard per descrivere un set correlato di risorse Kubernetes e vengono in genere sottoposte a controllo delle versioni insieme all'applicazione che descrivono. I grafici Helm variano da semplici a complessi, a seconda dei requisiti dell'installazione che descrivono.

I grafici Helm di eShopOnContainers sono disponibili nella cartella/K8S/Helm. La figura 2-6 illustra come i diversi componenti dell'applicazione sono organizzati in una struttura di cartelle utilizzata da Helm per definire e distribuire le distribuzioni.

![architettura eShopOnContainers](./media/eshoponcontainers-helm-folder.png)
**figura 2-6**. Cartella Helm eShopOnContainers.

Ogni singolo componente viene installato utilizzando un comando `helm install`. Questi comandi sono facilmente scritti e eShopOnContainers fornisce uno script "deploy all" che esegue il ciclo dei diversi componenti e li installa usando i rispettivi grafici Helm. Il risultato è un processo ripetibile, con versione con l'applicazione nel controllo del codice sorgente, che chiunque nel team può distribuire in un cluster AKS con un comando di script a una riga. In particolare in combinazione con Azure Dev Spaces, questo consente agli sviluppatori di diagnosticare e testare facilmente le proprie modifiche alle proprie app native basate su microservizi.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Azure Dev Spaces aiuta i singoli sviluppatori a ospitare la propria versione univoca dei cluster AKS in Azure durante lo sviluppo. Questo consente di ridurre al minimo i requisiti dei computer locali e consente ai membri del team di verificare rapidamente il comportamento delle modifiche in un ambiente AKS reale. Azure Dev Spaces offre un'interfaccia della riga di comando per gli sviluppatori da usare per gestire gli spazi di sviluppo e per eseguire la distribuzione in uno spazio di sviluppo figlio specifico, se necessario. Si fa riferimento a ogni spazio dev figlio usando un sottodominio URL univoco, consentendo distribuzioni affiancate di cluster modificati in modo che i singoli sviluppatori possano evitare conflitti con il lavoro in corso. Nella figura 2-7 è possibile vedere come Developer Susie ha distribuito una propria versione del microservizio Bikes nello spazio di sviluppo. Potrà quindi testare le modifiche usando un URL personalizzato che inizia con il nome dello spazio (susie.s.dev.myapp.eus.azds.io).

![architettura eShopOnContainers](./media/azure-devspaces-one.png)
**figura 2-7**. Developer Susie distribuisce la propria versione del microservizio Bikes e ne esegue il test.

Allo stesso tempo, lo sviluppatore Giorgio sta personalizzando il microservizio prenotazioni e deve testare le proprie modifiche. È in grado di distribuire le modifiche nel proprio spazio di sviluppo senza conflitti con le modifiche di Susie, come illustrato nella figura 2-8. Può testare le modifiche usando il proprio URL, che è preceduto dal nome dello spazio (john.s.dev.myapp.eus.azds.io).

![architettura eShopOnContainers](./media/azure-devspaces-two.png)
**figura 2-8**. Developer Giorgio distribuisce la propria versione del microservizio prenotazioni e la testa senza conflitti con altri sviluppatori.

Con Azure Dev Spaces, i team possono lavorare direttamente con AKS mentre cambiano, distribuiscono e verificano le modifiche in modo indipendente. Questo approccio riduce la necessità di ambienti host dedicati distinti, perché ogni sviluppatore ha in effetti un proprio ambiente AKS. Gli sviluppatori possono lavorare con Azure Dev Spaces usando l'interfaccia della riga di comando o avviare l'applicazione per Azure Dev Spaces direttamente da Visual Studio. [Altre informazioni sul funzionamento di Azure Dev Spaces e sulla configurazione.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Funzioni di Azure e app per la logica (senza server)

L'esempio eShopOnContainers include il supporto per tenere traccia delle campagne di marketing online. Una funzione di Azure viene usata per eseguire il pull dei dettagli della campagna di marketing per un determinato ID campagna. Invece di creare un'applicazione ASP.NET Core completa a questo scopo, un singolo endpoint funzione di Azure è più semplice e sufficiente. Funzioni di Azure include un modello di compilazione e distribuzione molto più semplice rispetto alle applicazioni full ASP.NET Core, specialmente se configurato per l'esecuzione in Kubernetes. La distribuzione della funzione viene scritta tramite script usando i modelli di Azure Resource Manager (ARM) e l'interfaccia della riga di comando di Azure. Questo microservizio di dettagli della campagna non è destinato al cliente e non ha gli stessi requisiti del negozio online, rendendolo un candidato ideale per funzioni di Azure. La funzione richiede che alcune configurazioni funzionino correttamente, ad esempio i dati della stringa di connessione del database e le impostazioni dell'URI di base dell'immagine. Le funzioni di Azure vengono configurate nel portale di Azure.

## <a name="references"></a>Riferimenti

- [eShopOnContainers: creare un cluster Kubernetes in AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Precedente](map-eshoponcontainers-azure-services.md)
>[Successivo](centralized-configuration.md)
