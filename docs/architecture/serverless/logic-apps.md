---
title: App per la logica di Azure - App senza serverAzure Logic Apps - Serverless apps
description: Le app per la logica di Azure consentono la creazione di flussi di lavoro scalabili automatizzati che integrano app e dati tra servizi cloud e sistemi locali.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577454"
---
# <a name="azure-logic-apps"></a>App per la logica di Azure

[App per](https://docs.microsoft.com/azure/logic-apps) la logica di Azure offre un motore senza server per creare flussi di lavoro automatizzati per integrare app e dati tra servizi cloud e sistemi locali. I flussi di lavoro vengono compilati utilizzando una finestra di progettazione visiva. È possibile attivare i flussi di lavoro in base a eventi o timer e sfruttare i connettori alle applicazioni di integrazione e facilitare la comunicazione business-to-business (B2B). App per la logica si integra perfettamente con Funzioni di Azure.Logic Apps integrates seamlessly with Azure Functions.

![Logo delle app per la logica di AzureAzure Logic Apps logo](./media/logic-apps-logo.png)

Le app per la logica possono fare di più che connettere i servizi cloud (come le funzioni) con le risorse cloud (ad esempio code e database). È anche possibile orchestrare i flussi di lavoro locali con il gateway locale. Ad esempio, è possibile usare l'app per la logica per attivare una stored procedure SQL locale in risposta a un evento basato su cloud o a una logica condizionale nel flusso di lavoro. Altre informazioni sulla connessione a origini dati locali con il gateway dati locale di Azure.Learn more about [Connecting to on-premises data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Architettura delle app per la logica](./media/logic-apps-architecture.png)

Come Funzioni di Azure, è possibile avviare i flussi di lavoro dell'app per la logica con un trigger. Ci sono molti trigger tra cui scegliere. La cattura seguente mostra solo alcuni dei più popolari su centinaia che sono disponibili.

![Trigger delle app per la logica](./media/logic-app-triggers.png)

Dopo aver attivato l'app, puoi usare la finestra di progettazione visiva per compilare passaggi, cicli, condizioni e azioni. Tutti i dati ingeriti in un passaggio precedente sono disponibili per l'utilizzo nei passaggi successivi. Il flusso di lavoro seguente carica gli URL da un database CosmosDB. Trova quelli con una `t.co` miriade di poi cerca rli su Twitter. Se trova i tweet corrispondenti, aggiorna i documenti con i tweet correlati chiamando una funzione.

![Flusso di lavoro dell'app per la logica](./media/logic-app-workflow.png)

Il dashboard App per la logica mostra la cronologia dell'esecuzione dei flussi di lavoro e indica se ogni esecuzione è stata completata correttamente o meno. È possibile passare a qualsiasi esecuzione e controllare i dati utilizzati da ogni passaggio per la risoluzione dei problemi. App per la logica fornisce anche modelli esistenti che è possibile modificare e sono adatti per flussi di lavoro aziendali complessi.

Per altre informazioni, vedere [App per la logica](https://docs.microsoft.com/azure/logic-apps)di Azure.To learn more, see Azure Logic Apps .

>[!div class="step-by-step"]
>[Successivo](application-insights.md)
>[precedente](event-grid.md)
