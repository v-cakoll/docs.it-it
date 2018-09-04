---
title: HTTP duale WS
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 16795a32aaec84ec1ae5a1c445f2bc519ef56a3b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502113"
---
# <a name="ws-dual-http"></a><span data-ttu-id="ffb81-102">HTTP duale WS</span><span class="sxs-lookup"><span data-stu-id="ffb81-102">WS Dual Http</span></span>
<span data-ttu-id="ffb81-103">Nell'esempio di HTTP duale viene illustrato come configurare l'associazione `WSDualHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ffb81-103">The Dual Http sample demonstrates how to configure the `WSDualHttpBinding` binding.</span></span> <span data-ttu-id="ffb81-104">Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ffb81-104">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="ffb81-105">Il servizio implementa un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="ffb81-105">The service implements a duplex contract.</span></span> <span data-ttu-id="ffb81-106">Il contratto è definito dall'interfaccia `ICalculatorDuplex`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione).</span><span class="sxs-lookup"><span data-stu-id="ffb81-106">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="ffb81-107">In questo esempio, l'interfaccia `ICalculatorDuplex` consente al client di eseguire operazioni matematiche, calcolando un risultato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="ffb81-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over the session.</span></span> <span data-ttu-id="ffb81-108">Il servizio restituisce risultati sull'interfaccia `ICalculatorDuplexCallback` indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="ffb81-108">Independently, the service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="ffb81-109">Poiché occorre definire un contesto per correlare il set di messaggi scambiati fra il client e il servizio, un contratto duplex richiede una sessione.</span><span class="sxs-lookup"><span data-stu-id="ffb81-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between client and service.</span></span> <span data-ttu-id="ffb81-110">L'associazione `WSDualHttpBinding` supporta la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="ffb81-110">The `WSDualHttpBinding` binding supports duplex communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffb81-111">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ffb81-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffb81-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ffb81-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ffb81-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ffb81-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ffb81-114">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="ffb81-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffb81-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ffb81-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`  
  
 <span data-ttu-id="ffb81-116">Per configurare un endpoint del servizio con `WSDualHttpBinding`, specificare l'associazione nella configurazione dell'endpoint come illustrato.</span><span class="sxs-lookup"><span data-stu-id="ffb81-116">To configure a service endpoint with the `WSDualHttpBinding`, specify the binding in the endpoint configuration as shown.</span></span>  
  
```xml  
<endpoint address=""  
         binding="wsDualHttpBinding"  
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
```  
  
 <span data-ttu-id="ffb81-117">Nel client, è necessario configurare un indirizzo usabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ffb81-117">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
         "http://localhost/servicemodelsamples/service.svc"   
         binding="wsDualHttpBinding"   
         bindingConfiguration="Binding1"   
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
  </client>  
  
  <bindings>  
    <!-- Configure a WSDualHttpBinding that supports duplex -->  
    <!-- communication. -->  
    <wsDualHttpBinding>  
      <binding name="Binding1"  
               clientBaseAddress="http://localhost:8000/myClient/"  
               useDefaultWebProxy="true"  
               bypassProxyOnLocal="false">  
      </binding>  
    </wsDualHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="ffb81-118">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="ffb81-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ffb81-119">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="ffb81-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Press <ENTER> to terminate client once the output is displayed.  
  
Result(100)  
Result(50)  
Result(882.5)  
Result(441.25)  
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)  
```  
  
 <span data-ttu-id="ffb81-120">Quando si esegue l'esempio, vengono visualizzati i messaggi restituiti al client sull'interfaccia di callback inviata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ffb81-120">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="ffb81-121">Una volta completate tutte le operazioni, vengono visualizzati tutti i risultati intermedi, seguiti dall'intera equazione.</span><span class="sxs-lookup"><span data-stu-id="ffb81-121">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="ffb81-122">Premere INVIO per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="ffb81-122">Press ENTER to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ffb81-123">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ffb81-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ffb81-124">Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="ffb81-124">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="ffb81-125">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffb81-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="ffb81-126">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffb81-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="ffb81-127">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffb81-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ffb81-128">Quando si esegue il client in una configurazione tra più computer, assicurarsi di sostituire localhost sia la `address` attributo del [endpoint](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento e il `clientBaseAddress` attributo del [ \< associazione >](../../../../docs/framework/misc/binding.md) dell'elemento di [ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento con il nome del computer appropriato, come illustrato:</span><span class="sxs-lookup"><span data-stu-id="ffb81-128">When running the client in a cross-machine configuration, be sure to replace localhost in both the `address` attribute of the [endpoint](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element and the `clientBaseAddress` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown:</span></span>  
  
    ```xml  
    <client>  
        <endpoint name = ""  
          address=  
         "http://service_machine_name/servicemodelsamples/service.svc"  
        />  
    </client>  
    ...  
    <wsDualHttpBinding>  
        <binding name="DuplexBinding" clientBaseAddress=  
            "http://client_machine_name:8000/myClient/">  
        </binding>  
    </wsDualHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ffb81-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffb81-129">See Also</span></span>
