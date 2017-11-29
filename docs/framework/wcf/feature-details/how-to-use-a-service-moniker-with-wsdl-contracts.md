---
title: 'Procedura: usare un moniker di servizio con i contratti WSDL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d98fb82984fec4acbb8b95d4bc4667468804ff9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a><span data-ttu-id="cdd4e-102">Procedura: usare un moniker di servizio con i contratti WSDL</span><span class="sxs-lookup"><span data-stu-id="cdd4e-102">How to: Use a Service Moniker with WSDL Contracts</span></span>
<span data-ttu-id="cdd4e-103">In alcune situazioni può essere necessario disporre di un client per l'interoperabilità COM completamente autonomo.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-103">There are situations when you may want to have a completely self-contained COM Interop client.</span></span> <span data-ttu-id="cdd4e-104">Il servizio che si desidera chiamare può non esporre un endpoint MEX e la DLL del client WCF può non essere registrata per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-104">The service you want to call may not expose a MEX endpoint, and the WCF client DLL may not be registered for COM interop.</span></span> <span data-ttu-id="cdd4e-105">In questi casi è possibile creare un file WSDL che descriva il servizio e lo passi nel moniker del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-105">In these cases, you can create a WSDL file that describes the service and pass it into the WCF service moniker.</span></span> <span data-ttu-id="cdd4e-106">In questo argomento viene illustrato come chiamare l'esempio WCF della Guida introduttiva utilizzando un moniker WSDL WCF.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-106">This topic describes how to call the Getting Started WCF sample using a WCF WSDL moniker.</span></span>  
  
### <a name="using-the-wsdl-service-moniker"></a><span data-ttu-id="cdd4e-107">Utilizzo del moniker del servizio WSDL</span><span class="sxs-lookup"><span data-stu-id="cdd4e-107">Using the WSDL service moniker</span></span>  
  
1.  <span data-ttu-id="cdd4e-108">Aprire e compilare la soluzione di esempio GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-108">Open and build the GettingStarted sample solution.</span></span>  
  
2.  <span data-ttu-id="cdd4e-109">Aprire Internet Explorer e immettere http://localhost/ServiceModelSamples/Service.svc per assicurarsi che il servizio sia in funzione.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-109">Open Internet Explorer and browse to http://localhost/ServiceModelSamples/Service.svc to make sure that the service is working.</span></span>  
  
3.  <span data-ttu-id="cdd4e-110">Nel file Service.cs aggiungere l'attributo seguente alla classe CalculatorService:</span><span class="sxs-lookup"><span data-stu-id="cdd4e-110">In the Service.cs file, add the following attribute on the CalculatorService class:</span></span>  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  <span data-ttu-id="cdd4e-111">Aggiungere un spazio dei nomi dell'associazione al servizio App.config:</span><span class="sxs-lookup"><span data-stu-id="cdd4e-111">Add a binding namespace to the service App.config:</span></span>  
  
  
  
5.  <span data-ttu-id="cdd4e-112">Creare un file WSDL che deve essere letto dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-112">Create a WSDL file for the application to read.</span></span> <span data-ttu-id="cdd4e-113">Poiché gli spazi dei nomi vengono aggiunti nei passaggi 3 e 4, è possibile utilizzare Internet Explorer per eseguire una query per l'intera descrizione WSDL del servizio immettendo http://localhost/ServiceModelSamples/Service.svc?wsdl.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-113">Because the namespaces were added in steps 3 and 4, you can use IE to query for the entire WSDL description of the service by browsing to http://localhost/ServiceModelSamples/Service.svc?wsdl.</span></span> <span data-ttu-id="cdd4e-114">È quindi possibile salvare il file da Internet Explorer come serviceWSDL.xml.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-114">You can then save the file from Internet Explorer as serviceWSDL.xml.</span></span> <span data-ttu-id="cdd4e-115">Se non si specificano gli spazi dei nomi nei passaggi 3 e 4, il documento WSDL restituito dalla query sull'URL precedente non sarà il WSDL completo.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-115">If you do not specify the namespaces in steps 3 and 4, the WSDL document returned from querying the above URL will not be the complete WSDL.</span></span> <span data-ttu-id="cdd4e-116">Il documento WSDL restituito includerà molte istruzioni di importazione che consentono di importare altri documenti WSDL.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-116">The WSDL document returned will include several import statements that import other WSDL documents.</span></span> <span data-ttu-id="cdd4e-117">Sarà quindi necessario esaminare ogni istruzione di importazione e compilare il documento WSDL completo, combinando il WSDL restituito dal servizio con il WSDL importato.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-117">You will have to go through each import statement and build the complete WSDL document, combining the WSDL returned from the service with the WSDL imported.</span></span>  
  
6.  <span data-ttu-id="cdd4e-118">Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-118">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="cdd4e-119">Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:</span><span class="sxs-lookup"><span data-stu-id="cdd4e-119">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore "Sintassi non valida".  <span data-ttu-id="cdd4e-121">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-121">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
7.  <span data-ttu-id="cdd4e-122">Eseguire l'applicazione Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cdd4e-122">Run the Visual Basic application.</span></span> <span data-ttu-id="cdd4e-123">Verrà visualizzata una finestra di messaggio con i risultati della chiamata a Subtract(145, 76.54).</span><span class="sxs-lookup"><span data-stu-id="cdd4e-123">A message box will be displayed with the results of calling Subtract(145, 76.54).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd4e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdd4e-124">See Also</span></span>  
 [<span data-ttu-id="cdd4e-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="cdd4e-125">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="cdd4e-126">L'integrazione con panoramica delle applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="cdd4e-126">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
