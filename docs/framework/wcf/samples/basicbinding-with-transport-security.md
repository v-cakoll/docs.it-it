---
title: BasicBinding con sicurezza del trasporto
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
ms.openlocfilehash: 822a7dcb20c6559a70ba77719b6e7a62633bb31c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575667"
---
# <a name="basicbinding-with-transport-security"></a><span data-ttu-id="14a0e-102">BasicBinding con sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="14a0e-102">BasicBinding with Transport Security</span></span>

<span data-ttu-id="14a0e-103">Questo esempio dimostra l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="14a0e-103">This sample demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="14a0e-104">Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="14a0e-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14a0e-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="14a0e-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="14a0e-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="14a0e-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="14a0e-107">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="14a0e-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="14a0e-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="14a0e-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`

## <a name="sample-details"></a><span data-ttu-id="14a0e-109">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="14a0e-109">Sample Details</span></span>

<span data-ttu-id="14a0e-110">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="14a0e-110">By default, the basic binding supports HTTP communication.</span></span> <span data-ttu-id="14a0e-111">L'esempio illustra come abilitare sicurezza del trasporto per l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="14a0e-111">The sample shows how to enable transport security for the basic binding.</span></span> <span data-ttu-id="14a0e-112">Prima di eseguire l'esempio, è necessario creare un certificato e assegnarlo usando la Procedura guidata certificati server Web.</span><span class="sxs-lookup"><span data-stu-id="14a0e-112">Before you run the sample, you must create a certificate and assign it by using the Web Server Certificate Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="14a0e-113">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="14a0e-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="14a0e-114">Il codice programma nell'esempio è identico a quello del servizio [Introduzione](getting-started-sample.md) .</span><span class="sxs-lookup"><span data-stu-id="14a0e-114">The program code in the sample is identical to that of the [Getting Started](getting-started-sample.md) service.</span></span> <span data-ttu-id="14a0e-115">Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione sono state modificate per consentire la comunicazione protetta, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14a0e-115">The endpoint definition and binding definition in the configuration file settings are modified to enable secure communication, as shown in the following sample configuration.</span></span>

```xml
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
   </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"/>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```

<span data-ttu-id="14a0e-116">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert. exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo HTTPS: nel browser, ad esempio `https://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="14a0e-116">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an HTTPS: address in your browser, such as `https://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="14a0e-117">Per consentire il funzionamento del client Windows Communication Foundation (WCF) con un certificato di test, al client viene aggiunto codice aggiuntivo per non visualizzare l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="14a0e-117">To allow the Windows Communication Foundation (WCF) client to work with a test certificate, some additional code is added to the client to suppress the security alert.</span></span> <span data-ttu-id="14a0e-118">Il codice e la classe associata non sono necessari quando si usano certificati reali.</span><span class="sxs-lookup"><span data-stu-id="14a0e-118">This code, and the accompanying class, is not necessary when using real certificates.</span></span>

```csharp
// This code is required only for test certificates such as those
// created by Makecert.exe.
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");
```

<span data-ttu-id="14a0e-119">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="14a0e-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="14a0e-120">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="14a0e-120">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="14a0e-121">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="14a0e-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="14a0e-122">Installare ASP.NET 4,0 usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14a0e-122">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="14a0e-123">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14a0e-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="14a0e-124">Assicurarsi di aver eseguito le [istruzioni di installazione del certificato Server Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="14a0e-124">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](iis-server-certificate-installation-instructions.md).</span></span>

4. <span data-ttu-id="14a0e-125">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14a0e-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

5. <span data-ttu-id="14a0e-126">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14a0e-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>
