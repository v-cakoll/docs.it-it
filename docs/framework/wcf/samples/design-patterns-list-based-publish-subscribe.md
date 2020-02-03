---
title: 'Modelli di progettazione: pubblicazione-sottoscrizione basata su elenchi'
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: 3a62b09a29ec0b7e241bf2fdc09df6eaba5420c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728836"
---
# <a name="design-patterns-list-based-publish-subscribe"></a><span data-ttu-id="4eec0-102">Modelli di progettazione: pubblicazione-sottoscrizione basata su elenchi</span><span class="sxs-lookup"><span data-stu-id="4eec0-102">Design Patterns: List-Based Publish-Subscribe</span></span>
<span data-ttu-id="4eec0-103">Questo esempio illustra il modello di pubblicazione-sottoscrizione basato su elenchi implementato come programma Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4eec0-103">This sample illustrates the List-based Publish-Subscribe pattern implemented as a Windows Communication Foundation (WCF) program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4eec0-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4eec0-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4eec0-105">Il modello di progettazione di pubblicazione-sottoscrizione basato su elenchi viene descritto nella pubblicazione di Microsoft Patterns & Practices, [modelli di integrazione](https://docs.microsoft.com/previous-versions/msp-n-p/ff647309(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="4eec0-105">The List-based Publish-Subscribe design pattern is described in the Microsoft Patterns & Practices publication, [Integration Patterns](https://docs.microsoft.com/previous-versions/msp-n-p/ff647309(v=pandp.10)).</span></span> <span data-ttu-id="4eec0-106">Il modello di pubblicazione-sottoscrizione passa le informazioni a una raccolta di destinatari che hanno sottoscritto un argomento di informazioni.</span><span class="sxs-lookup"><span data-stu-id="4eec0-106">The Publish-Subscribe pattern passes information to a collection of recipients who have subscribed to an information topic.</span></span> <span data-ttu-id="4eec0-107">La pubblicazione-sottoscrizione basata su elenchi gestisce un elenco di sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="4eec0-107">List-based publish-subscribe maintains a list of subscribers.</span></span> <span data-ttu-id="4eec0-108">Quando esistono informazioni da condividere, una copia viene inviata a ogni sottoscrittore presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4eec0-108">When there is information to share, a copy is sent to each subscriber on the list.</span></span> <span data-ttu-id="4eec0-109">In questo esempio viene illustrato un modello di pubblicazione-sottoscrizione basato su elenchi dinamici, in cui i client possono effettuare la sottoscrizione o annullare la sottoscrizione ogni volta che lo desiderano.</span><span class="sxs-lookup"><span data-stu-id="4eec0-109">This sample demonstrates a dynamic list-based publish-subscribe pattern, where clients can subscribe or unsubscribe as often as required.</span></span>  
  
 <span data-ttu-id="4eec0-110">L'esempio di pubblicazione-sottoscrizione basata su elenchi consiste in un client, un servizio e un programma dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4eec0-110">The List-based Publish-Subscribe sample consists of a client, a service, and a data source program.</span></span> <span data-ttu-id="4eec0-111">È consentita l'esecuzione di più client e più programmi delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="4eec0-111">There can be more than one client and more than one data source program running.</span></span> <span data-ttu-id="4eec0-112">I client sottoscrivono il servizio, ricevono le notifiche e annullano la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="4eec0-112">Clients subscribe to the service, receive notifications, and unsubscribe.</span></span> <span data-ttu-id="4eec0-113">I programmi delle origini dati inviano informazioni al servizio da condividere con tutti i sottoscrittori correnti.</span><span class="sxs-lookup"><span data-stu-id="4eec0-113">Data source programs send information to the service to be shared with all current subscribers.</span></span>  
  
 <span data-ttu-id="4eec0-114">In questo esempio il client e l'origine dati sono programmi della console (file con estensione exe) e il servizio è una libreria (con estensione dll) ospitata in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4eec0-114">In this sample, the client and data source are console programs (.exe files) and the service is a library (.dll) hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="4eec0-115">Le attività del client e dell'origine dati sono visibili sul desktop.</span><span class="sxs-lookup"><span data-stu-id="4eec0-115">Client and data source activity are visible on the desktop.</span></span>  
  
 <span data-ttu-id="4eec0-116">Il servizio usa la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="4eec0-116">The service uses duplex communication.</span></span> <span data-ttu-id="4eec0-117">Il contratto di servizio `ISampleContract` è accoppiato a un contratto di callback `ISampleClientCallback`.</span><span class="sxs-lookup"><span data-stu-id="4eec0-117">The `ISampleContract` service contract is paired up with an `ISampleClientCallback` callback contract.</span></span> <span data-ttu-id="4eec0-118">Il servizio implementa operazioni del servizio di sottoscrizione e annullamento della sottoscrizione che consentono ai client di essere aggiunti o rimossi dall'elenco dei sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="4eec0-118">The service implements Subscribe and Unsubscribe service operations, which clients use to join or leave the list of subscribers.</span></span> <span data-ttu-id="4eec0-119">Il servizio implementa inoltre l'operazione del servizio `PublishPriceChange` chiamata dal programma dell'origine dati per fornire nuove informazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-119">The service also implements the `PublishPriceChange` service operation, which the data source program calls to provide the service with new information.</span></span> <span data-ttu-id="4eec0-120">Il programma client implementa l'operazione del servizio `PriceChange` chiamata dal servizio per notificare a tutti i sottoscrittori la modifica di un prezzo.</span><span class="sxs-lookup"><span data-stu-id="4eec0-120">The client program implements the `PriceChange` service operation, which the service calls to notify all subscribers of a price change.</span></span>  
  
```csharp  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,   
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 <span data-ttu-id="4eec0-121">Il servizio usa un evento .NET Framework come meccanismo per informare tutti i sottoscrittori dell'esistenza di nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="4eec0-121">The service uses a .NET Framework event as the mechanism to inform all subscribers about new information.</span></span> <span data-ttu-id="4eec0-122">L'aggiunta di un client al servizio tramite una chiamata a Subscribe determina la disponibilità di un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-122">When a client joins the service by calling Subscribe, it provides an event handler.</span></span> <span data-ttu-id="4eec0-123">La rimozione di un client dal servizio determina l'annullamento della sottoscrizione del relativo gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-123">When a client leaves, it unsubscribes its event handler from the event.</span></span> <span data-ttu-id="4eec0-124">Quando un'origine dati chiama il servizio per segnalare la modifica di un prezzo, il servizio genera l'evento,</span><span class="sxs-lookup"><span data-stu-id="4eec0-124">When a data source calls the service to report a price change, the service raises the event.</span></span> <span data-ttu-id="4eec0-125">che a sua volta chiama ogni istanza del servizio, una per ogni client che ha effettuato la sottoscrizione, e causa l'esecuzione dei relativi gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-125">This calls each instance of the service, one for each client that has subscribed, and causes their event handlers to execute.</span></span> <span data-ttu-id="4eec0-126">Ogni gestore eventi passa le informazioni al client corrispondente tramite la relativa funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="4eec0-126">Each event handler passes the information to its client through its callback function.</span></span>  
  
```csharp
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 <span data-ttu-id="4eec0-127">Eseguire l'esempio avviando più client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-127">When you run the sample, launch several clients.</span></span> <span data-ttu-id="4eec0-128">I client sottoscrivono il servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-128">The clients subscribe to the service.</span></span> <span data-ttu-id="4eec0-129">Eseguire quindi il programma dell'origine dati che invia informazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-129">Then run the data source program, which sends information to the service.</span></span> <span data-ttu-id="4eec0-130">Il servizio passa le informazioni a tutti i sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="4eec0-130">The service passes on the information to all subscribers.</span></span> <span data-ttu-id="4eec0-131">In ogni console client sono visibili le attività, a conferma dell'avvenuta ricezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="4eec0-131">You can see activity on each client console confirming that the information has been received.</span></span> <span data-ttu-id="4eec0-132">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-132">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="4eec0-133">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4eec0-133">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="4eec0-134">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4eec0-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4eec0-135">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4eec0-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="4eec0-136">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="4eec0-136">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="4eec0-137">Verificare che sia possibile accedere al servizio utilizzando un browser immettendo l'indirizzo seguente: `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="4eec0-137">Test that you can access the service using a browser by entering the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="4eec0-138">In risposta, viene visualizzata un pagina di conferma.</span><span class="sxs-lookup"><span data-stu-id="4eec0-138">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="4eec0-139">Eseguire client. exe da \client\bin\\\, dalla cartella specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-139">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="4eec0-140">L'attività del client viene visualizzata nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-140">Client activity is displayed on the client console window.</span></span> <span data-ttu-id="4eec0-141">Avviare più client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-141">Launch several clients.</span></span>  
  
3. <span data-ttu-id="4eec0-142">Eseguire DataSource. exe da \datasource\bin\\, dalla cartella specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-142">Run Datasource.exe from \datasource\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="4eec0-143">L'attività dell'origine dati viene visualizzata nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="4eec0-143">Data source activity is displayed on the console window.</span></span> <span data-ttu-id="4eec0-144">Dopo l'invio delle informazioni al servizio da parte dell'origine dati, è necessario che tali informazioni vengano inviate a ogni client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-144">Once the data source sends information to the service, it should be passed on to each client.</span></span>  
  
4. <span data-ttu-id="4eec0-145">Se il client, l'origine dati e i programmi di servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4eec0-145">If the client, data source, and service programs are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="4eec0-146">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="4eec0-146">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="4eec0-147">Configurare il computer del servizio:</span><span class="sxs-lookup"><span data-stu-id="4eec0-147">Set up the service machine:</span></span>  
  
    1. <span data-ttu-id="4eec0-148">Sul computer del servizio, creare una directory virtuale denominata ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="4eec0-148">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="4eec0-149">Il file batch Setupvroot. bat dalla [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) può essere utilizzato per creare la directory del disco e la directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="4eec0-149">The batch file Setupvroot.bat from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2. <span data-ttu-id="4eec0-150">Copiare i file del programma del servizio da %SystemDrive%\Inetpub\wwwroot\servicemodelsamples alla directory virtuale di ServiceModelSamples sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-150">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="4eec0-151">Verificare di includere i file nella directory \bin.</span><span class="sxs-lookup"><span data-stu-id="4eec0-151">Be sure to include the files in the \bin directory.</span></span>  
  
    3. <span data-ttu-id="4eec0-152">Verificare che sia possibile accedere al servizio dal computer client usando un browser.</span><span class="sxs-lookup"><span data-stu-id="4eec0-152">Test that you can access the service from the client machine using a browser.</span></span>  
  
2. <span data-ttu-id="4eec0-153">Configurare i computer client:</span><span class="sxs-lookup"><span data-stu-id="4eec0-153">Set up the client machines:</span></span>  
  
    1. <span data-ttu-id="4eec0-154">Copiare i file del programma client dalla cartella \client\bin\, nella cartella specifica del linguaggio, all'interno dei computer client.</span><span class="sxs-lookup"><span data-stu-id="4eec0-154">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machines.</span></span>  
  
    2. <span data-ttu-id="4eec0-155">In ogni file di configurazione del client modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-155">In each client configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="4eec0-156">Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="4eec0-156">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
3. <span data-ttu-id="4eec0-157">Configurare il computer dell'origine dati:</span><span class="sxs-lookup"><span data-stu-id="4eec0-157">Set up the data source machine:</span></span>  
  
    1. <span data-ttu-id="4eec0-158">Copiare i file del programma dell'origine dati dalla cartella \datasource\bin\, nella cartella specifica del linguaggio, all'interno del computer dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4eec0-158">Copy the data source program files from the \datasource\bin\ folder, under the language-specific folder, to the data source machine.</span></span>  
  
    2. <span data-ttu-id="4eec0-159">Nel file di configurazione dell'origine dati modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="4eec0-159">In the data source configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="4eec0-160">Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="4eec0-160">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
4. <span data-ttu-id="4eec0-161">Nei computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-161">On the client machines, launch Client.exe from a command prompt.</span></span>  
  
5. <span data-ttu-id="4eec0-162">Nel computer dell'origine dati avviare Datasource.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-162">On the data source machine, launch Datasource.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4eec0-163">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4eec0-163">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4eec0-164">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4eec0-164">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4eec0-165">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4eec0-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4eec0-166">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4eec0-166">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`  
