---
title: App per la logica di Azure-app senza server
description: App per la logica di Azure consente di creare flussi di lavoro scalabili automatizzati che integrano le app e i dati tra servizi cloud e sistemi locali.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577454"
---
# <a name="azure-logic-apps"></a>App per la logica di Azure

[App](https://docs.microsoft.com/azure/logic-apps) per la logica di Azure offre un motore senza server per creare flussi di lavoro automatizzati per integrare app e dati tra i servizi cloud e i sistemi locali. I flussi di lavoro vengono compilati utilizzando una finestra di progettazione visiva. È possibile attivare flussi di lavoro basati su eventi o timer e sfruttare i connettori per le applicazioni di integrazione e semplificare le comunicazioni business-to-business (B2B). App per la logica si integra perfettamente con funzioni di Azure.

![Logo app per la logica di Azure](./media/logic-apps-logo.png)

Le app per la logica non possono semplicemente connettere i servizi cloud, ad esempio le funzioni, con risorse cloud, ad esempio code e database. È anche possibile orchestrare i flussi di lavoro locali con il gateway locale. Ad esempio, è possibile usare l'app per la logica per attivare un stored procedure SQL locale in risposta a un evento basato sul cloud o a una logica condizionale nel flusso di lavoro. Altre informazioni sulla [connessione a origini dati locali con il gateway dati locale di Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Architettura di app per la logica](./media/logic-apps-architecture.png)

Analogamente alle funzioni di Azure, è possibile avviare i flussi di lavoro delle app per la logica con un trigger. È possibile scegliere tra molti trigger. L'acquisizione seguente mostra solo alcuni dei più diffusi da centinaia disponibili.

![Trigger di app per la logica](./media/logic-app-triggers.png)

Una volta attivata l'app, è possibile usare la finestra di progettazione visiva per compilare passaggi, cicli, condizioni e azioni. Tutti i dati inseriti in un passaggio precedente sono disponibili per l'uso nei passaggi successivi. Il flusso di lavoro seguente carica URL da un database CosmosDB. Trova quelli con un host di `t.co` quindi li cerca su Twitter. Se vengono trovati Tweet corrispondenti, i documenti vengono aggiornati con i Tweet correlati chiamando una funzione.

![Flusso di lavoro dell'app per la logica](./media/logic-app-workflow.png)

Il Dashboard app per la logica Mostra la cronologia di esecuzione dei flussi di lavoro e se ogni esecuzione è stata completata correttamente. È possibile passare a una determinata esecuzione ed esaminare i dati utilizzati da ogni passaggio per la risoluzione dei problemi. App per la logica fornisce anche modelli esistenti che è possibile modificare e sono particolarmente adatti per flussi di lavoro aziendali complessi.

Per altre informazioni, vedere [app](https://docs.microsoft.com/azure/logic-apps)per la logica di Azure.

>[!div class="step-by-step"]
>[Precedente](application-insights.md)
>[Successivo](event-grid.md)
