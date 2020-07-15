---
title: Monitorare i servizi delle applicazioni nei contenitori
description: Informazioni su alcuni aspetti fondamentali del monitoraggio delle architetture dei contenitori
ms.date: 02/15/2019
ms.openlocfilehash: e41df53ad94784436442c3cf7defed3fab510455
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374442"
---
# <a name="monitor-containerized-application-services"></a>Monitorare i servizi delle applicazioni nei contenitori

È fondamentale per le applicazioni suddivise in più contenitori e microservizi avere un modo per monitorare e analizzare il comportamento dell'intera applicazione.

## <a name="azure-monitor"></a>Monitoraggio di Azure

[Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/) è un servizio di analisi estendibile che consente di monitorare un'applicazione attiva. Il servizio consente di rilevare e diagnosticare problemi di prestazioni e individuare le operazioni effettivamente eseguite dagli utenti nell'applicazione. Il servizio è progettato per gli sviluppatori con lo scopo di favorire un continuo miglioramento delle prestazioni e dell'usabilità dei servizi o delle applicazioni. Monitoraggio di Azure può essere usato sia con app Web o servizi che con app autonome in numerose piattaforme come .NET, Java, Node.js e molte altre piattaforme, ospitate in locale o nel cloud.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Panoramica di monitoraggio di Azure** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **Informazioni su Azure Application Insights** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Cosa sono le metriche di Monitoraggio di Azure?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Soluzione di monitoraggio del contenitore in monitoraggio di Azure** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Servizi di sicurezza e backup

Poiché esistono molte operazioni di supporto con numerosi dettagli che è necessario gestire per garantire che le applicazioni e l'infrastruttura siano nelle condizioni ottimali per rispondere alle esigenze aziendali e la situazione diventa più complessa per i microservizi, è necessario avere a disposizione viste d'insieme e viste dettagliate per eseguire un'azione.

Azure include gli strumenti per gestire e offrire una vista unificata dei quattro aspetti critici delle risorse del cloud e locali:

- **Sicurezza**. Con [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/).
  - Ottenere visibilità completa e controllo della sicurezza di macchine virtuali, app e carichi di lavoro.
  - Centralizzare la gestione dei criteri di sicurezza e integrare i processi e gli strumenti esistenti.
  - Rilevare le minacce effettive con analisi avanzata.

- **Backup**. Con [Backup di Azure](https://azure.microsoft.com/services/backup/).
  - Evitare costose interruzioni dell'attività aziendale, raggiungere gli obiettivi di conformità e proteggere i dati da ransomware ed errori umani.
  - Mantenere crittografati i dati di backup in transito o inattivi.
  - Garantire un accesso basato sull'autenticazione a più fattori per impedire l'uso non autorizzato.

- **Risorse locali**. Con [soluzioni cloud ibride](https://azure.microsoft.com/solutions/hybrid-cloud-app/).

>[!div class="step-by-step"]
>[Precedente](manage-production-docker-environments.md) 
> [Avanti](../key-takeaways/index.md)
