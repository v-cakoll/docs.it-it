---
title: Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud
ms.date: 04/28/2018
ms.openlocfilehash: c5222ba13258f9c8a40ca3b9ce240aeb9f41da63
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546510"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud

Nell'elenco seguente vengono descritti gli strumenti, le tecnologie e le soluzioni riconosciuti come requisiti per le app ottimizzate per il cloud. È possibile adottare gli elementi ottimizzati per il cloud in modo selettivo o graduale, a seconda delle priorità.

- **Infrastruttura cloud:** l'infrastruttura che fornisce la piattaforma di elaborazione, il sistema operativo, la rete e l'archiviazione. Microsoft Azure è posizionato a questo livello.

- **Runtime**: Questo livello fornisce l'ambiente in cui l'applicazione deve essere eseguita. Se si utilizzano contenitori, questo livello è in genere basato su [Docker Engine](https://docs.docker.com/engine/), in esecuzione su host Linux o su host Windows. ([I contenitori](https://docs.microsoft.com/virtualization/windowscontainers/about/) di Windows sono supportati a partire da Windows Server 2016. Contenitori di Windows è la scelta migliore per le applicazioni .NET Framework esistenti eseguite in Windows.)

- **Cloud gestito:** quando si sceglie un'opzione cloud gestito, è possibile evitare le spese e la complessità della gestione e del supporto dell'infrastruttura sottostante, delle macchine virtuali, delle patch del sistema operativo e della configurazione di rete. Se si sceglie di eseguire la migrazione tramite IaaS, si è responsabili di tutte queste attività e dei costi associati. In un'opzione cloud gestito è possibile gestire solo le applicazioni e i servizi sviluppati. Il provider di servizi cloud gestisce in genere tutto il resto. Esempi di servizi cloud gestiti in Azure includono [il database SQL](https://azure.microsoft.com/services/sql-database)di Azure , Azure [Redis Cache](https://azure.microsoft.com/services/cache/), Azure [Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), Archiviazione di [Azure](https://azure.microsoft.com/services/storage/), Azure Database [for MySQL](https://azure.microsoft.com/services/mysql/), Azure Database for [PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)e servizi di calcolo gestiti come set di [scalabilità delle macchine virtuali](https://azure.microsoft.com/services/virtual-machine-scale-sets/), Servizio app di [Azure](https://azure.microsoft.com/services/app-service/)e Servizio [Azure Kubernetes](https://azure.microsoft.com/services/container-service/).

- **Sviluppo di**applicazioni: è possibile scegliere tra molti linguaggi quando si compilano applicazioni eseguite in contenitori. Questa guida è incentrata su [.NET](https://dotnet.microsoft.com), ma è possibile sviluppare app basate su contenitori usando altri linguaggi, ad esempio Node.js, Python, Spring/Java o Go.

- **Monitoraggio, telemetria, registrazione e controllo:** la capacità di monitorare e controllare le applicazioni e i contenitori in esecuzione nel cloud è fondamentale per qualsiasi applicazione ottimizzata per il cloud. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono i principali strumenti Microsoft che forniscono monitoraggio e controllo per le app ottimizzate per il cloud.

- **Provisioning:** gli strumenti di automazione consentono di eseguire il provisioning dell'infrastruttura e di distribuire un'applicazione in più ambienti (produzione, test, gestione temporanea). Puoi usare strumenti come Chef e Puppet per gestire la configurazione e l'ambiente di un'applicazione. Questo livello può essere implementato anche utilizzando approcci più semplici e diretti. Ad esempio, è possibile distribuire direttamente usando gli strumenti dell'interfaccia della riga di comando di Azure (CLI di Azure) e quindi usare le pipeline di distribuzione e gestione del rilascio continue nei servizi DevOps di [Azure.](https://azure.microsoft.com/services/devops/)

- **Ciclo di vita dell'applicazione:** i [servizi DevOps](https://azure.microsoft.com/services/devops/) di Azure e altri strumenti, ad esempio Jenkins, sono server di automazione compilati che consentono di implementare pipeline CI/CD, inclusa la gestione del rilascio.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate si concentrano in particolare sui dettagli sul livello di runtime (contenitori di Windows). The guidance describes the ways you can deploy Windows Containers on Windows Server 2016 (and later versions) VMs and Azure Container Instances. Copre anche piattaforme PaaS più avanzate come il servizio app di Azure e l'orchestratore come il servizio Azure Kubernetes.It also covers more advanced PaaS platforms like Azure App Service and orchestrator like Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Le applicazioni monolitiche *possono* essere ottimizzate per il cloud

È importante sottolineare che le applicazioni monolitiche (applicazioni non basate su microservizi) *possono* essere applicazioni ottimizzate per il cloud. È possibile compilare e gestire applicazioni monolitiche che sfruttano il modello di cloud computing utilizzando una combinazione di contenitori, recapito continuo e DevOps. Se un'applicazione monolitica esistente è giusta per i tuoi obiettivi aziendali, puoi modernizzarla e renderla ottimizzata per il cloud.

Analogamente, se le applicazioni monolitiche possono essere applicazioni ottimizzate per il cloud, altre architetture più complesse come le applicazioni A più livelli possono anche essere modernizzate come applicazioni ottimizzate per il cloud.

>[!div class="step-by-step"]
>[Successivo](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[precedente](what-about-cloud-native-applications.md)
