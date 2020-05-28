---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 8894fdc4fd085b9d55a8fc25043e5258c306024c
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143478"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="c4394-102">Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="c4394-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="c4394-103">Dopo aver sviluppato alcuni nuovi servizi WCF, è possibile decidere di poter chiamare questi servizi da uno script o da un'applicazione Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="c4394-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="c4394-104">Un metodo consiste nel generare un assembly client WCF, registrare l'assembly con COM, installare l'assembly nella GAC, quindi fare riferimento ai tipi COM dal codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c4394-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="c4394-105">Quando si distribuisce l'applicazione, sarà necessario distribuire anche l'assembly client WCF.</span><span class="sxs-lookup"><span data-stu-id="c4394-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="c4394-106">L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale.</span><span class="sxs-lookup"><span data-stu-id="c4394-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="c4394-107">L'interoperabilità COM di WCF consente inoltre di effettuare le stesse chiamate al servizio senza basarsi su un assembly client WCF.</span><span class="sxs-lookup"><span data-stu-id="c4394-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="c4394-108">Il moniker WCF consente di chiamare qualsiasi servizio WCF da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un URI dell'endpoint MEX (Metadata Exchange) che il moniker del servizio utilizza per estrarre le informazioni sul tipo relative al servizio.</span><span class="sxs-lookup"><span data-stu-id="c4394-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="c4394-109">In questo argomento viene illustrato come chiamare l'esempio WCF Introduzione usando un moniker WCF che specifica un endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="c4394-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4394-110">I tipi definiti dall'assembly client WCF non vengono mai creati in realtà.</span><span class="sxs-lookup"><span data-stu-id="c4394-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="c4394-111">e l'assembly viene usato solo per i metadati.</span><span class="sxs-lookup"><span data-stu-id="c4394-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="c4394-112">Utilizzo del moniker del servizio con un indirizzo Mex</span><span class="sxs-lookup"><span data-stu-id="c4394-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="c4394-113">Compilare l'esempio Introduzione e utilizzare Internet Explorer per passare all'URL ( `http://localhost/ServiceModelSamples/Service.svc` ) per assicurarsi che il servizio sia funzionante.</span><span class="sxs-lookup"><span data-stu-id="c4394-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (`http://localhost/ServiceModelSamples/Service.svc`) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="c4394-114">Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c4394-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="c4394-115">Eseguire l'applicazione o lo script Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c4394-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c4394-116">Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="c4394-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="c4394-117">Per altre informazioni, vedere [procedura: pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c4394-118">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="c4394-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="c4394-119">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="c4394-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4394-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c4394-120">See also</span></span>

- [<span data-ttu-id="c4394-121">Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="c4394-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="c4394-122">Procedura: usare un moniker di servizio con i contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="c4394-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
