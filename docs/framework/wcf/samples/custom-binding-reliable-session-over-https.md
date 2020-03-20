---
title: Sessione affidabile di associazione personalizzata su HTTPS
ms.date: 03/30/2017
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
ms.openlocfilehash: 051e7f56662a2ca67018ae7dd29189ff50245fc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183865"
---
# <a name="custom-binding-reliable-session-over-https"></a><span data-ttu-id="6b644-102">Sessione affidabile di associazione personalizzata su HTTPS</span><span class="sxs-lookup"><span data-stu-id="6b644-102">Custom Binding Reliable Session over HTTPS</span></span>
<span data-ttu-id="6b644-103">In questo esempio viene illustrato l'utilizzo della sicurezza del trasporto SSL con le sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="6b644-103">This sample demonstrates the use of SSL transport security with Reliable Sessions.</span></span> <span data-ttu-id="6b644-104">Le sessioni affidabili implementano il protocollo WS-RM (WS-Reliable Messaging).</span><span class="sxs-lookup"><span data-stu-id="6b644-104">Reliable Sessions implements the WS-Reliable Messaging protocol.</span></span> <span data-ttu-id="6b644-105">È possibile ottenere una sessione affidabile protetta componendo WS-Security su sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="6b644-105">You can have a secure reliable session by composing WS-Security over Reliable Sessions.</span></span> <span data-ttu-id="6b644-106">Tuttavia, è anche possibile scegliere di utilizzare la sicurezza del trasporto HTTP con SSL.</span><span class="sxs-lookup"><span data-stu-id="6b644-106">But sometimes, you may choose to instead use HTTP transport security with SSL.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b644-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6b644-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6b644-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6b644-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6b644-109">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6b644-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b644-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6b644-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a><span data-ttu-id="6b644-111">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="6b644-111">Sample Details</span></span>  
 <span data-ttu-id="6b644-112">SSL assicura che i pacchetti stessi siano protetti.</span><span class="sxs-lookup"><span data-stu-id="6b644-112">SSL ensures that the packets themselves are secured.</span></span> <span data-ttu-id="6b644-113">È importante notare che questo meccanismo è diverso dalla protezione della sessione affidabile mediante WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="6b644-113">It is important to note that this is different from securing the reliable session using WS-Secure Conversation.</span></span>  
  
 <span data-ttu-id="6b644-114">Per utilizzare sessioni affidabili su HTTPS, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6b644-114">To use reliable session over HTTPS, you must create a custom binding.</span></span> <span data-ttu-id="6b644-115">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="6b644-115">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="6b644-116">Un'associazione personalizzata viene creata utilizzando l'elemento di associazione di sessione affidabile e [ \<l'>httpsTransport ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md).</span><span class="sxs-lookup"><span data-stu-id="6b644-116">A custom binding is created using the reliable session binding element and the [\<httpsTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md).</span></span> <span data-ttu-id="6b644-117">La configurazione seguente riguarda l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6b644-117">The following configuration is of the custom binding.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="reliableSessionOverHttps"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed as http://localhost/servicemodelsamples/service.svc/mex-->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="reliableSessionOverHttps">  
          <reliableSession />  
          <httpsTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="true" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="6b644-118">Il codice del programma nell'esempio è identico a quello del servizio [Guida introduttiva.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="6b644-118">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="6b644-119">È necessario creare un certificato e assegnarlo utilizzando la Gestione guidata certificati server Web prima di compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="6b644-119">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="6b644-120">Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione abilitano l'uso dell'associazione personalizzata, come illustrato nella configurazione di esempio seguente per il client.</span><span class="sxs-lookup"><span data-stu-id="6b644-120">The endpoint definition and binding definition in the configuration file settings enable the use of custom binding as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint name=""  
                address="https://localhost/servicemodelsamples/service.svc"
                binding="customBinding"
                bindingConfiguration="reliableSessionOverHttps"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
      <bindings>  
        <customBinding>  
          <binding name="reliableSessionOverHttps">  
            <reliableSession />  
            <httpsTransport />  
          </binding>  
        </customBinding>
    </bindings>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="6b644-121">L'indirizzo specificato utilizza lo schema https://.</span><span class="sxs-lookup"><span data-stu-id="6b644-121">The address specified uses the https:// scheme.</span></span>  
  
 <span data-ttu-id="6b644-122">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert.exe, https://localhost/servicemodelsamples/service.svcviene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo https:, ad esempio , dal browser.</span><span class="sxs-lookup"><span data-stu-id="6b644-122">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="6b644-123">Per consentire al client Windows Communication Foundation (WCF) di lavorare con un certificato di prova sul posto, è stato aggiunto codice aggiuntivo al client per eliminare l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6b644-123">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="6b644-124">Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.</span><span class="sxs-lookup"><span data-stu-id="6b644-124">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="6b644-125">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="6b644-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6b644-126">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="6b644-126">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6b644-127">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6b644-127">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6b644-128">Installare ASP.NET 4.0 utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6b644-128">Install  ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="6b644-129">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b644-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="6b644-130">Assicurarsi di aver eseguito le istruzioni per l'installazione dei certificati server di [Internet Information Services (IIS).](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)</span><span class="sxs-lookup"><span data-stu-id="6b644-130">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="6b644-131">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b644-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="6b644-132">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b644-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
