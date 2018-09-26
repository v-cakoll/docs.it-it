---
title: Protezione dei messaggi tramite client con tipo di credenziale UserName
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
author: BrucePerlerMS
ms.openlocfilehash: e26665b76518e33de266c73600e1da918eb2a51d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47203498"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="e2c63-102">Protezione dei messaggi tramite client con tipo di credenziale UserName</span><span class="sxs-lookup"><span data-stu-id="e2c63-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="e2c63-103">La figura seguente mostra un servizio Windows Communication Foundation (WCF) e un client protetto usando la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2c63-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="e2c63-104">Il servizio viene autenticato con un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="e2c63-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="e2c63-105">Il client esegue l'autenticazione utilizzando un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="e2c63-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="e2c63-106">Per un'applicazione di esempio, vedere [messaggi tramite nome utente sicurezza](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="e2c63-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="e2c63-107">![Sicurezza dei messaggi con l'autenticazione di nome utente](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="e2c63-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="e2c63-108">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="e2c63-108">Characteristic</span></span>|<span data-ttu-id="e2c63-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c63-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e2c63-110">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e2c63-110">Security Mode</span></span>|<span data-ttu-id="e2c63-111">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e2c63-111">Message</span></span>|  
|<span data-ttu-id="e2c63-112">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="e2c63-112">Interoperability</span></span>|<span data-ttu-id="e2c63-113">Windows Communication Foundation (WCF) solo</span><span class="sxs-lookup"><span data-stu-id="e2c63-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="e2c63-114">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="e2c63-114">Authentication (Server)</span></span>|<span data-ttu-id="e2c63-115">La negoziazione iniziale richiede l'autenticazione server</span><span class="sxs-lookup"><span data-stu-id="e2c63-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="e2c63-116">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="e2c63-116">Authentication (Client)</span></span>|<span data-ttu-id="e2c63-117">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="e2c63-117">User name/password</span></span>|  
|<span data-ttu-id="e2c63-118">Integrità</span><span class="sxs-lookup"><span data-stu-id="e2c63-118">Integrity</span></span>|<span data-ttu-id="e2c63-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="e2c63-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="e2c63-120">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="e2c63-120">Confidentiality</span></span>|<span data-ttu-id="e2c63-121">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="e2c63-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="e2c63-122">Trasporto</span><span class="sxs-lookup"><span data-stu-id="e2c63-122">Transport</span></span>|<span data-ttu-id="e2c63-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="e2c63-123">HTTP</span></span>|  
|<span data-ttu-id="e2c63-124">Binding</span><span class="sxs-lookup"><span data-stu-id="e2c63-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="e2c63-125">Servizio</span><span class="sxs-lookup"><span data-stu-id="e2c63-125">Service</span></span>  
 <span data-ttu-id="e2c63-126">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="e2c63-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e2c63-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2c63-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="e2c63-128">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="e2c63-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="e2c63-129">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="e2c63-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e2c63-130">Codice</span><span class="sxs-lookup"><span data-stu-id="e2c63-130">Code</span></span>  
 <span data-ttu-id="e2c63-131">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2c63-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="e2c63-132">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2c63-132">Configuration</span></span>  
 <span data-ttu-id="e2c63-133">Invece del codice, è possibile utilizzare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="e2c63-133">The following configuration can be used instead of the code:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="e2c63-134">Client</span><span class="sxs-lookup"><span data-stu-id="e2c63-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="e2c63-135">Codice</span><span class="sxs-lookup"><span data-stu-id="e2c63-135">Code</span></span>  
 <span data-ttu-id="e2c63-136">Il codice seguente crea il client.</span><span class="sxs-lookup"><span data-stu-id="e2c63-136">The following code creates the client.</span></span> <span data-ttu-id="e2c63-137">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`.</span><span class="sxs-lookup"><span data-stu-id="e2c63-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="e2c63-138">Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).</span><span class="sxs-lookup"><span data-stu-id="e2c63-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="e2c63-139">Il codice per restituire il nome utente e la password non è riportato qui perché deve essere eseguito a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c63-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="e2c63-140">Utilizzare, ad esempio, una finestra di dialogo Windows Form per chiedere i dati all'utente.</span><span class="sxs-lookup"><span data-stu-id="e2c63-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="e2c63-141">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2c63-141">Configuration</span></span>  
 <span data-ttu-id="e2c63-142">Nel codice seguente viene configurato il client.</span><span class="sxs-lookup"><span data-stu-id="e2c63-142">The following code configures the client.</span></span> <span data-ttu-id="e2c63-143">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `UserName`.</span><span class="sxs-lookup"><span data-stu-id="e2c63-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="e2c63-144">Il nome utente e la password possono essere specificati solo tramite codice (non è configurabile).</span><span class="sxs-lookup"><span data-stu-id="e2c63-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2c63-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2c63-145">See Also</span></span>  
 [<span data-ttu-id="e2c63-146">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e2c63-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="e2c63-147">Sicurezza dei messaggi tramite nome utente</span><span class="sxs-lookup"><span data-stu-id="e2c63-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="e2c63-148">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="e2c63-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e2c63-149">\<identità ></span><span class="sxs-lookup"><span data-stu-id="e2c63-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="e2c63-150">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="e2c63-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
