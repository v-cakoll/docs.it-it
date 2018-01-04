---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d2b5b6d4a671a3eb281f49dd60fd3c00ee76f8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="9f713-102">Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="9f713-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="9f713-103">Dopo aver sviluppato alcuni nuovi servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è possibile scegliere di chiamare questi servizi da uno script o da un'applicazione Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="9f713-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="9f713-104">Uno metodo per ottenere questo risultato consiste nel generare un assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], registrare l'assembly con COM, installare l'assembly nella cache di assembly globale e quindi fare riferimento ai tipi COM dal codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f713-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="9f713-105">Quando si distribuisce l'applicazione, è necessario distribuire anche l'assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f713-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="9f713-106">L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale.</span><span class="sxs-lookup"><span data-stu-id="9f713-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="9f713-107">L'interoperabilità COM [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente anche di eseguire le stesse chiamate al servizio senza basarsi su un assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f713-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="9f713-108">Il moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente di chiamare qualsiasi servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un URI dell'endpoint Mex (metadata exchange) che il moniker del servizio usa per estrarre informazioni sui tipi per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9f713-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="9f713-109">In questo argomento viene illustrato come chiamare l'esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] della Guida introduttiva usando un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che specifica un endpoint Mex.</span><span class="sxs-lookup"><span data-stu-id="9f713-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f713-110">Non viene mai creata un'istanza dei tipi definiti dall'assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f713-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="9f713-111">e l'assembly viene usato solo per i metadati.</span><span class="sxs-lookup"><span data-stu-id="9f713-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="9f713-112">Utilizzo del moniker del servizio con un indirizzo Mex</span><span class="sxs-lookup"><span data-stu-id="9f713-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="9f713-113">Creare l'esempio della Guida introduttiva e usare Internet Explorer per passare all'URL (http://localhost/ServiceModelSamples/Service.svc) per verificare che il servizio sia in funzione.</span><span class="sxs-lookup"><span data-stu-id="9f713-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="9f713-114">Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9f713-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="9f713-115">Eseguire l'applicazione o lo script Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f713-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f713-116">Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9f713-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="9f713-117">Per ulteriori informazioni, vedere [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="9f713-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f713-118">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="9f713-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="9f713-119">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="9f713-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f713-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f713-120">See Also</span></span>  
 [<span data-ttu-id="9f713-121">Procedura: Usare il moniker servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="9f713-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="9f713-122">Procedura: usare un moniker servizio con contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="9f713-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
