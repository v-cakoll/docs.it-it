---
title: Tecnologie Microsoft nelle applicazioni ottimizzato su Cloud
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Tecnologie Microsoft nelle applicazioni ottimizzato su Cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 3c5886dc3583a5d4a6cc9566556edbe1822ad6d1
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315180"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologie Microsoft nelle applicazioni ottimizzato su cloud

Nell'elenco seguente descrive gli strumenti, tecnologie e soluzioni che sono riconosciute come i requisiti per le app ottimizzato su Cloud. È possibile adottare elementi ottimizzato su Cloud in modo selettivo o gradualmente, a seconda delle priorità.

-   **Infrastruttura cloud**: l'infrastruttura che fornisce la piattaforma di calcolo, sistema operativo, rete e archiviazione. Microsoft Azure è posizionato a questo livello.

-   **Runtime**: questo livello fornisce l'ambiente per l'esecuzione dell'applicazione. Se si usano i contenitori, questo livello è basato in genere su [motore Docker](https://docs.docker.com/engine/), in esecuzione negli host di Linux o in host Windows. ([i contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) sono supportate a partire da Windows Server 2016. I contenitori di Windows è la scelta migliore per le applicazioni .NET Framework esistenti in esecuzione su Windows.)

-   **Gestito cloud**: quando si seleziona un'opzione cloud gestito, è possibile evitare abbattere i costi e complessità di gestire e supportare le patch del sistema operativo dell'infrastruttura, le macchine virtuali, sottostante e configurazione della rete. Se si sceglie di eseguire la migrazione tramite IaaS, è responsabile per tutte le attività e per i costi associati. In un'opzione cloud gestito, viene gestito solo le applicazioni e servizi sviluppati. Il provider di servizi cloud gestisce in genere tutti gli altri elementi. Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Sviluppo di applicazioni**: È possibile scegliere tra molte lingue quando si compilano applicazioni eseguite nei contenitori. Questa guida è incentrata sulla [.NET](https://www.microsoft.com/net), tuttavia, è possibile sviluppare applicazioni basate sul contenitore utilizzando altri linguaggi, ad esempio Node. js, Python, Spring/Java, o passare.

-   **Monitoraggio, dati di telemetria, registrazione e controllo**: la possibilità di monitoraggio e controllo delle applicazioni e i contenitori in esecuzione nel cloud è fondamentale per qualsiasi applicazione ottimizzato su Cloud. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono i principali strumenti di Microsoft che forniscono il monitoraggio e controllo per le app ottimizzato su Cloud.

-   **Provisioning**: strumenti di automazione consentono di eseguire il provisioning dell'infrastruttura e distribuire un'applicazione in più ambienti (ambiente di produzione, eseguire test, gestione temporanea). È possibile usare strumenti come Puppet e Chef per gestire l'ambiente e configurazione di un'applicazione. Questo livello può essere implementato utilizzando gli approcci più semplici e più diretti. Ad esempio, è possibile distribuire direttamente tramite Azure interfaccia della riga di comando (CLI di Azure), per gli strumenti e quindi utilizzare la distribuzione continua e rilasciare le pipeline di gestione in [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/).

-   **Ciclo di vita dell'applicazione**: [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/) e altri strumenti, ad esempio Jenkins, vengono compilati automazione i server che consentono di implementare pipeline CI/CD, tra cui la gestione del rilascio.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate, riguardano in particolare i dettagli sul livello di runtime (i contenitori di Windows). Le linee guida vengono descritte le modalità è possibile distribuire macchine virtuali di contenitori di Windows in Windows Server 2016 (e versioni successive) e istanze di contenitore di Azure. Descrive inoltre piattaforme di PaaS più avanzate, ad esempio Azure App Service e agente di orchestrazione come servizio Kubernetes Azure e Azure Service Fabric.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Le applicazioni monolitiche *possibile* essere ottimizzato su Cloud

È importante evidenziare tale monolitico applicazioni (che non si basano su microservizi) *possibile* essere ottimizzato per il Cloud le applicazioni. È possibile creare e gestire monolitiche applicazioni che sfruttano il cloud computing modello utilizzando una combinazione di contenitori, il recapito continuo e DevOps. Se un'applicazione monolitica esistente è adatto per gli obiettivi aziendali, è possibile modernizzare e renderlo ottimizzato su Cloud.

Analogamente, se le applicazioni monolitiche possono essere ottimizzato per il Cloud le applicazioni, architetture più complesso, ad esempio le applicazioni a più livelli possono anche modernizzate come applicazioni ottimizzato su Cloud.

>[!div class="step-by-step"]
[Precedente](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Successivo](what-about-cloud-native-applications.md)
