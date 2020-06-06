---
title: <message> di <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: 748a734af8cf6767ce47cfffce9aec3ef627cb44
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736736"
---
# <a name="message-of-basichttpbinding"></a><span data-ttu-id="f3345-102">\<message> di \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f3345-102">\<message> of \<basicHttpBinding></span></span>
<span data-ttu-id="f3345-103">Definisce le impostazioni per la sicurezza a livello di messaggio dell'oggetto [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f3345-103">Defines the settings for message-level security of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="f3345-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3345-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3345-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f3345-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f3345-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f3345-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3345-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f3345-107">Attributes</span></span>  
  
|<span data-ttu-id="f3345-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f3345-108">Attribute</span></span>|<span data-ttu-id="f3345-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3345-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3345-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="f3345-110">algorithmSuite</span></span>|<span data-ttu-id="f3345-111">Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="f3345-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="f3345-112">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, che specifica gli algoritmi e le dimensioni della chiave.</span><span class="sxs-lookup"><span data-stu-id="f3345-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="f3345-113">Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="f3345-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="f3345-114">Il valore predefinito è `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="f3345-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="f3345-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f3345-115">clientCredentialType</span></span>|<span data-ttu-id="f3345-116">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza basata sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3345-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="f3345-117">Il valore predefinito è `UserName`.</span><span class="sxs-lookup"><span data-stu-id="f3345-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f3345-118">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f3345-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f3345-119">Valore</span><span class="sxs-lookup"><span data-stu-id="f3345-119">Value</span></span>|<span data-ttu-id="f3345-120">Description</span><span class="sxs-lookup"><span data-stu-id="f3345-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f3345-121">UserName</span><span class="sxs-lookup"><span data-stu-id="f3345-121">UserName</span></span>|<span data-ttu-id="f3345-122">-Richiede che il client venga autenticato nel server con una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="f3345-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="f3345-123">Questa credenziale deve essere specificata usando [\<clientCredentials>](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="f3345-123">This credential needs to be specified using the [\<clientCredentials>](clientcredentials.md).</span></span><br /><span data-ttu-id="f3345-124">-WCF non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f3345-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="f3345-125">Pertanto, WCF impone che il trasporto sia protetto quando si utilizzano le credenziali del nome utente.</span><span class="sxs-lookup"><span data-stu-id="f3345-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="f3345-126">Per `basicHttpBinding`, questo richiede l'impostazione di un canale SSL.</span><span class="sxs-lookup"><span data-stu-id="f3345-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="f3345-127">Certificato</span><span class="sxs-lookup"><span data-stu-id="f3345-127">Certificate</span></span>|<span data-ttu-id="f3345-128">Richiede che l'autenticazione del client sul server avvenga mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="f3345-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="f3345-129">La credenziale client in questo caso deve essere specificata usando [\<clientCredentials>](clientcredentials.md) e [\<clientCertificate>](clientcertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="f3345-129">The client credential in this case needs to be specified using [\<clientCredentials>](clientcredentials.md) and the [\<clientCertificate>](clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="f3345-130">Inoltre, quando si usa la modalità di sicurezza del messaggio, è necessario eseguire il provisioning del client con il certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="f3345-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="f3345-131">In questo caso la credenziale del servizio deve essere specificata tramite <xref:System.ServiceModel.Description.ClientCredentials> `ClientCredentials` l'elemento Class o Behavior e specificando il certificato di servizio utilizzando [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="f3345-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3345-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f3345-132">Child Elements</span></span>  
 <span data-ttu-id="f3345-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="f3345-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3345-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f3345-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f3345-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3345-135">Element</span></span>|<span data-ttu-id="f3345-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3345-136">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="f3345-137">Definisce le funzionalità di sicurezza per [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f3345-137">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3345-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3345-138">Example</span></span>  
 <span data-ttu-id="f3345-139">In questo esempio viene dimostrato come implementare un'applicazione che usa basicHttpBinding e la sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3345-139">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="f3345-140">Nel seguente esempio di configurazione di un servizio, la definizione dell'endpoint specifica basicHttpBinding e fa riferimento a una configurazione di associazione denominata `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="f3345-140">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="f3345-141">Il certificato usato dal servizio per l'autenticazione con il client è impostato nella sezione `behaviors` del file di configurazione sotto l'elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="f3345-141">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="f3345-142">Anche la modalità di convalida applicata al certificato usato dal servizio per l'autenticazione con il client è impostata nella sezione `behaviors` del file di configurazione sotto l'elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="f3345-142">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="f3345-143">Gli stessi dettagli sull'associazione e la sicurezza sono specificati nel file di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="f3345-143">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3345-144">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f3345-144">See also</span></span>

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [<span data-ttu-id="f3345-145">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="f3345-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f3345-146">Binding</span><span class="sxs-lookup"><span data-stu-id="f3345-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f3345-147">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f3345-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f3345-148">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f3345-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
