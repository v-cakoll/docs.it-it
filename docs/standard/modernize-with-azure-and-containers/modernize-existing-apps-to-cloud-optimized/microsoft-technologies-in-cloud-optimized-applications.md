---
title: Tecnologie Microsoft nelle applicazioni ottimizzato per il Cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Tecnologie Microsoft nelle applicazioni ottimizzato per il Cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 874eeffe77d7f5e459be4d1a93cc2c45e8f8711a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615039"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologie Microsoft nelle applicazioni ottimizzato per il cloud

Nell'elenco seguente vengono descritti strumenti, tecnologie e soluzioni che sono riconosciute come i requisiti per le app ottimizzato per il Cloud. È possibile adottare gradualmente, o in modo selettivo ottimizzato per il Cloud elementi a seconda delle tue priorità.

-   **Infrastruttura cloud**: l'infrastruttura che fornisce la piattaforma di calcolo, sistema operativo, rete e archiviazione. Microsoft Azure è posizionato in corrispondenza di questo livello.

-   **Runtime**: questo livello fornisce l'ambiente per l'esecuzione dell'applicazione. Se si usano contenitori, questo livello in genere si basa sul [motore Docker](https://docs.docker.com/engine/), in esecuzione negli host Linux o negli host Windows. ([i contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) sono supportate a partire da Windows Server 2016. I contenitori Windows è la scelta migliore per le applicazioni .NET Framework esistenti in esecuzione su Windows).

-   **Managed cloud**: quando si sceglie un'opzione cloud gestito, è possibile evitare i costi e la complessità di gestione e che supportano le patch del sistema operativo dell'infrastruttura, le macchine virtuali, sottostante e configurazione della rete. Se si sceglie di eseguire la migrazione tramite la tecnologia IaaS, è responsabile per tutte queste attività e per i costi associati. In un'opzione cloud gestito, è gestire solo le applicazioni e servizi sviluppati personalmente. In genere il provider di servizi cloud gestisce tutto il resto. Esempi di servizi cloud gestiti in Azure [Database SQL di Azure](https://azure.microsoft.com/services/sql-database), [Cache Redis di Azure](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [archiviazione di Azure](https://azure.microsoft.com/services/storage/), [Database di azure per MySQL](https://azure.microsoft.com/services/mysql/), [per Database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)e gestiti i servizi di calcolo, ad esempio [scalabilità di macchine Virtuali imposta](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [servizio App di Azure](https://azure.microsoft.com/services/app-service/), e [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Sviluppo di applicazioni**: È possibile scegliere tra molte lingue quando si compilano applicazioni che vengono eseguiti in contenitori. Questa guida è incentrata sul [.NET](https://www.microsoft.com/net), tuttavia, è possibile sviluppare App basate su contenitore con altri linguaggi, come Java o Node. js, Python, Spring, o passare.

-   **Monitoraggio, i dati di telemetria, registrazione e controllo**: la capacità di monitoraggio e controllo delle applicazioni e i contenitori in esecuzione nel cloud è fondamentale per qualsiasi applicazione ottimizzato per il Cloud. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono i principali strumenti di Microsoft che forniscono il monitoraggio e il controllo per le app ottimizzato per il Cloud.

-   **Provisioning**: strumenti di automazione consentono di eseguire il provisioning dell'infrastruttura e distribuire un'applicazione in più ambienti (produzione, test, staging). Gestione configurazione di un'applicazione e dell'ambiente, è possibile usare strumenti quali Chef e Puppet. Questo livello può anche essere implementato usando approcci più semplici e diretti. Ad esempio, è possibile distribuisce direttamente usando l'interfaccia della riga (Azure CLI) degli strumenti, quindi usare la distribuzione continua e rilasciare le pipeline di gestione [servizi di Azure DevOps](https://visualstudio.microsoft.com/team-services/).

-   **Application Lifecycle Management**: [servizi di Azure DevOps](https://visualstudio.microsoft.com/team-services/) e altri strumenti, come Jenkins, vengono compilati automazione i server che consentono di implementare pipeline CI/CD, tra cui la gestione del rilascio.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate, concentrarsi in modo specifico sui dettagli sul livello di runtime (contenitori Windows). Il materiale sussidiario descrive i modi in cui è possibile distribuire i contenitori di Windows in Windows Server 2016 (e versioni successive) macchine virtuali e istanze di contenitore di Azure. Illustra anche le piattaforme PaaS più avanzate, ad esempio servizio App di Azure e dell'agente di orchestrazione come Azure Service Fabric e Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Le applicazioni monolitiche *possibile* essere ottimizzato per il Cloud

È importante evidenziare che (applicazioni non basate su microservizi) le applicazioni monolitiche *possibile* essere ottimizzato per il Cloud le applicazioni. È possibile compilare ed eseguire applicazioni monolitiche che sfruttano i vantaggi del cloud computing del modello usando una combinazione di contenitori, recapito continuo e DevOps. Se un'applicazione monolitica esistente è corretta per gli obiettivi aziendali, è possibile modernizzare lo e renderlo ottimizzato per il Cloud.

Analogamente, se le applicazioni monolitiche possono essere ottimizzato per il Cloud le applicazioni, le architetture più complesso, ad esempio applicazioni a più livelli possono essere modernizzate ottimizzato per il Cloud delle applicazioni.

>[!div class="step-by-step"]
[Precedente](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Successivo](what-about-cloud-native-applications.md)
