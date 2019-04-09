---
title: Gestione degli errori HTTP Web WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 834c642e36e1551081dbe1f14529ed7596df1360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152698"
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="8afea-102">Gestione degli errori HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="8afea-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="8afea-103">Gestione degli errori HTTP Web di Windows Communication Foundation (WCF) consente di restituire errori da servizi HTTP Web WCF che specificano un codice di stato HTTP e restituiscono i dettagli dell'errore utilizzando lo stesso formato dell'operazione (ad esempio, XML o JSON).</span><span class="sxs-lookup"><span data-stu-id="8afea-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="8afea-104">Gestione degli errori HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="8afea-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="8afea-105">La classe <xref:System.ServiceModel.Web.WebFaultException> definisce un costruttore che consente di specificare un codice di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="8afea-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="8afea-106">Questo codice di stato viene quindi restituito al client.</span><span class="sxs-lookup"><span data-stu-id="8afea-106">This status code is then returned to the client.</span></span> <span data-ttu-id="8afea-107">Versione generica della classe <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> consente di restituire un tipo definito dall'utente che contiene informazioni sull'errore verificatosi.</span><span class="sxs-lookup"><span data-stu-id="8afea-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="8afea-108">Questo oggetto personalizzato viene serializzato utilizzando il formato specificato dall'operazione e restituito al client.</span><span class="sxs-lookup"><span data-stu-id="8afea-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="8afea-109">Nell'esempio riportato di seguito viene illustrato il modo in cui restituire un codice di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="8afea-109">The following example shows how to return an HTTP status code.</span></span>  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="8afea-110">Nell'esempio seguente viene illustrato come restituire un codice di stato HTTP e informazioni aggiuntive in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8afea-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> `MyErrorDetail` <span data-ttu-id="8afea-111">è un tipo definito dall'utente che contiene informazioni aggiuntive sull'errore verificatosi.</span><span class="sxs-lookup"><span data-stu-id="8afea-111">is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="8afea-112">Il codice precedente restituisce una risposta HTTP con il codice di stato proibito e un corpo che contiene un'istanza dell'oggetto `MyErrorDetails`.</span><span class="sxs-lookup"><span data-stu-id="8afea-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="8afea-113">Il formato dell'oggetto `MyErrorDetails` viene determinato dagli elementi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8afea-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
-   <span data-ttu-id="8afea-114">Valore del parametro `ResponseFormat` dell'attributo <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> specificato nell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="8afea-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
-   <span data-ttu-id="8afea-115">Valore di <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="8afea-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
-   <span data-ttu-id="8afea-116">Valore della proprietà <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> accedendo a <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="8afea-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="8afea-117">Per altre informazioni sugli effetti la formattazione dell'operazione di questi valori, vedere [formattazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8afea-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <xref:System.ServiceModel.Web.WebFaultException> <span data-ttu-id="8afea-118">è un <xref:System.ServiceModel.FaultException> e pertanto può essere utilizzato come il modello di programmazione di eccezione di errore per i servizi che espongono endpoint SOAP, nonché gli endpoint HTTP web.</span><span class="sxs-lookup"><span data-stu-id="8afea-118">is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8afea-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8afea-119">See also</span></span>

- [<span data-ttu-id="8afea-120">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="8afea-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="8afea-121">Formattazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="8afea-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [<span data-ttu-id="8afea-122">Definizione e specifica degli errori</span><span class="sxs-lookup"><span data-stu-id="8afea-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [<span data-ttu-id="8afea-123">Gestione di eccezioni ed errori</span><span class="sxs-lookup"><span data-stu-id="8afea-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="8afea-124">Invio e ricezione degli errori</span><span class="sxs-lookup"><span data-stu-id="8afea-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
