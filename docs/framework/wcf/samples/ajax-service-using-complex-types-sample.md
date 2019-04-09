---
title: Esempio di servizio AJAX che usa tipi complessi
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 54d8c90f8317b69195401eda64e8a482aaf8460a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128505"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="ee2e1-102">Esempio di servizio AJAX che usa tipi complessi</span><span class="sxs-lookup"><span data-stu-id="ee2e1-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="ee2e1-103">Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio ASP.NET Asynchronous JavaScript and XML (AJAX) che crea istanze di tipi complessi e li invia tra servizio e client come JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="ee2e1-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="ee2e1-104">È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="ee2e1-105">In questo esempio si basa sul [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="ee2e1-106">Supporto AJAX in WCF è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il <xref:System.Web.UI.ScriptManager> controllo.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="ee2e1-107">Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="ee2e1-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee2e1-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ee2e1-109">Il servizio nell'esempio seguente è un servizio WCF senza codice AJAX specifico.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="ee2e1-110">Perché l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non è applicato, viene utilizzato il verbo HTTP predefinito ("POST").</span><span class="sxs-lookup"><span data-stu-id="ee2e1-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="ee2e1-111">Il servizio ha un'operazione, `DoMath` che restituisce un tipo complesso denominato `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="ee2e1-112">Il tipo complesso è un tipo di contratto dati standard che non contiene codice AJAX specifico.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 <span data-ttu-id="ee2e1-113">Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="ee2e1-114">La pagina Web complextypeclientpage. aspx del client contiene il codice ASP.NET e JavaScript per richiamare il servizio quando l'utente fa clic il **eseguire il calcolo** pulsante nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="ee2e1-115">Il codice per richiamare il servizio costruisce un corpo JSON e lo invia utilizzando HTTP POST, simile al [servizio AJAX con HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="ee2e1-116">Dopo che la chiamata del servizio riesce, è possibile accedere ai membri dati singoli (`sum`, `difference`, `product` e `quotient`) sull'oggetto JavaScript risultante.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ee2e1-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ee2e1-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ee2e1-118">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee2e1-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ee2e1-119">Compilare la soluzione Complextypeajaxservice come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee2e1-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ee2e1-120">Passare a `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (non aprire complextypeclientpage. aspx nel browser dalla directory del progetto).</span><span class="sxs-lookup"><span data-stu-id="ee2e1-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee2e1-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ee2e1-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ee2e1-123">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee2e1-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ee2e1-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="ee2e1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee2e1-125">See also</span></span>

- [<span data-ttu-id="ee2e1-126">Servizio AJAX di base</span><span class="sxs-lookup"><span data-stu-id="ee2e1-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
