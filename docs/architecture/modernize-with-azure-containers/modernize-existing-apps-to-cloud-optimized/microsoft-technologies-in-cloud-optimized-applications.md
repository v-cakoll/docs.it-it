---
title: Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69578224"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologie Microsoft nelle applicazioni ottimizzate per il cloud

L'elenco seguente descrive gli strumenti, le tecnologie e le soluzioni riconosciuti come requisiti per le app ottimizzate per il cloud. È possibile adottare elementi ottimizzati per il cloud in modo selettivo o graduale, a seconda delle priorità.

- **Infrastruttura cloud**: infrastruttura che fornisce la piattaforma di calcolo, il sistema operativo, la rete e l'archiviazione. Microsoft Azure è posizionato a questo livello.

- **Runtime**: questo livello fornisce l'ambiente per l'esecuzione dell'applicazione. Se si usano contenitori, questo livello si basa in genere sul [motore Docker](https://docs.docker.com/engine/), in esecuzione negli host Linux o negli host Windows. I[contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) sono supportati a partire da windows server 2016. I contenitori di Windows sono la scelta migliore per le applicazioni .NET Framework esistenti eseguite in Windows.

- **Managed cloud**: quando si sceglie un'opzione cloud gestita, è possibile evitare i costi e la complessità della gestione e del supporto dell'infrastruttura sottostante, delle macchine virtuali, delle patch del sistema operativo e della configurazione di rete. Se si sceglie di eseguire la migrazione tramite IaaS, l'utente è responsabile di tutte queste attività e dei costi associati. In un'opzione cloud gestita è possibile gestire solo le applicazioni e i servizi che si sviluppano. Il provider di servizi cloud gestisce in genere tutto il resto. Esempi di servizi cloud gestiti in Azure includono [database SQL di Azure](https://azure.microsoft.com/services/sql-database), [cache Redis di Azure](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [archiviazione di Azure](https://azure.microsoft.com/services/storage/), [database di Azure per MySQL](https://azure.microsoft.com/services/mysql/), [database di Azure per PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)e servizi di calcolo gestiti come i [set di scalabilità di macchine virtuali](https://azure.microsoft.com/services/virtual-machine-scale-sets/), il [servizio app Azure](https://azure.microsoft.com/services/app-service/)e il [servizio Azure Kubernetes](https://azure.microsoft.com/services/container-service/).

- **Sviluppo**di applicazioni: è possibile scegliere tra molte lingue quando si compilano applicazioni eseguite in contenitori. Questa guida è incentrata su [.NET](https://www.microsoft.com/net), ma è possibile sviluppare app basate su contenitori usando altri linguaggi, ad esempio node. js, Python, Spring/Java o go.

- **Monitoraggio, telemetria, registrazione e controllo**: la possibilità di monitorare e controllare le applicazioni e i contenitori in esecuzione nel cloud è essenziale per qualsiasi applicazione ottimizzata per il cloud. [Applicazione Azure Insights](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sono gli strumenti Microsoft principali che forniscono il monitoraggio e il controllo per le app ottimizzate per il cloud.

- **Provisioning**: gli strumenti di automazione consentono di effettuare il provisioning dell'infrastruttura e distribuire un'applicazione in più ambienti (produzione, test, gestione temporanea). È possibile usare strumenti come chef e Puppet per gestire la configurazione e l'ambiente di un'applicazione. Questo livello può essere implementato anche usando approcci più semplici e più diretti. Ad esempio, è possibile distribuire direttamente usando gli strumenti dell'interfaccia della riga di comando di Azure (interfaccia della riga di comando di Azure) e quindi usare le pipeline di distribuzione continua e di gestione delle versioni in [Azure DevOps Services](https://azure.microsoft.com/services/devops/).

- **Ciclo di vita dell'applicazione**: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) e altri strumenti, ad esempio Jenkins, sono server di automazione compilati che consentono di implementare pipeline ci/CD, inclusa la gestione delle versioni.

Le sezioni successive di questo capitolo e le procedure dettagliate correlate si concentrano in particolare sui dettagli relativi al livello di runtime (contenitori di Windows). Le linee guida illustrano i modi in cui è possibile distribuire i contenitori di Windows in macchine virtuali di Windows Server 2016 (e versioni successive) e istanze di contenitore di Azure. Vengono inoltre illustrate piattaforme PaaS più avanzate come servizio app Azure e agente di orchestrazione come il servizio Azure Kubernetes.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Le applicazioni monolitiche *possono* essere ottimizzate per il cloud

È importante evidenziare che le applicazioni monolitiche, ovvero le applicazioni che non sono basate su microservizi, *possono* essere applicazioni ottimizzate per il cloud. È possibile creare e usare applicazioni monolitiche che sfruttano i vantaggi del modello di cloud computing usando una combinazione di contenitori, recapito continuo e DevOps. Se un'applicazione monolitica esistente è giusta per gli obiettivi aziendali, è possibile modernizzarla e renderla ottimizzata per il cloud.

Analogamente, se le applicazioni monolitiche possono essere applicazioni ottimizzate per il cloud, altre architetture più complesse come le applicazioni a più livelli possono anche essere modernizzate come applicazioni ottimizzate per il cloud.

>[!div class="step-by-step"]
>[Precedente](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[Successivo](what-about-cloud-native-applications.md)
