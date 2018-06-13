---
title: Tecnologie Microsoft nelle applicazioni ottimizzato su Cloud
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Tecnologie Microsoft nelle applicazioni ottimizzato su Cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ece366ee3918124bb60e367d3c7447c1d4555c72
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957941"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologie Microsoft nelle applicazioni ottimizzato su cloud

Nell'elenco seguente descrive gli strumenti, tecnologie e soluzioni che sono riconosciute come i requisiti per le app ottimizzato su Cloud. È possibile adottare elementi ottimizzato su Cloud in modo selettivo o gradualmente, a seconda delle priorità.

-   **Infrastruttura cloud**: l'infrastruttura che fornisce la piattaforma di calcolo, sistema operativo, rete e archiviazione. Microsoft Azure è posizionato in corrispondenza di questo livello.

-   **Runtime**: questo livello fornisce l'ambiente per l'esecuzione dell'applicazione. Se si usano i contenitori, questo livello è basato in genere su [motore Docker](https://docs.docker.com/engine/), in esecuzione in host Linux o in host Windows. ([Contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) sono supportate a partire da Windows Server 2016. Contenitori di Windows è la scelta migliore per le applicazioni .NET Framework esistenti in esecuzione su Windows.)

-   **Cloud gestito**: quando si seleziona un'opzione cloud gestito, è possibile evitare i costi e complessità di gestire e supportare le patch del sistema operativo di infrastruttura, le macchine virtuali, sottostante e configurazione della rete. Se si sceglie di eseguire la migrazione tramite IaaS, è responsabile per tutte le attività e per i costi associati. In un'opzione cloud gestito, viene gestito solo le applicazioni e servizi sviluppati. Il provider di servizi cloud gestisce in genere tutti gli altri elementi. Esempi di servizi cloud gestito di Azure [Database SQL di Azure](https://azure.microsoft.com/services/sql-database), [Cache Redis di Azure](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [archiviazione di Azure](https://azure.microsoft.com/services/storage/), [Database di azure per MySQL](https://azure.microsoft.com/services/mysql/), [Database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)e gestiti i servizi di calcolo, ad esempio [scalabilità della macchina virtuale imposta](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), e [Azure Kubernetes servizio](https://azure.microsoft.com/services/container-service/).

-   **Sviluppo di applicazioni**: È possibile scegliere tra molte lingue quando si compilano applicazioni eseguibili nei contenitori. Questa guida è incentrata sulla [.NET](https://www.microsoft.com/net), tuttavia, è possibile sviluppare applicazioni basate sul contenitore utilizzando altri linguaggi, ad esempio Node. js, Python, Spring/Java, o passare.

-   **Monitoraggio, dati di telemetria, registrazione e controllo**: la possibilità di monitoraggio e controllo delle applicazioni e i contenitori in esecuzione nel cloud è fondamentale per qualsiasi applicazione ottimizzato su Cloud. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono i principali strumenti di Microsoft che forniscono il monitoraggio e controllo per le app ottimizzato su Cloud.

-   **Provisioning**: strumenti di automazione consentono di eseguire il provisioning dell'infrastruttura e distribuire un'applicazione in più ambienti (ambiente di produzione, test, gestione temporanea). È possibile utilizzare strumenti come Chef e Puppet per gestire l'ambiente e configurazione di un'applicazione. Questo livello può essere implementato utilizzando gli approcci più semplici e più diretti. Ad esempio, è possibile distribuire direttamente tramite Azure interfaccia della riga di comando (CLI di Azure) degli strumenti e quindi utilizzare la distribuzione continua e rilasciare le pipeline di gestione in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Ciclo di vita dell'applicazione**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) e altri strumenti, ad esempio Jenkins, vengono compilati automazione i server che consentono di implementare pipeline CI/CD, tra cui la gestione del rilascio.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate, lo stato attivo in modo specifico sui dettagli sul livello di runtime (i contenitori di Windows). Le linee guida vengono descritte le modalità è possibile distribuire macchine virtuali di contenitori di Windows in Windows Server 2016 (e versioni successive) e istanze di contenitore di Azure. Descrive inoltre piattaforme di PaaS più avanzate, ad esempio Azure App Service e agente di orchestrazione come servizio Kubernetes Azure e Azure Service Fabric.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Le applicazioni monolitiche *possibile* essere ottimizzato su Cloud

È importante evidenziare tale monolitico applicazioni (che non si basano su microservizi) *possibile* essere ottimizzato per il Cloud le applicazioni. È possibile creare e gestire monolitiche applicazioni che sfruttano i vantaggi del cloud computing modello utilizzando una combinazione di contenitori, il recapito continuo e DevOps. Se un'applicazione monolitica esistente è adatto per gli obiettivi aziendali, è possibile modernizzare e renderlo ottimizzato su Cloud.

Analogamente, se le applicazioni monolitiche possono essere ottimizzato per il Cloud le applicazioni, architetture più complesso, ad esempio le applicazioni a più livelli possono anche modernizzate come applicazioni ottimizzato su Cloud.

>[!div class="step-by-step"]
[Precedente](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Successivo](what-about-cloud-native-applications.md)
