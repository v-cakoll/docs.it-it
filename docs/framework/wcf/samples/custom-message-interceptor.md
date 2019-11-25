---
title: Intercettore dei messaggi personalizzati
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 61f9bae24f5edb70430f4f3eaa16e42da221a7b4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978303"
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="82197-102">Intercettore dei messaggi personalizzati</span><span class="sxs-lookup"><span data-stu-id="82197-102">Custom Message Interceptor</span></span>
<span data-ttu-id="82197-103">In questo esempio viene illustrato l'utilizzo del modello di estensibilità del canale.</span><span class="sxs-lookup"><span data-stu-id="82197-103">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="82197-104">In particolare, viene illustrato come implementare un elemento di associazione personalizzato che crea channel factory e listener del canale per intercettare tutti i messaggi in ingresso e in uscita in un particolare punto nello stack di runtime.</span><span class="sxs-lookup"><span data-stu-id="82197-104">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="82197-105">L'esempio include anche un client e un server che illustrano l'utilizzo di queste factory personalizzate.</span><span class="sxs-lookup"><span data-stu-id="82197-105">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="82197-106">In questo esempio sia il client che il servizio sono programmi console (.exe).</span><span class="sxs-lookup"><span data-stu-id="82197-106">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="82197-107">Il client e il servizio fanno entrambi uso di una libreria comune (.dll) che contiene l'elemento di associazione personalizzato e gli oggetti di runtime associati.</span><span class="sxs-lookup"><span data-stu-id="82197-107">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82197-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="82197-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="82197-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="82197-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82197-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="82197-110">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="82197-111">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="82197-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82197-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="82197-112">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="82197-113">Nell'esempio viene descritta la procedura consigliata per la creazione di un canale su più livelli personalizzato in Windows Communication Foundation (WCF) utilizzando il Framework del canale e le procedure consigliate WCF seguenti.</span><span class="sxs-lookup"><span data-stu-id="82197-113">The sample describes the recommended procedure for creating a custom layered channel in Windows Communication Foundation (WCF), by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="82197-114">I passaggi per creare un canale su più livelli personalizzato sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="82197-114">The steps to create a custom layered channel are as follows:</span></span>  
  
