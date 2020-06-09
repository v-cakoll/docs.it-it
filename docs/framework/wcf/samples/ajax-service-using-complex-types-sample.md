---
title: Esempio di servizio AJAX che usa tipi complessi
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4227446e8844accd06490d8e7cf933da43d875a6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575914"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="b9200-102">Esempio di servizio AJAX che usa tipi complessi</span><span class="sxs-lookup"><span data-stu-id="b9200-102">AJAX Service Using Complex Types Sample</span></span>

<span data-ttu-id="b9200-103">In questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio AJAX (ASP.NET Asynchronous JavaScript and XML) che crea istanze di tipi complessi e li invia tra servizio e client come JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="b9200-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="b9200-104">È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web.</span><span class="sxs-lookup"><span data-stu-id="b9200-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="b9200-105">Questo esempio si basa sull'esempio di [servizio AJAX di base](basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="b9200-105">This sample builds on the [Basic AJAX Service](basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="b9200-106">Il supporto AJAX in WCF è ottimizzato per l'uso con ASP.NET AJAX tramite il <xref:System.Web.UI.ScriptManager> controllo.</span><span class="sxs-lookup"><span data-stu-id="b9200-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="b9200-107">Per un esempio di utilizzo di WCF con ASP.NET AJAX, vedere gli [esempi di AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="b9200-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b9200-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b9200-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="b9200-109">Il servizio nell'esempio seguente è un servizio WCF senza codice specifico per AJAX.</span><span class="sxs-lookup"><span data-stu-id="b9200-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="b9200-110">Perché l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non è applicato, viene utilizzato il verbo HTTP predefinito ("POST").</span><span class="sxs-lookup"><span data-stu-id="b9200-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="b9200-111">Il servizio ha un'operazione, `DoMath` che restituisce un tipo complesso denominato `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="b9200-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="b9200-112">Il tipo complesso è un tipo di contratto dati standard che non contiene codice AJAX specifico.</span><span class="sxs-lookup"><span data-stu-id="b9200-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>

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

<span data-ttu-id="b9200-113">Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.</span><span class="sxs-lookup"><span data-stu-id="b9200-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="b9200-114">La pagina Web ComplexTypeClientPage. aspx del client contiene il codice ASP.NET e JavaScript per richiamare il servizio quando l'utente fa clic sul pulsante **Esegui calcolo** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b9200-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="b9200-115">Il codice per richiamare il servizio costruisce un corpo JSON e lo invia usando HTTP POST, simile al [servizio AJAX che usa l'esempio http post](ajax-service-using-http-post.md) .</span><span class="sxs-lookup"><span data-stu-id="b9200-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](ajax-service-using-http-post.md) sample.</span></span>

<span data-ttu-id="b9200-116">Dopo che la chiamata del servizio riesce, è possibile accedere ai membri dati singoli (`sum`, `difference`, `product` e `quotient`) sull'oggetto JavaScript risultante.</span><span class="sxs-lookup"><span data-stu-id="b9200-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("sum").value = mathResult.sum;
     document.getElementById("difference").value = mathResult.difference;
     document.getElementById("product").value = mathResult.product;
     document.getElementById("quotient").value = mathResult.quotient;
}
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b9200-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b9200-117">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="b9200-118">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b9200-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="b9200-119">Compilare la soluzione ComplexTypeAjaxService. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b9200-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="b9200-120">Passare a `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (non aprire ComplexTypeClientPage. aspx nel browser dalla directory del progetto).</span><span class="sxs-lookup"><span data-stu-id="b9200-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9200-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b9200-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b9200-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b9200-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b9200-123">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b9200-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9200-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b9200-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a><span data-ttu-id="b9200-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9200-125">See also</span></span>

- [<span data-ttu-id="b9200-126">Servizio AJAX di base</span><span class="sxs-lookup"><span data-stu-id="b9200-126">Basic AJAX Service</span></span>](basic-ajax-service.md)
