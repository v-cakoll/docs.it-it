---
title: 'Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 702eda2d4641dc2efdac40f9d730228063e306a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="1b65d-102">Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="1b65d-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="1b65d-103">È possibile utilizzare il **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b65d-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="1b65d-104">In questo modo è possibile accedere più facilmente a un servizio dati in un'applicazione client sviluppata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1b65d-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="1b65d-105">Al completamento di questa procedura, verranno generate classi di dati in base ai metadati ottenuti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="1b65d-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="1b65d-106">Per ulteriori informazioni, vedere [la generazione della libreria Client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1b65d-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="1b65d-107">Per aggiungere un riferimento al servizio dati</span><span class="sxs-lookup"><span data-stu-id="1b65d-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="1b65d-108">(Facoltativo) Se il servizio dati non fa parte della soluzione e non è già in esecuzione, avviare il servizio dati e prendere nota dell'URI del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="1b65d-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="1b65d-109">Fare clic sul progetto client e quindi selezionare **Aggiungi riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="1b65d-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="1b65d-110">Se il servizio dati fa parte della soluzione corrente, fare clic su **Discover**.</span><span class="sxs-lookup"><span data-stu-id="1b65d-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="1b65d-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="1b65d-111">-or-</span></span>  
  
     <span data-ttu-id="1b65d-112">Nel **indirizzo** nella casella di testo digitare l'URL di base del servizio dati, ad esempio `http://localhost:1234/Northwind.svc`, quindi fare clic su **passare**.</span><span class="sxs-lookup"><span data-stu-id="1b65d-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="1b65d-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b65d-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="1b65d-114">Aggiunge un nuovo file di codice contenente le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti.</span><span class="sxs-lookup"><span data-stu-id="1b65d-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b65d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b65d-115">See Also</span></span>  
 [<span data-ttu-id="1b65d-116">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="1b65d-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
