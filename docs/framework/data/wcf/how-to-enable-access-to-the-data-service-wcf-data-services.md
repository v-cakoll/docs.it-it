---
title: "Procedura: abilitare l'accesso al servizio dati (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: eb9d7cd8e62a73f49fd2b0f2fc2572b01109553b
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364376"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="e9ab4-102">Procedura: abilitare l'accesso al servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="e9ab4-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="e9ab4-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è necessario concedere in modo esplicito l'accesso alle risorse esposte da un servizio dati.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="e9ab4-104">In altre parole, dopo aver creato un nuovo servizio dati, è necessario fornire in modo esplicito l'accesso alle singole risorse come set di entità.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="e9ab4-105">Questo argomento viene illustrato come abilitare la lettura e accesso in scrittura a cinque dell'entità vengono impostate nel servizio dati Northwind creato al completamento di [Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9ab4-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="e9ab4-106">Poiché l'enumerazione <xref:System.Data.Services.EntitySetRights> viene definita tramite <xref:System.FlagsAttribute>, è possibile utilizzare un operatore logico OR per specificare più autorizzazioni per un solo set di entità.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9ab4-107">I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="e9ab4-108">Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="e9ab4-109">Per altre informazioni, vedere [NIB: sicurezza ASP.NET](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span><span class="sxs-lookup"><span data-stu-id="e9ab4-109">For more information, see [NIB: ASP.NET Security](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="e9ab4-110">Per abilitare l'accesso al servizio dati</span><span class="sxs-lookup"><span data-stu-id="e9ab4-110">To enable access to the data service</span></span>  
  
-   <span data-ttu-id="e9ab4-111">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e9ab4-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="e9ab4-112">In questo modo i client saranno in grado di accedere in lettura e scrittura ai set di entità `Orders` e `Order_Details` e solo in lettura ai set di entità `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e9ab4-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ab4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ab4-113">See Also</span></span>  
 [<span data-ttu-id="e9ab4-114">Procedura: sviluppare un servizio WCF in esecuzione in IIS</span><span class="sxs-lookup"><span data-stu-id="e9ab4-114">How to: Develop a WCF Data Service Running on IIS</span></span>](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [<span data-ttu-id="e9ab4-115">Configurazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="e9ab4-115">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
