---
title: Monitorare i servizi delle applicazioni nei contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio di architetture di contenitore
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641207"
---
# <a name="monitor-containerized-application-services"></a>Monitorare i servizi delle applicazioni nei contenitori

È fondamentale per le applicazioni di suddividere in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'applicazione.

## <a name="azure-monitor"></a>Monitoraggio di Azure

[Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/) è un servizio di analitica estendibile che consente di monitorare l'applicazione in tempo reale. Consente di rilevare e diagnosticare i problemi di prestazioni e comprendere ciò che effettivamente eseguite dagli utenti all'app. È progettato per gli sviluppatori, con lo scopo di aiutarti a migliorare continuamente le prestazioni e usabilità del servizi o applicazioni. Monitoraggio di Azure funziona con web/servizi e autonoma delle App su una vasta gamma di piattaforme quali .NET, Java, Node. js e molte altre piattaforme, ospitate in locale o nel cloud.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Panoramica del monitoraggio di Azure** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **Informazioni su Azure Application Insights** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Che cos'è metriche di monitoraggio di Azure?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Soluzione monitoraggio contenitori in Monitoraggio di Azure** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Servizi di protezione e backup

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

- **Le risorse locali**. Con [un cloud ibrido davvero coerente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Precedente](manage-production-docker-environments.md)
>[Successivo](../key-takeaways/index.md)
