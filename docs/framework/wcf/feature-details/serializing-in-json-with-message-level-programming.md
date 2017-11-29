---
title: Serializzazione in Json con la programmazione a livello di messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 33337f75032031ccfc81173f188f4ff7695ffd40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="0db65-102">Serializzazione in Json con la programmazione a livello di messaggi</span><span class="sxs-lookup"><span data-stu-id="0db65-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="0db65-103">WCF supporta la serializzazione dei dati in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="0db65-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="0db65-104">In questo argomento viene descritto come impostare WCF in modo da serializzare i tipi utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0db65-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="0db65-105">Programmazione di messaggi tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db65-105">Typed Message Programming</span></span>  
 <span data-ttu-id="0db65-106">L'oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> viene utilizzato quando l'oggetto <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> viene applicato a un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0db65-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="0db65-107">Entrambi gli attributi consentono di specificare `RequestFormat` e `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="0db65-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="0db65-108">Per utilizzare JSON per le richieste e le risposte, impostarli entrambi su `WebMessageFormat.Json`.</span><span class="sxs-lookup"><span data-stu-id="0db65-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="0db65-109">Per utilizzare JSON, è necessario utilizzare l'oggetto <xref:System.ServiceModel.WebHttpBinding> che configura automaticamente <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0db65-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="0db65-110">Per ulteriori informazioni sulla serializzazione WCF, vedere: [la serializzazione e deserializzazione](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [serializzazione in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span><span class="sxs-lookup"><span data-stu-id="0db65-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="0db65-111">Per ulteriori informazioni su JSON e WCF vedere [An Introduction to servizi RESTfull con WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [abilitati per JSON con la creazione di servizi WCF in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), e [Panoramica di REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="0db65-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0db65-112">L'utilizzo di JSON richiede gli oggetti <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior> che non supportano la comunicazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="0db65-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="0db65-113">Servizi che comunicano con il <xref:System.ServiceModel.WebHttpBinding> non supportano l'esposizione dei metadati del servizio in modo non sarà in grado di utilizzare la funzionalità Aggiungi riferimento al servizio di Visual Studio o lo strumento da riga di comando svcutil per generare un proxy lato client.</span><span class="sxs-lookup"><span data-stu-id="0db65-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="0db65-114">Per ulteriori informazioni, come è possibile richiamare a livello di programmazione di servizi che utilizzano <xref:System.ServiceModel.WebHttpBinding>, vedere [come utilizzare i servizi REST con WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span><span class="sxs-lookup"><span data-stu-id="0db65-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="0db65-115">Programmazione di messaggi non tipizzati</span><span class="sxs-lookup"><span data-stu-id="0db65-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="0db65-116">Quando si utilizzano direttamente oggetti Message non tipizzati, è necessario impostare in modo esplicito le proprietà nel messaggio non tipizzato per serializzarlo come JSON.</span><span class="sxs-lookup"><span data-stu-id="0db65-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="0db65-117">Nel frammento di codice seguente viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0db65-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="0db65-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0db65-118">See Also</span></span>  
 [<span data-ttu-id="0db65-119">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="0db65-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="0db65-120">Serializzazione JSON autonoma</span><span class="sxs-lookup"><span data-stu-id="0db65-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="0db65-121">Serializzazione JSON</span><span class="sxs-lookup"><span data-stu-id="0db65-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
