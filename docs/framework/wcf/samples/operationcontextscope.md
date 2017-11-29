---
title: OperationContextScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f636fe5bc79c18634f2239bc403c5189531737b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="operationcontextscope"></a><span data-ttu-id="ffce5-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="ffce5-102">OperationContextScope</span></span>
<span data-ttu-id="ffce5-103">Nell'esempio OperationContextScope viene illustrato come inviare informazioni aggiuntive su una chiamata [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizzando le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="ffce5-103">The OperationContextScope sample demonstrates how to send extra information on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] call using headers.</span></span> <span data-ttu-id="ffce5-104">In questo esempio sia il server che il client sono applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="ffce5-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffce5-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ffce5-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ffce5-106">Nell'esempio viene illustrato in che modo un client può inviare informazioni aggiuntive come un <xref:System.ServiceModel.Channels.MessageHeader> utilizzando <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="ffce5-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="ffce5-107">Un oggetto <xref:System.ServiceModel.OperationContextScope> viene creato definendone l'ambito su un canale.</span><span class="sxs-lookup"><span data-stu-id="ffce5-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="ffce5-108">Le intestazioni che devono essere tradotte nel servizio remoto possono essere aggiunte alla raccolta <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffce5-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="ffce5-109">Le intestazioni aggiunte alla raccolta possono essere recuperate nel servizio accedendo alla proprietà <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffce5-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="ffce5-110">Le chiamate a questa proprietà vengono effettuate sui più canali e quindi le intestazioni aggiunte al client possono essere applicate solo al canale utilizzato per creare <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="ffce5-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="ffce5-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="ffce5-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="ffce5-112">Si tratta del servizio di esempio che riceve un messaggio dal client e tenta di cercare l'intestazione nella raccolta <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffce5-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="ffce5-113">Il client passa il GUID inviato nell'intestazione, quindi il servizio recupera l'intestazione personalizzata e, se presente, lo confronta con il GUID passato come argomento dal client.</span><span class="sxs-lookup"><span data-stu-id="ffce5-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```  
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="ffce5-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="ffce5-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="ffce5-115">Si tratta dell'implementazione client che usa il proxy generato da [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per comunicare con il servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="ffce5-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="ffce5-116">Crea innanzitutto due oggetti proxy di `MessageHeaderReaderClient`.</span><span class="sxs-lookup"><span data-stu-id="ffce5-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```  
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="ffce5-117">Il client crea quindi un OperationContextScope e ne definisce l'ambito su `client1`.</span><span class="sxs-lookup"><span data-stu-id="ffce5-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="ffce5-118">Aggiunge un <xref:System.ServiceModel.Channels.MessageHeader> a <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> ed esegue una chiamata su entrambi i client.</span><span class="sxs-lookup"><span data-stu-id="ffce5-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="ffce5-119">Assicura che l'intestazione venga inviata solo su `client1` e non in `client2` controllando il valore restituito dal `RetrieveHeader` chiamare.</span><span class="sxs-lookup"><span data-stu-id="ffce5-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```  
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetreieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="ffce5-120">Questo esempio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="ffce5-120">This sample is self-hosted.</span></span> <span data-ttu-id="ffce5-121">L'esecuzione dell'esempio fornisce l'output di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ffce5-121">The following sample output from running the sample is provided:</span></span>  
  
```  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ffce5-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ffce5-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ffce5-123">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffce5-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ffce5-124">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffce5-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ffce5-125">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffce5-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffce5-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ffce5-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ffce5-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ffce5-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ffce5-128">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffce5-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffce5-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ffce5-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## <a name="see-also"></a><span data-ttu-id="ffce5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffce5-130">See Also</span></span>
