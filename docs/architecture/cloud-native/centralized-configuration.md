---
title: Configurazione centralizzata
description: Centralizzazione della configurazione per le applicazioni native del cloud usando app Azure configurazione e l'insieme di credenziali AzureKey.
ms.date: 05/13/2020
ms.openlocfilehash: d389d29dcdb1db5162d95370d181ab5a85d72dc8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614227"
---
# <a name="centralized-configuration"></a>Configurazione centralizzata

A differenza di un'app monolitica in cui tutto viene eseguito all'interno di una singola istanza, un'applicazione nativa del cloud è costituita da servizi indipendenti distribuiti tra macchine virtuali, contenitori e aree geografiche. La gestione delle impostazioni di configurazione per decine di servizi interdipendenti può risultare complessa. Le copie duplicate delle impostazioni di configurazione in posizioni diverse sono soggette a errori e difficili da gestire. La configurazione centralizzata è un requisito fondamentale per le applicazioni distribuite native del cloud.

Come illustrato nel [capitolo 1](introduction.md), le raccomandazioni per le app a dodici fattori richiedono una separazione rigorosa tra il codice e la configurazione. La configurazione deve essere archiviata esternamente dall'applicazione e deve essere letta in base alle esigenze. L'archiviazione dei valori di configurazione come costanti o valori letterali nel codice è una violazione. Gli stessi valori di configurazione vengono spesso usati da molti servizi nella stessa applicazione. Inoltre, è necessario supportare gli stessi valori in più ambienti, ad esempio sviluppo, test e produzione. La procedura consigliata è archiviarli in un archivio di configurazione centralizzato.

Il cloud di Azure presenta diverse opzioni eccezionali.

## <a name="azure-app-configuration"></a>Configurazione app di Azure

[App Azure configurazione](https://docs.microsoft.com/azure/azure-app-configuration/overview) è un servizio di Azure completamente gestito che archivia le impostazioni di configurazione non segrete in una posizione sicura e centralizzata. I valori archiviati possono essere condivisi tra più servizi e applicazioni.

Il servizio è semplice da usare e offre diversi vantaggi:

- Rappresentazioni e mapping flessibili di chiave/valore
- Assegnazione di tag con etichette di Azure
- Interfaccia utente dedicata per la gestione
- Crittografia delle informazioni riservate
- Esecuzione di query e recupero batch

App Azure configurazione mantiene le modifiche apportate alle impostazioni chiave-valore per sette giorni. La funzionalità snapshot temporizzato consente di ricostruire la cronologia di un'impostazione e persino di eseguire il rollback per una distribuzione non riuscita.

La configurazione dell'app memorizza automaticamente nella cache ogni impostazione per evitare chiamate eccessive all'archivio di configurazione. L'operazione di aggiornamento resta in attesa fino a quando il valore memorizzato nella cache di un'impostazione non scade per aggiornare tale impostazione, anche quando il relativo valore viene modificato nell'archivio di configurazione. La scadenza predefinita della cache è 30 secondi. È possibile eseguire l'override dell'ora di scadenza.

La configurazione dell'app crittografa tutti i valori di configurazione in transito e inattivi. I nomi delle chiavi e le etichette vengono usati come indici per il recupero dei dati di configurazione e non vengono crittografati.

Sebbene la configurazione dell'app fornisca sicurezza avanzata, Azure Key Vault rappresenta comunque il posto migliore per l'archiviazione dei segreti delle applicazioni. Key Vault fornisce la crittografia a livello di hardware, i criteri di accesso granulari e le operazioni di gestione, ad esempio la rotazione del certificato. È possibile creare valori di configurazione dell'app che fanno riferimento a segreti archiviati in un Key Vault.

## <a name="azure-key-vault"></a>Insieme di credenziali chiave di Azure

Key Vault è un servizio gestito per l'archiviazione e l'accesso in modo sicuro ai segreti. Un segreto è qualsiasi elemento per cui si vuole controllare rigorosamente l'accesso, ad esempio chiavi API, password o certificati. Un insieme di credenziali è un gruppo logico di segreti.

Key Vault riduce notevolmente le probabilità di divulgazione accidentale dei segreti. Quando si usa Key Vault, gli sviluppatori di applicazioni non devono più archiviare le informazioni di sicurezza nell'applicazione. Questa pratica Elimina la necessità di archiviare queste informazioni all'interno del codice. Ad esempio, per un'applicazione potrebbe essere necessario connettersi a un database. Invece di archiviare la stringa di connessione nel codice dell'app, è possibile archiviarla in modo sicuro in Key Vault.

Le applicazioni possono accedere in modo sicuro alle informazioni necessarie tramite URI. Questi URI permettono alle applicazioni di recuperare versioni specifiche di un segreto. Non è necessario scrivere codice personalizzato per proteggere le informazioni segrete archiviate nel Key Vault.

L'accesso a Key Vault richiede l'autenticazione e l'autorizzazione del chiamante corrette. In genere, ogni microservizio nativo del cloud usa una combinazione ClientID/ClientSecret. È importante che queste credenziali vengano mantenute al di fuori del controllo del codice sorgente. Una procedura consigliata consiste nell'impostarli nell'ambiente dell'applicazione. L'accesso diretto a Key Vault da AKS può essere eseguito usando [Key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol).

## <a name="configuration-in-eshop"></a>Configurazione in eShop

L'applicazione eShopOnContainers include i file di impostazioni dell'applicazione locale con ogni microservizio. Questi file vengono archiviati nel controllo del codice sorgente, ma non includono i segreti di produzione, ad esempio le stringhe di connessione o le chiavi API. In produzione, le singole impostazioni possono essere sovrascritte con le variabili di ambiente per servizio. L'inserimento di segreti nelle variabili di ambiente è una pratica comune per le applicazioni ospitate, ma non fornisce un archivio di configurazione centrale. Per supportare la gestione centralizzata delle impostazioni di configurazione, ogni microservizio include un'impostazione che consente di alternare l'uso di impostazioni locali o Azure Key Vault impostazioni.

## <a name="references"></a>Riferimenti

- [Architettura eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Architecture)
- [Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/scalable-available-multi-container-microservice-applications)
- [Gestione API di Azure](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)
- [Panoramica del database SQL di Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)
- [Cache Redis di Azure](https://azure.microsoft.com/services/cache/)
- [API Azure Cosmos DB per MongoDB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)
- [Bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Panoramica di Monitoraggio di Azure](https://docs.microsoft.com/azure/azure-monitor/overview)
- [eShopOnContainers: creare un cluster Kubernetes in AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Precedente](deploy-eshoponcontainers-azure.md) 
> [Avanti](scale-applications.md)
