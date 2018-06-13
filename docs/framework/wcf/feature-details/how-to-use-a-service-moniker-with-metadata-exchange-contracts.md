---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491250"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="4d4f0-102">Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati</span><span class="sxs-lookup"><span data-stu-id="4d4f0-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="4d4f0-103">Dopo aver sviluppato alcuni nuovi servizi WCF, si potrebbe decidere che si desidera essere in grado di chiamare questi servizi da uno script o un'applicazione Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="4d4f0-104">Un metodo, è possibile generare un assembly client WCF, registrare l'assembly con COM, installare l'assembly nella Global Assembly Cache e quindi fare riferimento ai tipi COM dal codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="4d4f0-105">Quando si distribuisce l'applicazione, è necessario distribuire anche l'assembly Client WCF.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="4d4f0-106">L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="4d4f0-107">Interoperabilità COM WCF consente inoltre di apportare le stesse chiamate al servizio senza basarsi su un assembly client WCF.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="4d4f0-108">Il moniker WCF consente di chiamare qualsiasi servizio WCF da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un endpoint di exchange (Mex) metadati URI che utilizza il moniker del servizio per estrarre tipo informazioni sul servizio.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="4d4f0-109">In questo argomento viene descritto come chiamare l'esempio di recupero WCF usando un moniker WCF che specifica un endpoint Mex.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d4f0-110">I tipi definiti dall'assembly client WCF sono mai creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="4d4f0-111">e l'assembly viene usato solo per i metadati.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="4d4f0-112">Utilizzo del moniker del servizio con un indirizzo Mex</span><span class="sxs-lookup"><span data-stu-id="4d4f0-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="4d4f0-113">Compilare l'esempio di Guida introduttiva e usare Internet Explorer per passare all'URL (http://localhost/ServiceModelSamples/Service.svc) per verificare che il servizio sia in funzione.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="4d4f0-114">Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d4f0-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="4d4f0-115">Eseguire l'applicazione o lo script Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d4f0-116">Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="4d4f0-117">Per ulteriori informazioni, vedere [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4d4f0-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d4f0-118">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="4d4f0-119">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4f0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d4f0-120">See Also</span></span>  
 [<span data-ttu-id="4d4f0-121">Procedura: Usare il moniker servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="4d4f0-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="4d4f0-122">Procedura: usare un moniker servizio con contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="4d4f0-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
