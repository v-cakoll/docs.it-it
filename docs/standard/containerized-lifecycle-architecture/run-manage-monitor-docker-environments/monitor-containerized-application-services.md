---
title: Monitorare i servizi delle applicazioni in contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio di architetture di contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975745"
---
# <a name="monitor-containerized-application-services"></a>Monitorare i servizi delle applicazioni in contenitori

È fondamentale per le applicazioni di suddividere in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'applicazione.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) è un servizio di analitica estendibile che consente di monitorare l'applicazione in tempo reale. Consente di rilevare e diagnosticare i problemi di prestazioni e comprendere ciò che effettivamente eseguite dagli utenti all'app. È progettato per gli sviluppatori, con lo scopo di aiutarti a migliorare continuamente le prestazioni e usabilità del servizi o applicazioni. Application Insights funziona con web/servizi e autonoma delle App su una vasta gamma di piattaforme quali .NET, Java, Node. js e molte altre piattaforme, ospitate in locale o nel cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analizzare le app Docker in ambienti di controllo di qualità con Application Insights

Per quanto attiene a Docker, è possibile grafico gli eventi del ciclo di vita e i contatori delle prestazioni da contenitori Docker in Application Insights. È sufficiente eseguire la [immagine Docker di Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) come un contenitore nell'host che verrà visualizzati i contatori delle prestazioni per l'host e per le altre immagini di Docker. Questa immagine Docker di Application Insights (figura 6 - 1) consente di monitorare le applicazioni in contenitori, raccogliendo i dati di telemetria sulle prestazioni e l'attività dell'host Docker (vale a dire, le macchine virtuali Linux), i contenitori Docker e le applicazioni in esecuzione all'interno di essi.

![esempio](./media/image1.png)

**Figura 6-1**. Monitoraggio dei contenitori e host Docker di Application Insights

Quando si esegue la [immagine Docker di Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) nell'host Docker, trarre vantaggio da quanto segue:

- Dati di telemetria su tutti i contenitori in esecuzione nell'host del ciclo di vita, avviare, arrestare e così via.

- Contatori delle prestazioni per tutti i contenitori: CPU, memoria, utilizzo della rete e altro ancora.

- Se è installato anche [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) nelle App in esecuzione nei contenitori, tutti i dati di telemetria di tali App avranno proprietà aggiuntive che identificano il contenitore e il computer host. Quindi, ad esempio, se si dispone di istanze di un'app in esecuzione in più di un host, facilmente sarà in grado di filtrare i dati di telemetria dell'app dall'host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configurazione di Application Insights per monitorare applicazioni Docker e l'host Docker

Per creare una risorsa di Application Insights, seguire le istruzioni riportate negli articoli presentati nell'elenco che segue. Portale di Azure creerà lo script necessario per l'utente.

- **Monitorare le applicazioni Docker in Application Insights:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- **Immagine di Docker Insights dell'applicazione in Docker Hub e GitHub:** \
  <https://hub.docker.com/r/microsoft/applicationinsights/> e \
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- **Configurare Application Insights per App web ASP.NET e ASP.NET Core:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- **Application Insights per pagine web:**  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a>Sicurezza, backup e servizi di monitoraggio

Esistono molte attività di supporto con un numero elevato di dettagli che è necessario gestire per assicurarsi che l'infrastruttura e applicazioni siano in condizione di notch superiore per supportare le esigenze aziendali e la situazione diventa più complessa nell'area di autenticazione microservizi, pertanto è necessario un modo per avere visualizzazioni generali e dettagliate quando è necessario intervenire.

Azure offre gli strumenti per gestire e fornire una vista unificata dei quattro aspetti critici di risorse del cloud e locali:

- **Sicurezza**. Con [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/).
  - Ottenere visibilità completa e il controllo della sicurezza delle macchine virtuali, App e carichi di lavoro.
  - Centralizzare la gestione dei criteri di sicurezza e integra gli strumenti e processi esistenti.
  - Rilevare le minacce effettive con analitica avanzata.

- **Backup**. Con [Backup di Azure](https://azure.microsoft.com/services/backup/).
  - Evitare interruzioni aziendali costose, soddisfano gli obiettivi di conformità e proteggere i dati da ransomware ed errori umani.
  - Mantenere i dati di backup crittografati in transito e inattivi.
  - Verificare l'accesso in base a multi-factor authentication per evitare l'uso non autorizzato.

- **Monitoraggio**. Con [il monitoraggio di Azure](https://azure.microsoft.com/solutions/monitoring/), [Log Analitica](https://azure.microsoft.com/services/log-analytics/), e [Application Insights](https://azure.microsoft.com/services/application-insights/).
  - Ottieni la visibilità completa dell'integrità e prestazioni dei carichi di lavoro di Azure, App e infrastruttura.
  - Raccogliere i dati da qualsiasi origine e Ottieni informazioni dettagliate avanzate nelle macchine virtuali, contenitori e applicazioni.
  - Trovare le informazioni necessarie tramite query interattive e ricerca full-text. 
  - Eseguire l'analisi causa radice con analitica avanzata, inclusi algoritmi di machine learning.

- **Le risorse locali**. Con [un cloud ibrido davvero coerente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Precedente](manage-production-docker-environments.md)
>[Successivo](../key-takeaways/index.md)
