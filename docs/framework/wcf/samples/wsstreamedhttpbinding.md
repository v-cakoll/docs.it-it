---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d6259640bae2b4be4fac73883df8945bf1db7ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="de26c-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="de26c-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="de26c-103">Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene utilizzato il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="de26c-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de26c-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="de26c-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="de26c-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="de26c-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="de26c-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="de26c-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="de26c-107">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de26c-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="de26c-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="de26c-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="de26c-109">I passaggi per creare e configurare una nuova associazione standard sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="de26c-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="de26c-110">Creazione di una nuova associazione standard</span><span class="sxs-lookup"><span data-stu-id="de26c-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="de26c-111">Le associazioni standard di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], ad esempio basicHttpBinding e netTcpBinding configurano i trasporti sottostanti e i stack di canali per i requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="de26c-111">The standard bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="de26c-112">In questo esempio, `WSStreamedHttpBinding` configura lo stack di canali per supportare il flusso.</span><span class="sxs-lookup"><span data-stu-id="de26c-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="de26c-113">Per impostazione predefinita, WS-Security e la messaggistica affidabile non vengono aggiunti allo stack di canali perché entrambi le funzionalità non sono supportate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="de26c-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="de26c-114">La nuova associazione viene implementata nella classe `WSStreamedHttpBinding` che deriva da <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="de26c-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="de26c-115">`WSStreamedHttpBinding` contiene i seguenti elementi di associazione: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> e <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="de26c-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="de26c-116">La classe fornisce un metodo `CreateBindingElements()` per configurare lo stack dell'associazione risultante, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="de26c-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  <span data-ttu-id="de26c-117">Aggiunta del supporto di configurazione</span><span class="sxs-lookup"><span data-stu-id="de26c-117">Add configuration support</span></span>  
  
     <span data-ttu-id="de26c-118">Per esporre il trasporto tramite la configurazione l'esempio implementa altre due classi: `WSStreamedHttpBindingConfigurationElement` e `WSStreamedHttpBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="de26c-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="de26c-119">La classe `WSStreamedHttpBindingSection` è una classe  <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> che espone `WSStreamedHttpBinding` al sistema di configurazione di  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de26c-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system.</span></span> <span data-ttu-id="de26c-120">La maggior parte dell'implementazione viene delegata a `WSStreamedHttpBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="de26c-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="de26c-121">La classe `WSStreamedHttpBindingConfigurationElement` è dotata delle proprietà che corrispondono alle proprietà di `WSStreamedHttpBinding` e funzioni che consentono di eseguire il mapping di ogni elemento di configurazione a un'associazione.</span><span class="sxs-lookup"><span data-stu-id="de26c-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="de26c-122">Registrare il gestore nel sistema di configurazione, aggiungendo la sezione seguente al file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="de26c-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="de26c-123">È possibile fare riferimento al gestore dalla sezione di configurazione serviceModel.</span><span class="sxs-lookup"><span data-stu-id="de26c-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="de26c-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="de26c-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="de26c-125">Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="de26c-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="de26c-126">Assicurarsi di avere eseguito i passaggi elencati in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="de26c-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="de26c-127">Assicurarsi di avere eseguito la [istruzioni di installazione certificato Server Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="de26c-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="de26c-128">Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="de26c-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="de26c-129">Per eseguire l'esempio in una configurazione con più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="de26c-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="de26c-130">Quando viene visualizzata la finestra client, digitare "Esempio.txt."</span><span class="sxs-lookup"><span data-stu-id="de26c-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="de26c-131">Nella directory dovrebbe essere presente una "Copia di Esempio.txt".</span><span class="sxs-lookup"><span data-stu-id="de26c-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="de26c-132">Esempio di servizio WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="de26c-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="de26c-133">L'esempio di servizio che utilizza `WSStreamedHttpBinding` si trova nella sottodirectory del servizio.</span><span class="sxs-lookup"><span data-stu-id="de26c-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="de26c-134">L'implementazione di `OperationContract` utilizza un `MemoryStream` per recuperare tutti i dati dal flusso in ingresso prima di restituire `MemoryStream`.</span><span class="sxs-lookup"><span data-stu-id="de26c-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="de26c-135">L'esempio di servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="de26c-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="de26c-136">Esempio di Client WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="de26c-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="de26c-137">Il client utilizzato per interagire con il servizio utilizzando `WSStreamedHttpBinding` si trova nella sottodirectory client.</span><span class="sxs-lookup"><span data-stu-id="de26c-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="de26c-138">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert.exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo HTTPS nel browser, ad esempio https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="de26c-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="de26c-139">Per consentire al client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di lavorare con un certificato di prova, è stato aggiunto altro codice al client per sopprimere l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="de26c-139">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="de26c-140">Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.</span><span class="sxs-lookup"><span data-stu-id="de26c-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="de26c-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de26c-141">See Also</span></span>
