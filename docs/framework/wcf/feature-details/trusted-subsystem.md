---
title: Sottosistema attendibile
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f5ce46b-e259-4bc9-a0b9-89d06fc9341c
ms.openlocfilehash: 4f3166b8f1e59a100f54574ab548f5dae88eb5cd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742632"
---
# <a name="trusted-subsystem"></a><span data-ttu-id="5de42-102">Sottosistema attendibile</span><span class="sxs-lookup"><span data-stu-id="5de42-102">Trusted Subsystem</span></span>
<span data-ttu-id="5de42-103">Un client accede a uno o più servizi Web distribuiti in una rete.</span><span class="sxs-lookup"><span data-stu-id="5de42-103">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="5de42-104">I servizi Web sono progettati per far sì che l'accesso alle risorse aggiuntive (ad esempio database o altri servizi Web) sia incapsulato nella logica di business del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="5de42-104">The Web services are designed so that access to additional resources (such as databases or other Web services) is encapsulated in the business logic of the Web service.</span></span> <span data-ttu-id="5de42-105">Queste risorse devono essere protette da accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="5de42-105">These resources must be protected against unauthorized access.</span></span> <span data-ttu-id="5de42-106">Nella figura seguente viene illustrato un processo di sottosistema attendibile.</span><span class="sxs-lookup"><span data-stu-id="5de42-106">The following illustration depicts a trusted subsystem process.</span></span>  
  
 <span data-ttu-id="5de42-107">![Sottosistema attendibile](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span><span class="sxs-lookup"><span data-stu-id="5de42-107">![Trusted subsystem](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span></span>  
  
 <span data-ttu-id="5de42-108">Nei passaggi seguenti viene descritto il processo di sottosistema attendibile:</span><span class="sxs-lookup"><span data-stu-id="5de42-108">The following steps describe the trusted subsystem process as illustrated:</span></span>  
  
1. <span data-ttu-id="5de42-109">Il client invia una richiesta al sottosistema attendibile, insieme alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="5de42-109">The client submits a request to the trusted subsystem, along with credentials.</span></span>  
  
2. <span data-ttu-id="5de42-110">Il sottosistema attendibile autentica e autorizza l'utente.</span><span class="sxs-lookup"><span data-stu-id="5de42-110">The trusted subsystem authenticates and authorizes the user.</span></span>  
  
3. <span data-ttu-id="5de42-111">Il sottosistema attendibile invia un messaggio di richiesta alla risorsa remota.</span><span class="sxs-lookup"><span data-stu-id="5de42-111">The trusted subsystem sends a request message to the remote resource.</span></span> <span data-ttu-id="5de42-112">La richiesta è accompagnata dalle credenziali per il sottosistema attendibile (o per l'account del servizio in cui viene eseguito il processo del sottosistema attendibile).</span><span class="sxs-lookup"><span data-stu-id="5de42-112">This request is accompanied by the credentials for the trusted subsystem (or the service account under which the trusted subsystem process is being executed).</span></span>  
  
4. <span data-ttu-id="5de42-113">La risorsa back-end autentica e autorizza il sottosistema attendibile.</span><span class="sxs-lookup"><span data-stu-id="5de42-113">The back-end resource authenticates and authorizes the trusted subsystem.</span></span> <span data-ttu-id="5de42-114">Elabora quindi la richiesta e invia una risposta al sottosistema attendibile.</span><span class="sxs-lookup"><span data-stu-id="5de42-114">It then processes the request and issues a response to the trusted subsystem.</span></span>  
  
5. <span data-ttu-id="5de42-115">Il sottosistema attendibile elabora la risposta e invia la propria risposta al client.</span><span class="sxs-lookup"><span data-stu-id="5de42-115">The trusted subsystem processes the response and issues its own response to the client.</span></span>  
  
|<span data-ttu-id="5de42-116">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="5de42-116">Characteristic</span></span>|<span data-ttu-id="5de42-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5de42-117">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5de42-118">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5de42-118">Security Mode</span></span>|<span data-ttu-id="5de42-119">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5de42-119">Message</span></span>|  
|<span data-ttu-id="5de42-120">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="5de42-120">Interoperability</span></span>|<span data-ttu-id="5de42-121">Solo Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5de42-121">Windows Communication Foundation (WCF) only.</span></span>|  
|<span data-ttu-id="5de42-122">Autenticazione (servizio)</span><span class="sxs-lookup"><span data-stu-id="5de42-122">Authentication (service)</span></span>|<span data-ttu-id="5de42-123">Il servizio del token di sicurezza autentica e autorizza i client.</span><span class="sxs-lookup"><span data-stu-id="5de42-123">Security token service authenticates and authorizes clients.</span></span>|  
|<span data-ttu-id="5de42-124">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="5de42-124">Authentication (client)</span></span>|<span data-ttu-id="5de42-125">Il sottosistema attendibile autentica il client e la risorsa autentica il servizio del sottosistema attendibile.</span><span class="sxs-lookup"><span data-stu-id="5de42-125">The trusted subsystem authenticates the client and the resource authenticates the trusted subsystem service.</span></span>|  
|<span data-ttu-id="5de42-126">Integrità</span><span class="sxs-lookup"><span data-stu-id="5de42-126">Integrity</span></span>|<span data-ttu-id="5de42-127">Sì</span><span class="sxs-lookup"><span data-stu-id="5de42-127">Yes</span></span>|  
|<span data-ttu-id="5de42-128">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="5de42-128">Confidentiality</span></span>|<span data-ttu-id="5de42-129">Sì</span><span class="sxs-lookup"><span data-stu-id="5de42-129">Yes</span></span>|  
|<span data-ttu-id="5de42-130">Transport</span><span class="sxs-lookup"><span data-stu-id="5de42-130">Transport</span></span>|<span data-ttu-id="5de42-131">HTTP tra il client e il servizio del sottosistema attendibile.</span><span class="sxs-lookup"><span data-stu-id="5de42-131">HTTP between client and the trusted subsystem service.</span></span><br /><br /> <span data-ttu-id="5de42-132">NET.TCP tra il servizio del sottosistema attendibile e la risorsa (servizio back-end).</span><span class="sxs-lookup"><span data-stu-id="5de42-132">NET.TCP between trusted subsystem service and the resource (back-end service).</span></span>|  
|<span data-ttu-id="5de42-133">Associazione</span><span class="sxs-lookup"><span data-stu-id="5de42-133">Binding</span></span>|<span data-ttu-id="5de42-134"><xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="5de42-134"><xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span></span>|  
  
## <a name="resource-back-end-service"></a><span data-ttu-id="5de42-135">Risorsa (servizio back-end)</span><span class="sxs-lookup"><span data-stu-id="5de42-135">Resource (Back-End Service)</span></span>  
  
### <a name="code"></a><span data-ttu-id="5de42-136">Codice</span><span class="sxs-lookup"><span data-stu-id="5de42-136">Code</span></span>  
 <span data-ttu-id="5de42-137">Nel codice seguente viene illustrato come creare un endpoint del servizio per la risorsa che utilizza la protezione del trasporto sul protocollo di trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="5de42-137">The following code shows how to create a service endpoint for the resource, which uses transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystemsResource#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsresource/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsResource#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsresource/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="5de42-138">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="5de42-138">Configuration</span></span>  
 <span data-ttu-id="5de42-139">Nella configurazione seguente viene impostato lo stesso endpoint che utilizza la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5de42-139">The following configuration sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.BackendService"  
               behaviorConfiguration="BackendServiceBehavior">  
        <endpoint address="net.tcp://localhost.com:8001/BackendService"  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="BackendServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, BackendService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="trusted-subsystem"></a><span data-ttu-id="5de42-140">Sottosistema attendibile</span><span class="sxs-lookup"><span data-stu-id="5de42-140">Trusted Subsystem</span></span>  
  
### <a name="code"></a><span data-ttu-id="5de42-141">Codice</span><span class="sxs-lookup"><span data-stu-id="5de42-141">Code</span></span>  
 <span data-ttu-id="5de42-142">Nel codice seguente viene illustrato come creare un endpoint del servizio per il sottosistema attendibile che utilizza la protezione del messaggio sul protocollo HTTP e un nome utente e una password per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5de42-142">The following code shows how to create a service endpoint for the trusted subsystem that uses message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystems#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#1)]
 [!code-vb[TrustedSubSystems#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#1)]  
  
 <span data-ttu-id="5de42-143">Nel codice seguente viene illustrato un servizio in un sottosistema attendibile che comunica con un servizio back-end utilizzando la protezione del trasporto sul protocollo di trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="5de42-143">The following code shows a service in a trusted subsystem that communicates with a back-end service using transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystems#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#2)]
 [!code-vb[TrustedSubSystems#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="5de42-144">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="5de42-144">Configuration</span></span>  
 <span data-ttu-id="5de42-145">Nella configurazione seguente viene impostato lo stesso endpoint che utilizza la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5de42-145">The following configuration sets up the same endpoint using configuration.</span></span> <span data-ttu-id="5de42-146">Si notino le due associazioni: una protegge il servizio ospitato nel sottosistema attendibile e l'altra comunica tra il sottosistema attendibile e il servizio back-end.</span><span class="sxs-lookup"><span data-stu-id="5de42-146">Note the two bindings: One secures the service hosted in the trusted subsystem and the other communicates between the trusted subsystem and the back-end service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.FacadeService"  
               behaviorConfiguration="FacadeServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/FacadeService"/>  
          </baseAddresses>  
        </host>  
        <endpoint address="http://localhost:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <client>  
      <endpoint name=""   
                address="net.tcp://contoso.com:8001/BackendService"  
                binding="customBinding"  
                bindingConfiguration="ClientBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
      <customBinding>  
        <binding name="ClientBinding">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="FacadeServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                storeLocation="LocalMachine"  
                                storeName="My"  
                                x509FindType="FindBySubjectName" />  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, FacadeService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="5de42-147">Client</span><span class="sxs-lookup"><span data-stu-id="5de42-147">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="5de42-148">Codice</span><span class="sxs-lookup"><span data-stu-id="5de42-148">Code</span></span>  
 <span data-ttu-id="5de42-149">Nel codice seguente viene illustrato come creare il client che comunica con il sottosistema attendibile utilizzando la protezione del messaggio sul protocollo HTTP e un nome utente e una password per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5de42-149">The following code shows how to create the client that communicates with the trusted subsystem by using message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystemsClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsclient/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsclient/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="5de42-150">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="5de42-150">Configuration</span></span>  
 <span data-ttu-id="5de42-151">Nel codice seguente viene configurato il client in modo che utilizzi la protezione del messaggio sul protocollo HTTP e un nome utente e una password per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5de42-151">The following code configures the client to use message security over the HTTP protocol and a user name and password for authentication.</span></span> <span data-ttu-id="5de42-152">Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).</span><span class="sxs-lookup"><span data-stu-id="5de42-152">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <client>  
        <endpoint name=""   
                  address="http://www.cohowinery.com:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientUserNameBehavior"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientUserNameBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5de42-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de42-153">See also</span></span>

- [<span data-ttu-id="5de42-154">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="5de42-154">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="5de42-155">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5de42-155">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
