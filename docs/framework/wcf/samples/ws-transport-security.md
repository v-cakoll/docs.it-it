---
title: Sicurezza del trasporto WS
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: d0f357ddcfc355bac8eeb86d57641add0013a052
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596397"
---
# <a name="ws-transport-security"></a><span data-ttu-id="b02a0-102">Sicurezza del trasporto WS</span><span class="sxs-lookup"><span data-stu-id="b02a0-102">WS Transport Security</span></span>
<span data-ttu-id="b02a0-103">In questo esempio viene illustrato l'utilizzo della sicurezza del trasporto SSL con l'associazione <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b02a0-103">This sample demonstrates the use of SSL transport security with the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span> <span data-ttu-id="b02a0-104">Per impostazione predefinita, l'associazione `wsHttpBinding` consente la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="b02a0-104">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="b02a0-105">Se viene configurata per la sicurezza del trasporto, l'associazione supporta la comunicazione HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b02a0-105">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="b02a0-106">Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="b02a0-106">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="b02a0-107">L'associazione `wsHttpBinding` è specificata e configurata nei file di configurazione dell'applicazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="b02a0-107">The `wsHttpBinding` is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b02a0-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b02a0-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b02a0-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b02a0-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b02a0-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b02a0-110">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b02a0-111">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b02a0-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b02a0-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b02a0-112">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 <span data-ttu-id="b02a0-113">Il codice programma nell'esempio è identico a quello del servizio [Introduzione](getting-started-sample.md) .</span><span class="sxs-lookup"><span data-stu-id="b02a0-113">The program code in the sample is identical to that of the [Getting Started](getting-started-sample.md) service.</span></span> <span data-ttu-id="b02a0-114">È necessario creare un certificato e assegnarlo utilizzando la Gestione guidata certificati server Web prima di compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="b02a0-114">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="b02a0-115">Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione abilitano la modalità di sicurezza `Transport`, come illustrato nella configurazione di esempio seguente per il client.</span><span class="sxs-lookup"><span data-stu-id="b02a0-115">The endpoint definition and binding definition in the configuration file settings enable `Transport` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="b02a0-116">L'indirizzo specificato utilizza lo `https://` schema.</span><span class="sxs-lookup"><span data-stu-id="b02a0-116">The address specified uses the `https://` scheme.</span></span> <span data-ttu-id="b02a0-117">La configurazione dell'associazione imposta la modalità di sicurezza su `Transport`.</span><span class="sxs-lookup"><span data-stu-id="b02a0-117">The binding configuration sets the security mode to `Transport`.</span></span> <span data-ttu-id="b02a0-118">La stessa modalità di sicurezza deve essere specificata nel file Web.config del servizio.</span><span class="sxs-lookup"><span data-stu-id="b02a0-118">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="b02a0-119">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert. exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo https:, ad esempio `https://localhost/servicemodelsamples/service.svc` , dal browser.</span><span class="sxs-lookup"><span data-stu-id="b02a0-119">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span> <span data-ttu-id="b02a0-120">Per consentire al client Windows Communication Foundation (WCF) di utilizzare un certificato di prova, è stato aggiunto al client un altro codice per evitare l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b02a0-120">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="b02a0-121">Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.</span><span class="sxs-lookup"><span data-stu-id="b02a0-121">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="b02a0-122">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="b02a0-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b02a0-123">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="b02a0-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b02a0-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b02a0-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b02a0-125">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b02a0-125">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="b02a0-126">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b02a0-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="b02a0-127">Assicurarsi di aver eseguito le [istruzioni di installazione del certificato Server Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="b02a0-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="b02a0-128">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b02a0-128">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="b02a0-129">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b02a0-129">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
