---
title: Esempio di servizio AJAX che usa tipi complessi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c83da8aba2e1a88665f4443d98dbebbd5b1962b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="3f3aa-102">Esempio di servizio AJAX che usa tipi complessi</span><span class="sxs-lookup"><span data-stu-id="3f3aa-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="3f3aa-103">Questo esempio illustra come utilizzare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per creare un servizio AJAX (ASP.NET Asynchronous JavaScript e XML) che crea istanze di tipi complessi e li invia tra servizio e client come JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="3f3aa-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="3f3aa-104">È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="3f3aa-105">In questo esempio si basa il [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="3f3aa-106">Il supporto AJAX in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo <xref:System.Web.UI.ScriptManager>.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-106">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="3f3aa-107">Per un esempio di utilizzo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vedere il [esempi AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="3f3aa-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f3aa-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3f3aa-109">Il servizio dell'esempio seguente è un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senza codice specifico per AJAX.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span> <span data-ttu-id="3f3aa-110">Perché l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non è applicato, viene utilizzato il verbo HTTP predefinito ("POST").</span><span class="sxs-lookup"><span data-stu-id="3f3aa-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="3f3aa-111">Il servizio ha un'operazione, `DoMath` che restituisce un tipo complesso denominato `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="3f3aa-112">Il tipo complesso è un tipo di contratto dati standard che non contiene codice AJAX specifico.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  
  
```  
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
  
 <span data-ttu-id="3f3aa-113">Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="3f3aa-114">La pagina Web ComplexTypeClientPage.aspx del client contiene il codice ASP.NET e JavaScript per richiamare il servizio quando l'utente fa clic il **eseguire calcolo** pulsante nella pagina.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="3f3aa-115">Il codice per richiamare il servizio costruisce un corpo JSON e lo invia utilizzando HTTP POST, simile al [servizio AJAX con HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="3f3aa-116">Dopo che la chiamata del servizio riesce, è possibile accedere ai membri dati singoli (`sum`, `difference`, `product` e `quotient`) sull'oggetto JavaScript risultante.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3f3aa-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3f3aa-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3f3aa-118">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3f3aa-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3f3aa-119">Compilare la soluzione ComplexTypeAjaxService.sln, come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3f3aa-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3f3aa-120">Spostarsi alla pagina http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (non aprire ComplexTypeClientPage.aspx nel browser all'interno della directory del progetto).</span><span class="sxs-lookup"><span data-stu-id="3f3aa-120">Navigate to http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f3aa-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3f3aa-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3f3aa-123">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f3aa-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3f3aa-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3f3aa-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="3f3aa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f3aa-125">See Also</span></span>  
 [<span data-ttu-id="3f3aa-126">Servizio AJAX di base</span><span class="sxs-lookup"><span data-stu-id="3f3aa-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
