---
title: '&lt;message&gt; di &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: 8c3519e2db12e34d9f2bd03689e0e9684c5792ae
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151280"
---
# <a name="ltmessagegt-of-ltbasichttpbindinggt"></a><span data-ttu-id="99c8d-102">&lt;message&gt; di &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="99c8d-102">&lt;message&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="99c8d-103">Definisce le impostazioni per la sicurezza a livello di messaggio dei [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="99c8d-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="99c8d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="99c8d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99c8d-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="99c8d-105">\<bindings></span></span>  
<span data-ttu-id="99c8d-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="99c8d-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="99c8d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="99c8d-107">\<binding></span></span>  
<span data-ttu-id="99c8d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="99c8d-108">\<security></span></span>  
<span data-ttu-id="99c8d-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="99c8d-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c8d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99c8d-110">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c8d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99c8d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99c8d-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99c8d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c8d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="99c8d-113">Attributes</span></span>  
  
|<span data-ttu-id="99c8d-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="99c8d-114">Attribute</span></span>|<span data-ttu-id="99c8d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c8d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99c8d-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="99c8d-116">algorithmSuite</span></span>|<span data-ttu-id="99c8d-117">Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="99c8d-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="99c8d-118">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, che specifica gli algoritmi e le dimensioni della chiave.</span><span class="sxs-lookup"><span data-stu-id="99c8d-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="99c8d-119">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="99c8d-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="99c8d-120">Il valore predefinito è `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="99c8d-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="99c8d-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="99c8d-121">clientCredentialType</span></span>|<span data-ttu-id="99c8d-122">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza basata sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="99c8d-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="99c8d-123">Il valore predefinito è `UserName`.</span><span class="sxs-lookup"><span data-stu-id="99c8d-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="99c8d-124">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="99c8d-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="99c8d-125">Valore</span><span class="sxs-lookup"><span data-stu-id="99c8d-125">Value</span></span>|<span data-ttu-id="99c8d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c8d-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99c8d-127">UserName</span><span class="sxs-lookup"><span data-stu-id="99c8d-127">UserName</span></span>|<span data-ttu-id="99c8d-128">-Richiede l'autenticazione del client al server con una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="99c8d-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="99c8d-129">La credenziale deve essere specificata tramite il [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="99c8d-129">This credential needs to be specified using the [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span></span><br /><span data-ttu-id="99c8d-130">-WCF non supporta l'invio di un digest delle password o la derivazione delle chiavi usando le password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="99c8d-130">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="99c8d-131">WCF impone quindi che il trasporto sia protetto quando si usano credenziali UserName.</span><span class="sxs-lookup"><span data-stu-id="99c8d-131">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="99c8d-132">Per `basicHttpBinding`, questo richiede l'impostazione di un canale SSL.</span><span class="sxs-lookup"><span data-stu-id="99c8d-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="99c8d-133">Certificato</span><span class="sxs-lookup"><span data-stu-id="99c8d-133">Certificate</span></span>|<span data-ttu-id="99c8d-134">Richiede che l'autenticazione del client sul server avvenga mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="99c8d-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="99c8d-135">La credenziale client in questo caso deve essere specificata mediante [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) e il [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="99c8d-135">The client credential in this case needs to be specified using [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) and the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="99c8d-136">Inoltre, quando si usa la modalità di sicurezza del messaggio, è necessario eseguire il provisioning del client con il certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="99c8d-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="99c8d-137">La credenziale del servizio in questo caso deve essere specificata mediante <xref:System.ServiceModel.Description.ClientCredentials> classe oppure `ClientCredentials` elemento del comportamento e specificando il certificato tramite il [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="99c8d-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c8d-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99c8d-138">Child Elements</span></span>  
 <span data-ttu-id="99c8d-139">nessuno</span><span class="sxs-lookup"><span data-stu-id="99c8d-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c8d-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99c8d-140">Parent Elements</span></span>  
  
|<span data-ttu-id="99c8d-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="99c8d-141">Element</span></span>|<span data-ttu-id="99c8d-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c8d-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99c8d-143">\<security></span><span class="sxs-lookup"><span data-stu-id="99c8d-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="99c8d-144">Definisce le funzionalità di sicurezza per il [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="99c8d-144">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99c8d-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="99c8d-145">Example</span></span>  
 <span data-ttu-id="99c8d-146">In questo esempio viene dimostrato come implementare un'applicazione che usa basicHttpBinding e la sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="99c8d-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="99c8d-147">Nel seguente esempio di configurazione di un servizio, la definizione dell'endpoint specifica basicHttpBinding e fa riferimento a una configurazione di associazione denominata `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="99c8d-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="99c8d-148">Il certificato usato dal servizio per l'autenticazione con il client è impostato nella sezione `behaviors` del file di configurazione sotto l'elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="99c8d-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="99c8d-149">Anche la modalità di convalida applicata al certificato usato dal servizio per l'autenticazione con il client è impostata nella sezione `behaviors` del file di configurazione sotto l'elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="99c8d-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="99c8d-150">Gli stessi dettagli sull'associazione e la sicurezza sono specificati nel file di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="99c8d-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
    <!-- This configuration defines the SecurityMode as Message and
         the clientCredentialType as Certificate. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
               is in the user's Trusted People store, then it will be trusted without performing a
               validation of the certificate's issuer chain. This setting is used here for convenience so that the
               sample can be run without having to have certificates issued by a certification authority (CA).
               This setting is less secure than the default, ChainTrust. The security implications of this
               setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="99c8d-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99c8d-151">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpMessageSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>  
 [<span data-ttu-id="99c8d-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="99c8d-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="99c8d-153">Associazioni</span><span class="sxs-lookup"><span data-stu-id="99c8d-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99c8d-154">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="99c8d-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="99c8d-155">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="99c8d-155">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="99c8d-156">\<binding></span><span class="sxs-lookup"><span data-stu-id="99c8d-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
