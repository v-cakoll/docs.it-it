---
title: Protezione dei messaggi tramite client con tipo di credenziale UserName
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 3dd21268d4ea7dc59c74889ac94dc86678e91865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184644"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="648c8-102">Protezione dei messaggi tramite client con tipo di credenziale UserName</span><span class="sxs-lookup"><span data-stu-id="648c8-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="648c8-103">Nella figura seguente viene illustrato un servizio Windows Communication Foundation (WCF) e un client protetto tramite la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="648c8-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="648c8-104">Il servizio viene autenticato con un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="648c8-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="648c8-105">Il client esegue l'autenticazione utilizzando un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="648c8-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="648c8-106">Per un'applicazione di esempio, vedere [Nome utente di sicurezza dei messaggi](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="648c8-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="648c8-107">![Sicurezza dei messaggi con l'autenticazione del nome utente](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="648c8-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="648c8-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="648c8-108">Characteristic</span></span>|<span data-ttu-id="648c8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="648c8-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="648c8-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="648c8-110">Security Mode</span></span>|<span data-ttu-id="648c8-111">Message</span><span class="sxs-lookup"><span data-stu-id="648c8-111">Message</span></span>|  
|<span data-ttu-id="648c8-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="648c8-112">Interoperability</span></span>|<span data-ttu-id="648c8-113">Solo Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="648c8-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="648c8-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="648c8-114">Authentication (Server)</span></span>|<span data-ttu-id="648c8-115">La negoziazione iniziale richiede l'autenticazione server</span><span class="sxs-lookup"><span data-stu-id="648c8-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="648c8-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="648c8-116">Authentication (Client)</span></span>|<span data-ttu-id="648c8-117">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="648c8-117">User name/password</span></span>|  
|<span data-ttu-id="648c8-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="648c8-118">Integrity</span></span>|<span data-ttu-id="648c8-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="648c8-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="648c8-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="648c8-120">Confidentiality</span></span>|<span data-ttu-id="648c8-121">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="648c8-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="648c8-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="648c8-122">Transport</span></span>|<span data-ttu-id="648c8-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="648c8-123">HTTP</span></span>|  
|<span data-ttu-id="648c8-124">Associazione</span><span class="sxs-lookup"><span data-stu-id="648c8-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="648c8-125">Service</span><span class="sxs-lookup"><span data-stu-id="648c8-125">Service</span></span>  
 <span data-ttu-id="648c8-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="648c8-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="648c8-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="648c8-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="648c8-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="648c8-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="648c8-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="648c8-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="648c8-130">Codice</span><span class="sxs-lookup"><span data-stu-id="648c8-130">Code</span></span>  
 <span data-ttu-id="648c8-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="648c8-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="648c8-132">Configurazione</span><span class="sxs-lookup"><span data-stu-id="648c8-132">Configuration</span></span>  
 <span data-ttu-id="648c8-133">Invece del codice, è possibile utilizzare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="648c8-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="648c8-134">Client</span><span class="sxs-lookup"><span data-stu-id="648c8-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="648c8-135">Codice</span><span class="sxs-lookup"><span data-stu-id="648c8-135">Code</span></span>  
 <span data-ttu-id="648c8-136">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="648c8-136">The following code creates the client.</span></span> <span data-ttu-id="648c8-137">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`.</span><span class="sxs-lookup"><span data-stu-id="648c8-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="648c8-138">Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).</span><span class="sxs-lookup"><span data-stu-id="648c8-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="648c8-139">Il codice per restituire il nome utente e la password non è riportato qui perché deve essere eseguito a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="648c8-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="648c8-140">Utilizzare, ad esempio, una finestra di dialogo Windows Form per chiedere i dati all'utente.</span><span class="sxs-lookup"><span data-stu-id="648c8-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="648c8-141">Configurazione</span><span class="sxs-lookup"><span data-stu-id="648c8-141">Configuration</span></span>  
 <span data-ttu-id="648c8-142">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="648c8-142">The following code configures the client.</span></span> <span data-ttu-id="648c8-143">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`.</span><span class="sxs-lookup"><span data-stu-id="648c8-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="648c8-144">Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).</span><span class="sxs-lookup"><span data-stu-id="648c8-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="648c8-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="648c8-145">See also</span></span>

- [<span data-ttu-id="648c8-146">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="648c8-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="648c8-147">Sicurezza dei messaggi tramite nome utente</span><span class="sxs-lookup"><span data-stu-id="648c8-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)
- [<span data-ttu-id="648c8-148">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="648c8-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="648c8-149">\<identità></span><span class="sxs-lookup"><span data-stu-id="648c8-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
- <span data-ttu-id="648c8-150">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="648c8-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
