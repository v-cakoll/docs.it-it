---
title: Esempio di condivisione delle porte Net.TCP
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: 6c196380951d0da912cd937e3ebc38a03f80489c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584311"
---
# <a name="nettcp-port-sharing-sample"></a><span data-ttu-id="21f86-102">Esempio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="21f86-102">Net.TCP Port Sharing Sample</span></span>
<span data-ttu-id="21f86-103">Il protocollo TCP/IP utilizza un numero a 16 bit, definito porta, per differenziare le connessioni a più applicazioni di rete che sono in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="21f86-103">The TCP/IP protocol uses a 16-bit number, called a port, to differentiate connections to multiple network applications running on the same machine.</span></span> <span data-ttu-id="21f86-104">Se un'applicazione è in ascolto su una porta, tutto il traffico TCP per quella porta viene indirizzato a tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="21f86-104">If an application is listening on a port, then all TCP traffic for that port goes to that application.</span></span> <span data-ttu-id="21f86-105">Su quella porta non possono essere contemporaneamente in ascolto altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="21f86-105">Other applications cannot listen on that port at the same time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="21f86-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="21f86-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="21f86-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="21f86-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="21f86-108">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="21f86-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="21f86-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="21f86-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 <span data-ttu-id="21f86-110">Molti protocolli utilizzano un numero di porta standard o predefinito.</span><span class="sxs-lookup"><span data-stu-id="21f86-110">Many protocols have a standard or default port number that they use.</span></span> <span data-ttu-id="21f86-111">Ad esempio, il protocollo HTTP utilizza in genere la porta TCP 80.</span><span class="sxs-lookup"><span data-stu-id="21f86-111">For example, the HTTP protocol typically uses TCP port 80.</span></span> <span data-ttu-id="21f86-112">Internet Information Services (IIS) dispone di un listener per condividere una porta tra più applicazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="21f86-112">Internet Information Services (IIS) has a listener to share a port between multiple HTTP applications.</span></span> <span data-ttu-id="21f86-113">IIS è in ascolto direttamente sulla porta e inoltra i messaggi all'applicazione appropriata in base alle informazioni presenti all'interno del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="21f86-113">IIS listens on the port directly and forwards messages to the appropriate application based on information inside the message stream.</span></span> <span data-ttu-id="21f86-114">In questo modo più applicazioni HTTP possono utilizzare lo stesso numero di porta senza dover competere per riservare la porta per la ricezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="21f86-114">This allows multiple HTTP applications to use the same port number without having to compete to reserve the port for receiving messages.</span></span>  
  
 <span data-ttu-id="21f86-115">La condivisione delle porte NetTcp è una funzionalità di Windows Communication Foundation (WCF) che consente a più applicazioni di rete di condividere una singola porta.</span><span class="sxs-lookup"><span data-stu-id="21f86-115">NetTcp Port Sharing is a Windows Communication Foundation (WCF)feature that similarly allows multiple network applications to share a single port.</span></span> <span data-ttu-id="21f86-116">Il servizio di condivisione porte Net.Tcp accetta connessioni mediante il protocollo net.tcp e inoltra i messaggi in base al relativo indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="21f86-116">The NetTcp Port Sharing Service accepts connections using the net.tcp protocol and forwards messages based on their destination address.</span></span>  
  
 <span data-ttu-id="21f86-117">Questo servizio non è abilitato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="21f86-117">The NetTcp Port Sharing Service is not enabled by default.</span></span> <span data-ttu-id="21f86-118">ed è necessario abilitarlo manualmente prima di eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="21f86-118">Before running this sample, you must manually enable the service.</span></span> <span data-ttu-id="21f86-119">Per altre informazioni, vedere [procedura: abilitare il servizio di condivisione porte net. TCP](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="21f86-119">For more information, see [How to: Enable the Net.TCP Port Sharing Service](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span></span> <span data-ttu-id="21f86-120">Se il servizio è disabilitato, viene generata un'eccezione all'avvio dell'applicazione server.</span><span class="sxs-lookup"><span data-stu-id="21f86-120">If the service is disabled, an exception is thrown when the server application is started.</span></span>  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 <span data-ttu-id="21f86-121">La condivisione delle porte può essere abilitata sul server impostando la proprietà <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> dell'associazione <xref:System.ServiceModel.NetTcpBinding> o l'elemento di associazione <xref:System.ServiceModel.Channels.TcpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="21f86-121">Port sharing is enabled on the server by setting the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property of the <xref:System.ServiceModel.NetTcpBinding> binding or the <xref:System.ServiceModel.Channels.TcpTransportBindingElement> binding element.</span></span> <span data-ttu-id="21f86-122">Il client non deve necessariamente conoscere la modalità di configurazione della condivisione delle porte per poterla utilizzare sul server.</span><span class="sxs-lookup"><span data-stu-id="21f86-122">The client does not have to know how port sharing has been configured to use it on the server.</span></span>  
  
## <a name="enabling-port-sharing"></a><span data-ttu-id="21f86-123">Abilitazione della condivisione delle porte</span><span class="sxs-lookup"><span data-stu-id="21f86-123">Enabling Port Sharing</span></span>  
 <span data-ttu-id="21f86-124">Nel codice seguente viene illustrata l'abilitazione della condivisione delle porte sul server.</span><span class="sxs-lookup"><span data-stu-id="21f86-124">The following code demonstrates enabling port sharing on the server.</span></span> <span data-ttu-id="21f86-125">Viene avviata un'istanza del servizio `ICalculator` su una porta fissa con un percorso URI casuale.</span><span class="sxs-lookup"><span data-stu-id="21f86-125">It starts an instance of the `ICalculator` service on a fixed port with a random URI path.</span></span> <span data-ttu-id="21f86-126">Anche se due servizi possono condividere la stessa porta, gli indirizzi degli endpoint complessivi devono comunque essere univoci affinché il servizio di condivisione porte Net.Tcp possa indirizzare i messaggi all'applicazione corretta.</span><span class="sxs-lookup"><span data-stu-id="21f86-126">Even though two services can share the same port, their overall endpoint addresses still must be unique so that the NetTcp Port Sharing Service can route messages to the correct application.</span></span>  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address = $"net.tcp://localhost:9000/calculator/{salt}";
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 <span data-ttu-id="21f86-127">Quando la condivisione delle porte è abilitata, è possibile eseguire più volte il servizio senza generare un conflitto sul numero della porta.</span><span class="sxs-lookup"><span data-stu-id="21f86-127">With port sharing enabled, you can run the service multiple times without having a conflict over the port number.</span></span> <span data-ttu-id="21f86-128">Se si modifica il codice per disabilitare la condivisione delle porte, l'avvio di due copie del servizio comporta l'errore della seconda con un'eccezione <xref:System.ServiceModel.AddressAlreadyInUseException>.</span><span class="sxs-lookup"><span data-stu-id="21f86-128">If you change the code to disable port sharing, starting up two copies of the service results in the second failing with an <xref:System.ServiceModel.AddressAlreadyInUseException>.</span></span>  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="21f86-129">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="21f86-129">Running the Sample</span></span>  
 <span data-ttu-id="21f86-130">È possibile utilizzare il client di prova per verificare che i messaggi vengano indirizzati correttamente ai servizi che condividono la porta.</span><span class="sxs-lookup"><span data-stu-id="21f86-130">You can use the test client to check that messages are correctly routed to services sharing the port.</span></span>  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = $"net.tcp://localhost:9000/calculator/{salt}";
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 <span data-ttu-id="21f86-131">Ogni istanza del servizio mostra il relativo numero e indirizzo univoco.</span><span class="sxs-lookup"><span data-stu-id="21f86-131">Each instance of the service prints out its unique number and address.</span></span> <span data-ttu-id="21f86-132">Ad esempio, è possibile visualizzare il testo seguente quando si esegue service.exe.</span><span class="sxs-lookup"><span data-stu-id="21f86-132">For instance, you may see the following text when you run service.exe.</span></span>  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="21f86-133">Immettere il numero del servizio indicato in questo punto quando si esegue client.exe.</span><span class="sxs-lookup"><span data-stu-id="21f86-133">Enter the service number you see here when you run client.exe.</span></span>  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="21f86-134">Questo esempio può essere eseguito in una configurazione a più computer modificando l'indirizzo generato che il client utilizza.</span><span class="sxs-lookup"><span data-stu-id="21f86-134">This sample can be run in a cross-machine configuration by changing the generated address that the client uses.</span></span> <span data-ttu-id="21f86-135">Nel file Client.cs modificare la stringa di formato dell'indirizzo dell'endpoint affinché corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="21f86-135">In the Client.cs, change the endpoint address format string to match the new address of your service.</span></span> <span data-ttu-id="21f86-136">Sostituire qualsiasi riferimento a "localhost" con l'indirizzo IP del server.</span><span class="sxs-lookup"><span data-stu-id="21f86-136">Replace any references to "localhost" with the IP address of the server machine.</span></span> <span data-ttu-id="21f86-137">È necessario ricompilare l'esempio dopo avere apportato questa modifica.</span><span class="sxs-lookup"><span data-stu-id="21f86-137">You must recompile the sample after making this change.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="21f86-138">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="21f86-138">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="21f86-139">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="21f86-139">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="21f86-140">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="21f86-140">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="21f86-141">Abilitare il servizio di condivisione porte Net.Tcp come descritto nella sezione dell'introduzione.</span><span class="sxs-lookup"><span data-stu-id="21f86-141">Enable the NetTcp Port Sharing Service as previously described in the introduction section.</span></span>  
  
4. <span data-ttu-id="21f86-142">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="21f86-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="21f86-143">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="21f86-143">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="21f86-144">Dettagli specifici per l'esecuzione di questo esempio sono inclusi nella sezione Esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="21f86-144">Specific details for running this sample are included previously in the Running the Sample section.</span></span>  
