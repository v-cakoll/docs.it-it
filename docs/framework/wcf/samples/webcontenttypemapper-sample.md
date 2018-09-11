---
title: Esempio di WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 91e5cca478521a343f7528f878f114b85eff2d08
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262509"
---
# <a name="webcontenttypemapper-sample"></a><span data-ttu-id="2e0eb-102">Esempio di WebContentTypeMapper</span><span class="sxs-lookup"><span data-stu-id="2e0eb-102">WebContentTypeMapper Sample</span></span>
<span data-ttu-id="2e0eb-103">In questo esempio viene illustrato come eseguire il mapping di nuovi tipi di contenuto a formati del corpo del messaggio di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2e0eb-103">This sample demonstrates how to map new content types to Windows Communication Foundation (WCF) message body formats.</span></span>  
  
 <span data-ttu-id="2e0eb-104">Il <xref:System.ServiceModel.Description.WebHttpEndpoint> elemento inserisce il codificatore di messaggi Web, che consente a WCF ricevere i messaggi binari non elaborati sullo stesso endpoint, XML o JSON.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-104">The <xref:System.ServiceModel.Description.WebHttpEndpoint> element plugs in the Web message encoder, which allows WCF to receive JSON, XML, or raw binary messages at the same endpoint.</span></span> <span data-ttu-id="2e0eb-105">Il codificatore determina il formato del corpo del messaggio analizzando il tipo di contenuto HTTP della richiesta.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-105">The encoder determines the body format of the message by looking at the HTTP content-type of the request.</span></span> <span data-ttu-id="2e0eb-106">In questo esempio viene presentata la classe <xref:System.ServiceModel.Channels.WebContentTypeMapper>, che consente all'utente di controllare il mapping tra il tipo di contenuto e il formato del corpo.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-106">This sample introduces the <xref:System.ServiceModel.Channels.WebContentTypeMapper> class, which allows the user to control the mapping between content type and body format.</span></span>  
  
 <span data-ttu-id="2e0eb-107">WCF fornisce un set di mapping predefiniti per i tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-107">WCF provides a set of default mappings for content types.</span></span> <span data-ttu-id="2e0eb-108">Ad esempio, `application/json` esegue il mapping a JSON e `text/xml` esegue il mapping a XML.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-108">For example, `application/json` maps to JSON and `text/xml` maps to XML.</span></span> <span data-ttu-id="2e0eb-109">Qualsiasi tipo di contenuto per cui non viene eseguito il mapping a JSON o a XML, viene associato al formato binario non elaborato.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-109">Any content type that is not mapped to JSON or XML is mapped to raw binary format.</span></span>  
  
 <span data-ttu-id="2e0eb-110">In alcuni scenari (ad esempio, API di tipo push), lo sviluppatore del servizio non controlla il tipo di contenuto restituito dal client.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-110">In some scenarios (for example, push-style APIs), the service developer does not control the content type returned by the client.</span></span> <span data-ttu-id="2e0eb-111">Ad esempio, i client potrebbero restituire JSON come `text/javascript` anziché `application/json`.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-111">For example, clients might return JSON as `text/javascript` instead of `application/json`.</span></span> <span data-ttu-id="2e0eb-112">In questo caso, lo sviluppatore del servizio deve fornire un tipo che deriva da <xref:System.ServiceModel.Channels.WebContentTypeMapper> per gestire correttamente il tipo di contenuto specificato, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-112">In this case, the service developer must provide a type that derives from <xref:System.ServiceModel.Channels.WebContentTypeMapper> to handle the given content type correctly, as shown in the following sample code.</span></span>  
  
```  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="2e0eb-113">È necessario che il tipo esegua l'override del metodo <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-113">The type must override the <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> method.</span></span> <span data-ttu-id="2e0eb-114">Il metodo deve valutare l'argomento `contentType` e restituire uno dei seguenti valori: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-114">The method must evaluate the `contentType` argument and return one of the following values: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span></span> <span data-ttu-id="2e0eb-115">La restituzione di <xref:System.ServiceModel.Channels.WebContentFormat.Default> rinvia ai mapping del codificatore di messaggi Web predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-115">Returning <xref:System.ServiceModel.Channels.WebContentFormat.Default> defers to the default Web message encoder mappings.</span></span> <span data-ttu-id="2e0eb-116">Nell'esempio di codice precedente il tipo di contenuto `text/javascript` viene associato a JSON e tutti gli altri mapping rimangono immutati.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-116">In the previous sample code, the `text/javascript` content type is mapped to JSON, and all other mappings remain unchanged.</span></span>  
  
 <span data-ttu-id="2e0eb-117">Per utilizzare la classe `JsonContentTypeMapper`, modificare il file Web.config nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2e0eb-117">To use the `JsonContentTypeMapper` class, use the following in your Web.config:</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="2e0eb-118">Per verificare il requisito per l'utilizzo di JsonContentTypeMapper, rimuovere l'attributo contentTypeMapper dal file di configurazione illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-118">To verify the requirement for using the JsonContentTypeMapper, remove the contentTypeMapper attribute from the above configuration file.</span></span> <span data-ttu-id="2e0eb-119">Si verifica un errore durante il caricamento della pagina client quando si tenta di utilizzare  `text/javascript` per inviare contenuto JSON.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-119">The client page fails to load when attempting to use `text/javascript` to send JSON content.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2e0eb-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2e0eb-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2e0eb-121">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2e0eb-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2e0eb-122">Compilare la soluzione Webcontenttypemappersample come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2e0eb-122">Build the solution WebContentTypeMapperSample.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2e0eb-123">Passare a http://localhost/ServiceModelSamples/JCTMClientPage.htm (non aprire Jctmclientpage nel browser dalla directory del progetto).</span><span class="sxs-lookup"><span data-stu-id="2e0eb-123">Navigate to http://localhost/ServiceModelSamples/JCTMClientPage.htm (do not open JCTMClientPage.htm in the browser from within the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e0eb-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2e0eb-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2e0eb-126">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2e0eb-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2e0eb-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
  
## <a name="see-also"></a><span data-ttu-id="2e0eb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e0eb-128">See Also</span></span>
