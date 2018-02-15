---
title: Tecnologie Microsoft in applicazioni di cloud pronto devops
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Tecnologie Microsoft nelle applicazioni Cloud pronto DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3212bf1e938b789d68ca76dd06ce53a2788244b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a>Tecnologie Microsoft in applicazioni di cloud pronto devops

L'elenco seguente descrive gli strumenti, tecnologie e soluzioni che sono riconosciute come requisiti per le applicazioni Cloud pronto DevOps. È possibile adottare le app Cloud pronto DevOps, gradualmente, o in modo selettivo a seconda delle priorità.

-   **Infrastruttura cloud**: l'infrastruttura che fornisce la piattaforma di calcolo, sistema operativo, rete e archiviazione. Microsoft Azure è posizionato in corrispondenza di questo livello.

-   **Runtime**: questo livello fornisce l'ambiente per l'esecuzione dell'applicazione. Se si usano i contenitori, questo livello è basato in genere su [motore Docker](https://docs.docker.com/engine/), in esecuzione in host Linux o in host Windows. ([Contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) sono supportate a partire da Windows Server 2016. Contenitori di Windows è la scelta migliore per le applicazioni .NET Framework esistenti in esecuzione su Windows.)

-   **Cloud gestito**: quando si seleziona un'opzione cloud gestito, è possibile evitare i costi e complessità di gestire e supportare le patch del sistema operativo di infrastruttura, le macchine virtuali, sottostante e configurazione della rete. Se si sceglie di eseguire la migrazione tramite IaaS, è responsabile per tutte le attività e per i costi associati. In un'opzione cloud gestito, viene gestito solo le applicazioni e servizi sviluppati. Il provider di servizi cloud gestisce in genere tutti gli altri elementi. Esempi di servizi cloud gestiti in Azure [Database SQL di Azure](https://azure.microsoft.com/services/sql-database), [Cache Redis di Azure](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [di archiviazione di Azure](https://azure.microsoft.com/services/storage/), [Database di azure per MySQL](https://azure.microsoft.com/services/mysql/), [Database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)e gestire servizi di calcolo come [scalabilità della macchina virtuale imposta](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), e [servizio contenitore di Azure](https://azure.microsoft.com/services/container-service/).

-   **Sviluppo di applicazioni**: È possibile scegliere tra molte lingue quando si compilano applicazioni eseguibili nei contenitori. In questa guida è incentrata su [.NET](https://www.microsoft.com/net), tuttavia, è possibile sviluppare applicazioni basate sul contenitore con altri linguaggi, ad esempio Node.js, Python, molla/Java o GoLang.

-   **Monitoraggio, dati di telemetria, registrazione e controllo**: la possibilità di applicazioni di monitoraggio e controllo e i contenitori in esecuzione nel cloud è fondamentale per qualsiasi applicazione Cloud pronto DevOps. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono i principali strumenti di Microsoft che forniscono il monitoraggio e controllo per le app Cloud pronto DevOps.

-   **Provisioning**: strumenti di automazione consentono di eseguire il provisioning dell'infrastruttura e distribuire un'applicazione in più ambienti (ambiente di produzione, test, gestione temporanea). È possibile utilizzare strumenti come Chef e Puppet per gestire l'ambiente e configurazione di un'applicazione. Questo livello può essere implementato utilizzando gli approcci più semplici e più diretti. Ad esempio, è possibile distribuire direttamente tramite Azure interfaccia della riga di comando (CLI di Azure) degli strumenti e quindi utilizzare la distribuzione continua e rilasciare le pipeline di gestione in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Ciclo di vita dell'applicazione**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) e altri strumenti, ad esempio, Jenkins sono server di automazione di compilazione che consentono di implementare le pipeline CI/CD, tra cui la gestione del rilascio.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate, lo stato attivo in modo specifico sui dettagli sul livello di runtime (i contenitori di Windows). La guida descrive i modi in cui è possibile distribuire macchine virtuali di contenitori di Windows in Windows Server 2016 (e versioni successive). Descrive inoltre i livelli orchestrator più avanzati, quali Azure Service Fabric, Kubernetes e il servizio contenitore di Azure. L'impostazione dei livelli di orchestrator è un requisito fondamentale per modernizzazione .NET Framework (basato su Windows) applicazioni esistenti così come le applicazioni Cloud pronto DevOps.

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a>Applicazioni monolitiche *possibile* Cloud pronto DevOps

È importante evidenziare che le applicazioni monolitico (applicazioni che non sono basate su microservizi) *possibile* applicazioni Cloud pronto DevOps. È possibile creare e gestire monolitiche applicazioni che sfruttano i vantaggi del cloud computing modello utilizzando una combinazione di contenitori, il recapito continuo e DevOps. Se un'applicazione esistente monolitica è adatta per gli obiettivi aziendali, è possibile modernizzare e renderlo DevOps Cloud pronto.

Analogamente, se monolitiche applicazioni è possono utilizzare le applicazioni Cloud pronto DevOps architetture più complesso come applicazioni a più livelli inoltre possono essere moderno e come applicazioni Cloud pronto DevOps.

>[!div class="step-by-step"]
[Precedente](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Successivo](what-about-cloud-optimized-applications.md)