1. <span data-ttu-id="82197-115">Decidere quali forme del canale saranno supportate dalla channel factory e dal listener del canale.</span><span class="sxs-lookup"><span data-stu-id="82197-115">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2. <span data-ttu-id="82197-116">Creare una channel factory e un listener di canale che supportano le forme del canale.</span><span class="sxs-lookup"><span data-stu-id="82197-116">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3. <span data-ttu-id="82197-117">Inserire un elemento di associazione che aggiunge il canale su più livelli personalizzato a uno stack di canali.</span><span class="sxs-lookup"><span data-stu-id="82197-117">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4. <span data-ttu-id="82197-118">Aggiungere una sezione di estensione degli elementi di associazione per esporre il nuovo elemento di associazione al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="82197-118">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="82197-119">Forme del canale</span><span class="sxs-lookup"><span data-stu-id="82197-119">Channel Shapes</span></span>  
 <span data-ttu-id="82197-120">Per scrivere un canale su più livelli personalizzato, è necessario innanzitutto stabilire quali forme sono necessarie per il canale.</span><span class="sxs-lookup"><span data-stu-id="82197-120">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="82197-121">Per il controllo messaggi, si supporta qualsiasi forma supportata dal livello sottostante (ad esempio, se il livello sottostante può compilare <xref:System.ServiceModel.Channels.IOutputChannel> e <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, si espongono anche <xref:System.ServiceModel.Channels.IOutputChannel> e <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span><span class="sxs-lookup"><span data-stu-id="82197-121">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="82197-122">Channel Factory e Listener Factory</span><span class="sxs-lookup"><span data-stu-id="82197-122">Channel Factory and Listener Factory</span></span>  
 <span data-ttu-id="82197-123">Il passaggio successivo per scrivere un canale su più livelli personalizzato consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelFactory> per i canali client e di <xref:System.ServiceModel.Channels.IChannelListener> per i canali del servizio.</span><span class="sxs-lookup"><span data-stu-id="82197-123">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="82197-124">Queste classi prendono una factory interna e un listener e delegano tutto tranne le chiamate `OnCreateChannel` e `OnAcceptChannel` alla factory interna e al listener.</span><span class="sxs-lookup"><span data-stu-id="82197-124">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ 
    //... 
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ 
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="82197-125">Aggiunta di un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="82197-125">Adding a Binding Element</span></span>  
 <span data-ttu-id="82197-126">L'esempio definisce un elemento di associazione personalizzato: `InterceptingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="82197-126">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="82197-127">`InterceptingBindingElement` accetta come input un `ChannelMessageInterceptor` e utilizza questo `ChannelMessageInterceptor` per modificare i messaggi che lo passano.</span><span class="sxs-lookup"><span data-stu-id="82197-127">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="82197-128">Si tratta della sola classe che deve essere pubblica.</span><span class="sxs-lookup"><span data-stu-id="82197-128">This is the only class that must be public.</span></span> <span data-ttu-id="82197-129">La factory, il listener e i canali possono tutti essere implementazioni interne delle interfacce di runtime pubbliche.</span><span class="sxs-lookup"><span data-stu-id="82197-129">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="82197-130">Aggiunta del supporto di configurazione</span><span class="sxs-lookup"><span data-stu-id="82197-130">Adding Configuration Support</span></span>  
 <span data-ttu-id="82197-131">Per integrare la configurazione di associazione la libreria definisce un gestore della sezione di configurazione come sezione di estensione dell'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="82197-131">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="82197-132">I file di configurazione del client e del server devono registrare l'estensione dell'elemento di associazione con il sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="82197-132">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="82197-133">Implementatori che vogliono esporre l'elemento di associazione al sistema di configurazione possono derivare da questa classe.</span><span class="sxs-lookup"><span data-stu-id="82197-133">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement 
{ 
    //... 
}
```  
  
## <a name="adding-policy"></a><span data-ttu-id="82197-134">Aggiunta di criteri</span><span class="sxs-lookup"><span data-stu-id="82197-134">Adding Policy</span></span>  
 <span data-ttu-id="82197-135">Per integrarsi con il sistema dei criteri, `InterceptingBindingElement` implementa IPolicyExportExtension per segnalare che si deve partecipare alla generazione di criteri.</span><span class="sxs-lookup"><span data-stu-id="82197-135">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="82197-136">Per supportare i criteri di importazione su un client generato, l'utente può iscrivere una classe derivata di `InterceptingBindingElementImporter`() ed eseguire l'override di `CreateMessageInterceptor` per generare la classe `ChannelMessageInterceptor` attivata dal criterio.</span><span class="sxs-lookup"><span data-stu-id="82197-136">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="82197-137">Esempio: Controllo messaggi rilasciabili</span><span class="sxs-lookup"><span data-stu-id="82197-137">Example: Droppable Message Inspector</span></span>  
 <span data-ttu-id="82197-138">Inclusa nell'esempio vi è un'implementazione di esempio di `ChannelMessageInspector` che elimina i messaggi.</span><span class="sxs-lookup"><span data-stu-id="82197-138">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="82197-139">È possibile accedervi tramite configurazione come segue:</span><span class="sxs-lookup"><span data-stu-id="82197-139">You can access it from configuration as follows:</span></span>  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"   
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="82197-140">Il client e il server utilizzano entrambi questa sezione di configurazione appena creata per inserire le factory personalizzate nel livello più basso degli stack dei canali di runtime (sopra il livello del trasporto).</span><span class="sxs-lookup"><span data-stu-id="82197-140">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="82197-141">Il client utilizza la libreria `MessageInterceptor` per aggiungere un'intestazione personalizzata ai messaggi, anche a quelli numerati.</span><span class="sxs-lookup"><span data-stu-id="82197-141">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="82197-142">Il servizio d'altro canto utilizza la libreria `MessageInterceptor` per eliminare qualsiasi messaggio che non ha questa intestazione speciale.</span><span class="sxs-lookup"><span data-stu-id="82197-142">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="82197-143">Dopo l'esecuzione del servizio e del client, l'output del client dovrebbe essere il seguente.</span><span class="sxs-lookup"><span data-stu-id="82197-143">You should see the following client output after running the service and then the client.</span></span>  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 <span data-ttu-id="82197-144">Il client riporta 10 diverse velocità del vento al servizio, ma contrassegna solo la metà di esse con un'intestazione speciale.</span><span class="sxs-lookup"><span data-stu-id="82197-144">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="82197-145">Nel servizio, si dovrebbe vedere l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="82197-145">On the service, you should see the following output:</span></span>  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82197-146">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="82197-146">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="82197-147">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="82197-147">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="82197-148">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82197-148">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="82197-149">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82197-149">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="82197-150">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82197-150">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="82197-151">Eseguire prima Service.exe quindi Client.exe e controllare l'output di entrambe le finestre della console.</span><span class="sxs-lookup"><span data-stu-id="82197-151">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
