---
title: ConcurrencyMode.Reentrant
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 613a1ed827173b3915892dda54dd20ebabdf6dcf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183899"
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="bdcce-102">ConcurrencyMode.Reentrant</span><span class="sxs-lookup"><span data-stu-id="bdcce-102">ConcurrencyMode Reentrant</span></span>
<span data-ttu-id="bdcce-103">In questo esempio vengono descritte la necessità e le implicazioni dell'utilizzo di ConcurrencyMode.Reentrant in un'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="bdcce-103">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="bdcce-104">ConcurrencyMode.Reentrant implica che il servizio (o callback) elabora solo uno messaggio a un'ora specificata (come per `ConcurencyMode.Single`).</span><span class="sxs-lookup"><span data-stu-id="bdcce-104">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="bdcce-105">Per garantire la thread safety, Windows Communication `InstanceContext` Foundation (WCF) blocca l'elaborazione di un messaggio in modo che nessun altro messaggio può essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="bdcce-105">To ensure thread safety, Windows Communication Foundation (WCF) locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="bdcce-106">Nel caso della modalità Reentrant, `InstanceContext` viene sbloccato poco prima che il servizio effettui una chiamata in uscita, consentendo alla chiamata successiva (che può essere rientrante, come illustrato nell'esempio) di eseguire il blocco la prossima volta che entra nel servizio.</span><span class="sxs-lookup"><span data-stu-id="bdcce-106">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="bdcce-107">Per descrivere il comportamento, nell'esempio viene illustrato come un client e un servizio possono inviarsi messaggi utilizzando un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="bdcce-107">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="bdcce-108">Il contratto definito è un contratto duplex con il metodo `Ping` implementato dal servizio e il metodo di callback `Pong` implementato dal client.</span><span class="sxs-lookup"><span data-stu-id="bdcce-108">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="bdcce-109">Un client richiama il metodo `Ping` del server con un conteggio di tick, avviando così la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bdcce-109">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="bdcce-110">Il servizio verifica se il conteggio di tick non è uguale a 0 e richiama quindi il metodo `Pong` del callback,  mentre esegue il decremento del conteggio di tick.</span><span class="sxs-lookup"><span data-stu-id="bdcce-110">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="bdcce-111">Questa operazione viene eseguita nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="bdcce-111">This is done by the following code in the sample.</span></span>  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 L'implementazione `Pong` del callback è dotata della stessa logica dell'implementazione `Ping`. Ovvero, controlla se il conteggio non è zero, quindi richiama il metodo `Ping` sul canale di callback (in questo caso il canale utilizzato per inviare il messaggio `Ping` originale) con il conteggio decrementato di 1. Nel momento in cui il conteggio raggiunge lo zero, il metodo viene completato, annullando così il wrapping di tutte le risposte fino alla prima chiamata effettuata dal client che ha avviato la chiamata. <span data-ttu-id="bdcce-115">Questa operazione viene illustrata nell'implementazione del callback.</span><span class="sxs-lookup"><span data-stu-id="bdcce-115">This is shown in the callback implementation.</span></span>  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 Entrambi i metodi `Ping` e `Pong` sono di tipo request/reply, il che significa che la prima chiamata a `Ping` non viene restituita finché non viene restituita la chiamata a `CallbackChannel<T>.Pong()`. Nel client, il metodo `Pong` non può essere completato finché non viene restituita la chiamata `Ping` successiva. <span data-ttu-id="bdcce-118">Poiché il callback e il servizio devono eseguire chiamate in uscita di tipo request/reply prima che possano rispondere alla richiesta in sospeso, entrambi le implementazioni devono essere contrassegnate dal comportamento ConcurrencyMode.Reentrant.</span><span class="sxs-lookup"><span data-stu-id="bdcce-118">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bdcce-119">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="bdcce-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bdcce-120">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bdcce-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bdcce-121">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bdcce-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bdcce-122">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bdcce-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bdcce-123">Dimostra</span><span class="sxs-lookup"><span data-stu-id="bdcce-123">Demonstrates</span></span>  
 <span data-ttu-id="bdcce-124">Per eseguire l'esempio, compilare i progetti del client e del server.</span><span class="sxs-lookup"><span data-stu-id="bdcce-124">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="bdcce-125">Aprire quindi due finestre di comando \<e modificare le directory relative \<all'esempio>> directory di esempio> .</span><span class="sxs-lookup"><span data-stu-id="bdcce-125">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="bdcce-126">Avviare quindi il `service.exe` servizio digitando e quindi richiamare Client.exe con il valore iniziale dei segni di graduazione passati come argomento di input.</span><span class="sxs-lookup"><span data-stu-id="bdcce-126">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="bdcce-127">Viene illustrato un esempio di output per tick.</span><span class="sxs-lookup"><span data-stu-id="bdcce-127">A sample output for 10 ticks is shown.</span></span>  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="bdcce-128">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bdcce-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bdcce-129">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bdcce-129">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bdcce-130">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bdcce-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bdcce-131">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcce-131">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
