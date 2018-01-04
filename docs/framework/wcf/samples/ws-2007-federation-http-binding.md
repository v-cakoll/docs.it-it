---
title: Associazione HTTP WS 2007 Federation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b04984ad1e21da4bc86760046029d3b94b70758
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="47fb3-102">Associazione HTTP WS 2007 Federation</span><span class="sxs-lookup"><span data-stu-id="47fb3-102">WS 2007 Federation HTTP Binding</span></span>
<span data-ttu-id="47fb3-103">In questo esempio viene descritto l'utilizzo di <xref:System.ServiceModel.WS2007FederationHttpBinding>, un'associazione standard che è possibile utilizzare per compilare scenari federati che supportano la versione 1.3 della specifica WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="47fb3-103">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47fb3-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="47fb3-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="47fb3-105">Questo esempio è costituito da un programma console (Client.exe), da un programma del servizio token di sicurezza basato su console (Securitytokenservice.exe) e da un programma di console del servizio (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="47fb3-105">The sample consists of a console-based client program (Client.exe), a console-based security token service program (Securitytokenservice.exe), and a console-based service program (Service.exe).</span></span> <span data-ttu-id="47fb3-106">Il servizio implementa un contratto che definisce un modello di comunicazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="47fb3-106">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="47fb3-107">Il contratto viene definito dall'interfaccia `ICalculator` che espone operazioni matematiche (`Add`, `Subtract`, `Multiply` e `Divide`).</span><span class="sxs-lookup"><span data-stu-id="47fb3-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="47fb3-108">Il client riceve un token di protezione dal servizio token di sicurezza (STS), esegue richieste sincrone al servizio per un'operazione matematica specificata.</span><span class="sxs-lookup"><span data-stu-id="47fb3-108">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="47fb3-109">Il servizio risponde quindi fornendo il risultato.</span><span class="sxs-lookup"><span data-stu-id="47fb3-109">The service then replies with the result.</span></span> <span data-ttu-id="47fb3-110">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="47fb3-110">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="47fb3-111">L'esempio rende disponibile il contratto `ICalculator` utilizzando l'elemento `ws2007FederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="47fb3-111">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="47fb3-112">La configurazione di quest'associazione sul client viene illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47fb3-112">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="47fb3-113">Nel [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` valore specifica la modalità di sicurezza deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="47fb3-113">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="47fb3-114">In questo esempio, `message` viene utilizzata la sicurezza per questo motivo il [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) viene specificato all'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="47fb3-114">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="47fb3-115">Il [ \<dell'autorità di certificazione >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) elemento all'interno di [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifica l'indirizzo e l'associazione per il servizio token di sicurezza che rilascia un token di sicurezza per il client in modo che il client può eseguire l'autenticazione di `ICalculator` servizio.</span><span class="sxs-lookup"><span data-stu-id="47fb3-115">The [\<issuer>](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>  
  
 <span data-ttu-id="47fb3-116">La configurazione di quest'associazione sul servizio viene illustrata nel seguente codice.</span><span class="sxs-lookup"><span data-stu-id="47fb3-116">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="47fb3-117">Nel [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` valore specifica la modalità di sicurezza deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="47fb3-117">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="47fb3-118">In questo esempio, `message` viene utilizzata la sicurezza per questo motivo il [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) viene specificato all'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="47fb3-118">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="47fb3-119">Il [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) elemento di `ws2007FederationHttpBinding` all'interno di [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifica l'indirizzo e l'identità di un endpoint che può essere utilizzato per recuperare metadati per il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="47fb3-119">The [\<issuerMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>  
  
 <span data-ttu-id="47fb3-120">Il comportamento per il servizio viene illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="47fb3-120">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="47fb3-121">Il [ \<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> consente al servizio specificare i vincoli su token che i client possono presentare durante l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="47fb3-121">The [\<issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="47fb3-122">Questa configurazione specifica che i token firmati da un certificato il cui nome di soggetto è CN=STS possono essere accettati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="47fb3-122">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="47fb3-123">Il servizio token di sicurezza rende disponibile un singolo endpoint utilizzando l'oggetto <xref:System.ServiceModel.WS2007HttpBinding> standard.</span><span class="sxs-lookup"><span data-stu-id="47fb3-123">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="47fb3-124">Il servizio risponde alle richieste dei client per i token.</span><span class="sxs-lookup"><span data-stu-id="47fb3-124">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="47fb3-125">Se il client viene autenticato utilizzando un account di Windows, il servizio pubblica un token che contiene il nome utente del client come attestazione.</span><span class="sxs-lookup"><span data-stu-id="47fb3-125">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="47fb3-126">Come parte del processo di creazione del token, il servizio token di sicurezza firma il token utilizzando la chiave privata associata al certificato CN=STS .</span><span class="sxs-lookup"><span data-stu-id="47fb3-126">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="47fb3-127">Crea, inoltre, una chiave simmetrica e la crittografa utilizzando la chiave pubblica associata al certificato CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="47fb3-127">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="47fb3-128">Nel restituire il token al client, il servizio token di sicurezza restituisce anche la chiave simmetrica.</span><span class="sxs-lookup"><span data-stu-id="47fb3-128">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="47fb3-129">Il client presenta il token emesso al servizio `ICalculator` e dimostra che conosce la chiave simmetrica firmando il messaggio con quella chiave.</span><span class="sxs-lookup"><span data-stu-id="47fb3-129">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
 <span data-ttu-id="47fb3-130">Quando si esegue l'esempio, la richiesta per il token di sicurezza viene visualizzata nella finestra della console del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="47fb3-130">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="47fb3-131">Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console del client e in quella del servizio.</span><span class="sxs-lookup"><span data-stu-id="47fb3-131">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="47fb3-132">Premere INVIO in una delle finestre della console per arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47fb3-132">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
 `Add(100,15.99) = 115.99`  
  
 `Subtract(145,76.54) = 68.46`  
  
 `Multiply(9,81.25) = 731.25`  
  
 `Divide(22,7) = 3.14285714285714`  
  
 `Press <ENTER> to terminate client.`  
  
 <span data-ttu-id="47fb3-133">Il file Setup.bat incluso in questo esempio consente di configurare il server e il servizio token di sicurezza con i certificati attinenti per eseguire un'applicazione indipendente.</span><span class="sxs-lookup"><span data-stu-id="47fb3-133">The Setup.bat file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="47fb3-134">Il file batch crea due certificati, nell'archivio certificati di LocalMachine/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="47fb3-134">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="47fb3-135">Il primo certificato ha un nome soggetto di CN=STS e viene utilizzato dal servizio token di sicurezza per firmare i token di protezione emessi al client.</span><span class="sxs-lookup"><span data-stu-id="47fb3-135">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="47fb3-136">Il secondo certificato ha un nome soggetto di CN=localhost e viene utilizzato dal servizio token di sicurezza per crittografare una chiave in modo che il servizio non possa decrittografarla.</span><span class="sxs-lookup"><span data-stu-id="47fb3-136">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="47fb3-137">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="47fb3-137">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="47fb3-138">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47fb3-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="47fb3-139">Aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire Setup.bat per creare i certificati necessari.</span><span class="sxs-lookup"><span data-stu-id="47fb3-139">Open a Visual Studio command prompt with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>  
  
 <span data-ttu-id="47fb3-140">Questo file batch utilizza Certmgr.exe e Makecert.exe, distribuiti con Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="47fb3-140">This batch file uses Certmgr.exe and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="47fb3-141">È necessario tuttavia eseguire Setup.bat in un prompt dei comandi di Visual Studio per consentire allo script di trovare tali strumenti.</span><span class="sxs-lookup"><span data-stu-id="47fb3-141">However, you must run Setup.bat from within a Visual Studio  command prompt to enable the script to find these tools.</span></span>  
  
1.  <span data-ttu-id="47fb3-142">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47fb3-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="47fb3-143">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47fb3-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="47fb3-144">Se si utilizza [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], è necessario eseguire Service.exe, Client.exe e SecurityTokenService.exe con privilegi elevati (fare clic sui file e quindi fare clic su **Esegui come amministratore**).</span><span class="sxs-lookup"><span data-stu-id="47fb3-144">If you are using [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must run Service.exe, Client.exe, and SecurityTokenService.exe with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47fb3-145">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="47fb3-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="47fb3-146">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="47fb3-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47fb3-147">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47fb3-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47fb3-148">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="47fb3-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
## <a name="see-also"></a><span data-ttu-id="47fb3-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47fb3-149">See Also</span></span>
