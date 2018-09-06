---
title: 'Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032397"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="f8563-102">Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8563-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="f8563-103">È possibile usare la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="f8563-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="f8563-104">In questo modo è possibile accedere più facilmente a un servizio dati in un'applicazione client sviluppata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8563-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="f8563-105">Al completamento di questa procedura, verranno generate classi di dati in base ai metadati ottenuti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="f8563-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="f8563-106">Per altre informazioni, vedere [generazione della libreria Client di servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8563-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="f8563-107">Aggiungere un riferimento al servizio dati</span><span class="sxs-lookup"><span data-stu-id="f8563-107">Add a data service reference</span></span>

1. <span data-ttu-id="f8563-108">(Facoltativo) Se il servizio dati non fa parte della soluzione e non è già in esecuzione, avviare il servizio dati e prendere nota dell'URI del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="f8563-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="f8563-109">In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto client e quindi selezionare **Add** > **riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="f8563-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="f8563-110">Se il servizio dati fa parte della soluzione corrente, fare clic su **Discover**.</span><span class="sxs-lookup"><span data-stu-id="f8563-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="f8563-111">oppure</span><span class="sxs-lookup"><span data-stu-id="f8563-111">-or-</span></span>

     <span data-ttu-id="f8563-112">Nel **indirizzi** nella casella di testo digitare l'URL di base del servizio dati, ad esempio `http://localhost:1234/Northwind.svc`, quindi fare clic su **passare**.</span><span class="sxs-lookup"><span data-stu-id="f8563-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="f8563-113">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8563-113">Select **OK**.</span></span>

     <span data-ttu-id="f8563-114">Un nuovo file di codice che contiene le classi di dati che possono accedere e interagire con le risorse del servizio dati viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="f8563-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8563-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8563-115">See also</span></span>

- [<span data-ttu-id="f8563-116">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="f8563-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)