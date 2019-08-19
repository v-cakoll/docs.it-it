---
title: App per la logica di Azure-app senza server
description: App per la logica di Azure consente di creare flussi di lavoro scalabili automatizzati che integrano le app e i dati tra servizi cloud e sistemi locali.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577454"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="ac47f-103">App per la logica di Azure</span><span class="sxs-lookup"><span data-stu-id="ac47f-103">Azure Logic Apps</span></span>

<span data-ttu-id="ac47f-104">[App](https://docs.microsoft.com/azure/logic-apps) per la logica di Azure offre un motore senza server per creare flussi di lavoro automatizzati per integrare app e dati tra i servizi cloud e i sistemi locali.</span><span class="sxs-lookup"><span data-stu-id="ac47f-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="ac47f-105">I flussi di lavoro vengono compilati utilizzando una finestra di progettazione visiva.</span><span class="sxs-lookup"><span data-stu-id="ac47f-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="ac47f-106">È possibile attivare flussi di lavoro basati su eventi o timer e sfruttare i connettori per le applicazioni di integrazione e semplificare le comunicazioni business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="ac47f-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="ac47f-107">App per la logica si integra perfettamente con funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="ac47f-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Logo app per la logica di Azure](./media/logic-apps-logo.png)

<span data-ttu-id="ac47f-109">Le app per la logica non possono semplicemente connettere i servizi cloud, ad esempio le funzioni, con risorse cloud, ad esempio code e database.</span><span class="sxs-lookup"><span data-stu-id="ac47f-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="ac47f-110">È anche possibile orchestrare i flussi di lavoro locali con il gateway locale.</span><span class="sxs-lookup"><span data-stu-id="ac47f-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="ac47f-111">Ad esempio, è possibile usare l'app per la logica per attivare un stored procedure SQL locale in risposta a un evento basato sul cloud o a una logica condizionale nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac47f-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="ac47f-112">Altre informazioni sulla [connessione a origini dati locali con il gateway dati locale di Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span><span class="sxs-lookup"><span data-stu-id="ac47f-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Architettura di app per la logica](./media/logic-apps-architecture.png)

<span data-ttu-id="ac47f-114">Analogamente alle funzioni di Azure, è possibile avviare i flussi di lavoro delle app per la logica con un trigger.</span><span class="sxs-lookup"><span data-stu-id="ac47f-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="ac47f-115">È possibile scegliere tra molti trigger.</span><span class="sxs-lookup"><span data-stu-id="ac47f-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="ac47f-116">L'acquisizione seguente mostra solo alcuni dei più diffusi da centinaia disponibili.</span><span class="sxs-lookup"><span data-stu-id="ac47f-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Trigger di app per la logica](./media/logic-app-triggers.png)

<span data-ttu-id="ac47f-118">Una volta attivata l'app, è possibile usare la finestra di progettazione visiva per compilare passaggi, cicli, condizioni e azioni.</span><span class="sxs-lookup"><span data-stu-id="ac47f-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="ac47f-119">Tutti i dati inseriti in un passaggio precedente sono disponibili per l'uso nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="ac47f-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="ac47f-120">Il flusso di lavoro seguente carica URL da un database CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="ac47f-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="ac47f-121">Trova quelli con un host di `t.co` e quindi li cerca su Twitter.</span><span class="sxs-lookup"><span data-stu-id="ac47f-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="ac47f-122">Se vengono trovati Tweet corrispondenti, i documenti vengono aggiornati con i Tweet correlati chiamando una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac47f-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Flusso di lavoro dell'app per la logica](./media/logic-app-workflow.png)

<span data-ttu-id="ac47f-124">Il Dashboard app per la logica Mostra la cronologia di esecuzione dei flussi di lavoro e se ogni esecuzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac47f-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="ac47f-125">È possibile passare a una determinata esecuzione ed esaminare i dati utilizzati da ogni passaggio per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ac47f-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="ac47f-126">App per la logica fornisce anche modelli esistenti che è possibile modificare e sono particolarmente adatti per flussi di lavoro aziendali complessi.</span><span class="sxs-lookup"><span data-stu-id="ac47f-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="ac47f-127">Per altre informazioni, vedere [app](https://docs.microsoft.com/azure/logic-apps)per la logica di Azure.</span><span class="sxs-lookup"><span data-stu-id="ac47f-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ac47f-128">[Precedente](application-insights.md)
>[Successivo](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="ac47f-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
