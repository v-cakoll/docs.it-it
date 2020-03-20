---
title: Messaggi non incapsulati
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: 81592910d8530cea2df5ec1fd8a8b1145350ef78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143733"
---
# <a name="unwrapped-messages"></a><span data-ttu-id="8539a-102">Messaggi non incapsulati</span><span class="sxs-lookup"><span data-stu-id="8539a-102">Unwrapped Messages</span></span>
<span data-ttu-id="8539a-103">In questo esempio vengono illustrati i messaggi non incapsulati.</span><span class="sxs-lookup"><span data-stu-id="8539a-103">This sample demonstrates unwrapped messages.</span></span> <span data-ttu-id="8539a-104">Per impostazione predefinita, il corpo del messaggio è formattato in modo tale che i parametri di un'operazione del servizio sono incapsulati.</span><span class="sxs-lookup"><span data-stu-id="8539a-104">By default, the message body is formatted such that the parameters to a service operation are wrapped.</span></span> <span data-ttu-id="8539a-105">Nell'esempio seguente viene illustrato un messaggio di richiesta `Add` al servizio `ICalculator` in modalità incapsulata.</span><span class="sxs-lookup"><span data-stu-id="8539a-105">The following sample shows an `Add` request message to the `ICalculator` service in wrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="8539a-106">L'elemento `<Add>` nel corpo del messaggio incapsula i parametri `n1` e `n2`.</span><span class="sxs-lookup"><span data-stu-id="8539a-106">The `<Add>` element in the message body wraps the `n1` and `n2` parameters.</span></span> <span data-ttu-id="8539a-107">Diversamente, nell'esempio seguente viene illustrato il messaggio equivalente nella modalità non incapsulata.</span><span class="sxs-lookup"><span data-stu-id="8539a-107">In contrast, the following sample shows the equivalent message in the unwrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 <span data-ttu-id="8539a-108">Nel messaggio non incapsulato i parametri `n1` e `n2` non sono incapsulati in un elemento contenitore, bensì sono elementi figlio diretti dell'elemento del corpo SOAP.</span><span class="sxs-lookup"><span data-stu-id="8539a-108">The unwrapped message does not wrap the `n1` and `n2` parameters in a containing element, they are direct children of the soap body element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8539a-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8539a-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8539a-110">In questo esempio viene creato un messaggio non incapsulato applicando la classe <xref:System.ServiceModel.MessageContractAttribute> al tipo di parametro dell'operazione del servizio e al tipo di valore restituito, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8539a-110">In this sample, an unwrapped message is created by applying the <xref:System.ServiceModel.MessageContractAttribute> to the service operation parameter type and return value type as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 <span data-ttu-id="8539a-111">Per poter visualizzare i messaggi inviati e ricevuti, in questo esempio viene utilizzata la traccia.</span><span class="sxs-lookup"><span data-stu-id="8539a-111">To allow you to see the messages being sent and received, this sample uses tracing.</span></span> <span data-ttu-id="8539a-112">Inoltre, <xref:System.ServiceModel.WSHttpBinding> è stato configurato senza la sicurezza, per ridurre il numero di messaggi registrati.</span><span class="sxs-lookup"><span data-stu-id="8539a-112">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, to reduce the number of messages it logs.</span></span>  
  
 <span data-ttu-id="8539a-113">È possibile visualizzare il registro di traccia risultante (c:,logs,Message.log) utilizzando lo strumento Visualizzatore di tracce dei servizi [(SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8539a-113">The resulting trace log (c:\logs\Message.log) can be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="8539a-114">Per visualizzare il contenuto dei messaggi, selezionare **Messaggi** sia nel riquadro sinistro che in quello destro dello strumento Visualizzatore di traccia dei servizi.</span><span class="sxs-lookup"><span data-stu-id="8539a-114">To view message contents, select **Messages** in both the left and the right panes of the Service Trace Viewer tool.</span></span> <span data-ttu-id="8539a-115">I registri di traccia in questo esempio sono configurati in modo da essere generati nella cartella C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="8539a-115">Trace logs in this sample are configured to be generated into the C:\LOGS folder.</span></span> <span data-ttu-id="8539a-116">Creare questa cartella prima di eseguire l'esempio e assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.</span><span class="sxs-lookup"><span data-stu-id="8539a-116">Create this folder before running the sample and give the user Network Service write permissions for this directory.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8539a-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="8539a-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8539a-118">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8539a-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8539a-119">Creare una directory C:\LOGS per la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8539a-119">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="8539a-120">Assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.</span><span class="sxs-lookup"><span data-stu-id="8539a-120">Give the user Network Service write permissions for this directory.</span></span>  
  
3. <span data-ttu-id="8539a-121">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8539a-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="8539a-122">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8539a-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8539a-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8539a-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8539a-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8539a-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8539a-125">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8539a-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8539a-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8539a-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
