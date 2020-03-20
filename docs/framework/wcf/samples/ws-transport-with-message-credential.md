---
title: Trasporto WS con credenziali del messaggio
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 076d4490f6edc6efa8eeb50ae8baa23d5c4e369a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183141"
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="6d9a1-102">Trasporto WS con credenziali del messaggio</span><span class="sxs-lookup"><span data-stu-id="6d9a1-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="6d9a1-103">In questo esempio viene illustrato l'utilizzo della sicurezza del trasporto SSL in combinazione con l'inclusione delle credenziali client nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="6d9a1-104">In questo esempio viene usata l'associazione `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="6d9a1-105">Per impostazione predefinita, l'associazione `wsHttpBinding` consente la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="6d9a1-106">Se viene configurata per la sicurezza del trasporto, l'associazione supporta la comunicazione HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="6d9a1-107">Il protocollo HTTPS garantisce la riservatezza e l'integrità dei messaggi trasmessi in rete.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="6d9a1-108">Tuttavia il set di meccanismi di autenticazione che possono essere utilizzati per autenticare il client nel servizio è limitato ai meccanismi supportati dal trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="6d9a1-109">Windows Communication Foundation (WCF) offre una `TransportWithMessageCredential` modalità di sicurezza progettata per superare questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="6d9a1-110">Se è configurata questa modalità di sicurezza, viene utilizzata la sicurezza del trasporto per garantire la riservatezza e l'integrità dei messaggi trasmessi e per eseguire l'autenticazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="6d9a1-111">Tuttavia, l'autenticazione client viene eseguita inserendo la credenziale client direttamente nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="6d9a1-112">In questo modo è possibile utilizzare qualsiasi tipo di credenziale supportato dalla modalità di sicurezza dei messaggi per l'autenticazione del client, mantenendo i vantaggi a livello di prestazioni offerti dalla modalità di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="6d9a1-113">In questo esempio viene utilizzato un tipo di credenziale `UserName` per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="6d9a1-114">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="6d9a1-115">L'associazione `wsHttpBinding` è specificata e configurata nei file di configurazione dell'applicazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d9a1-116">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6d9a1-117">Il codice del programma nell'esempio è quasi identico a quello del servizio [Guida introduttiva.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="6d9a1-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="6d9a1-118">È tuttavia presente un'operazione aggiuntiva fornita dal contratto di servizio, ovvero `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="6d9a1-119">Questa operazione restituisce il nome dell'identità del chiamante al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="6d9a1-120">È necessario creare un certificato e assegnarlo utilizzando la Gestione guidata certificati server Web prima di compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="6d9a1-121">Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione abilitano la modalità di sicurezza `TransportWithMessageCredential`, come illustrato nella configurazione di esempio seguente per il client.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="6d9a1-122">L'indirizzo specificato utilizza lo schema https://.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="6d9a1-123">La configurazione dell'associazione imposta la modalità di sicurezza su `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="6d9a1-124">La stessa modalità di sicurezza deve essere specificata nel file Web.config del servizio.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="6d9a1-125">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con Makecert.exe, `https://localhost/servicemodelsamples/service.svc`viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo https:, ad esempio , dal browser.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as  `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span> <span data-ttu-id="6d9a1-126">Per consentire al client WCF di utilizzare un certificato di prova sul posto, è stato aggiunto del codice aggiuntivo al client per eliminare l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="6d9a1-127">Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="6d9a1-128">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6d9a1-129">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="6d9a1-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:
YourDomainName\YourAccountName  
   Enter password:
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6d9a1-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6d9a1-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6d9a1-131">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a1-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6d9a1-132">Assicurarsi di aver eseguito le istruzioni per l'installazione dei certificati server di [Internet Information Services (IIS).](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)</span><span class="sxs-lookup"><span data-stu-id="6d9a1-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3. <span data-ttu-id="6d9a1-133">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a1-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="6d9a1-134">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a1-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
