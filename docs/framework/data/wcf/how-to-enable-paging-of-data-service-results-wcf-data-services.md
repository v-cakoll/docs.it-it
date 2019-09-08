---
title: 'Procedura: Abilita paging dei risultati del servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 82b4d0fd3531778ab494d6526a56b092edf9481a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780044"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="4071e-102">Procedura: Abilita paging dei risultati del servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="4071e-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="4071e-103">consente di limitare il numero di entità restituite da una query del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="4071e-103">enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="4071e-104">I limiti di paging vengono definiti nel metodo chiamato all'avvio del servizio e possono essere impostati separatamente per ogni set di entità.</span><span class="sxs-lookup"><span data-stu-id="4071e-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="4071e-105">Quando il paging è abilitato, la voce finale nel feed contiene un collegamento alla pagina di dati successiva.</span><span class="sxs-lookup"><span data-stu-id="4071e-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="4071e-106">Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4071e-106">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="4071e-107">In questo argomento viene illustrato come modificare un servizio dati per abilitare il paging dei set di entità `Customers` e `Orders` restituiti.</span><span class="sxs-lookup"><span data-stu-id="4071e-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="4071e-108">Nell'esempio riportato in questo argomento viene usato il servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="4071e-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="4071e-109">Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4071e-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="4071e-110">Modalità di abilitazione del paging dei set di entità Customers e Orders restituiti</span><span class="sxs-lookup"><span data-stu-id="4071e-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
- <span data-ttu-id="4071e-111">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4071e-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="4071e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4071e-112">See also</span></span>

- [<span data-ttu-id="4071e-113">Caricamento di contenuto posticipato</span><span class="sxs-lookup"><span data-stu-id="4071e-113">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="4071e-114">Procedura: Caricare i risultati di paging</span><span class="sxs-lookup"><span data-stu-id="4071e-114">How to: Load Paged Results</span></span>](how-to-load-paged-results-wcf-data-services.md)
