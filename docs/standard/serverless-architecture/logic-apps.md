---
title: App di Azure per la logica - App senza server
description: Le App per la logica di Azure consentono di compilare scalabile flussi di lavoro automatizzati che integrano App e i dati tra cloud dei servizi e sistemi locali.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 019539f0da1d38259870907c38ed0eb6a62f1929
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369948"
---
# <a name="azure-logic-apps"></a>App per la logica di Azure

[Le App per la logica di Azure](https://docs.microsoft.com/azure/logic-apps) offre un motore senza server per compilare flussi di lavoro automatizzati per integrare le App e i dati tra servizi cloud e sistemi locali. È compilare flussi di lavoro usando una finestra di progettazione. È possibile attivare i flussi di lavoro basati su eventi o i timer e sfrutta i connettori per le applicazioni di integrazione e facilitare la comunicazione business to business (B2B). App per la logica si integra perfettamente con funzioni di Azure.

![Logo di App per la logica di Azure](./media/logic-apps-logo.png)

App per la logica è possibile eseguire più semplicemente connettere i servizi cloud (ad esempio, le funzioni) con le risorse cloud (ad esempio code e i database). È anche possibile orchestrare flussi di lavoro in locale con il gateway da sito locale. Ad esempio, è possibile usare l'App per la logica per attivare una locale stored procedure SQL in risposta a un evento basato sul cloud o per la logica condizionale nel flusso di lavoro. Altre informazioni sulle [ci si connette a origini dati locali con Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Architettura di App per la logica](./media/logic-apps-architecture.png)

Come funzioni di Azure, è avviare i flussi di lavoro di App per la logica con un trigger. Esistono molti trigger per cui scegliere. L'acquisizione di seguito viene illustrato solo alcuni dei più popolari quelli di centinaia disponibili.

![Trigger delle App per la logica](./media/logic-app-triggers.png)

Dopo aver attivato l'app, è possibile utilizzare la finestra di progettazione visiva per creare i passaggi, i cicli, le condizioni e azioni. Tutti i dati inseriti in un passaggio precedente sono disponibili per l'utilizzo nei passaggi successivi. Il flusso di lavoro seguente carica gli URL da un database di COSMOS DB. Rileva quelli scegliendo tra tantissimi `t.co` quindi eseguita la ricerca relativa su Twitter. Se vengono trovati i TWEET corrispondenti, aggiorna i documenti con i TWEET correlati chiamando la funzione.

![Flusso di lavoro App per la logica](./media/logic-app-workflow.png)

Il dashboard di App per la logica mostra la cronologia di esecuzione dei flussi di lavoro e che ogni esecuzione completata correttamente o meno. È possibile passare in qualsiasi esecuzione specificata e controllare i dati usati da ogni passaggio per la risoluzione dei problemi. App per la logica include anche modelli esistenti è possibile modificare e sono particolarmente adatti per flussi di lavoro aziendali complessi.

Per altre informazioni, vedere [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).

>[!div class="step-by-step"]
[Precedente](application-insights.md)
[Successivo](event-grid.md)