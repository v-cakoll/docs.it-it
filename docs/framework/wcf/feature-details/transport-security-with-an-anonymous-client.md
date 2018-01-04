---
title: Protezione del trasporto con un client anonimo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 97a3c9c618fc7d6c96deba0b72e25ef36c5785e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="b9208-102">Protezione del trasporto con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="b9208-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="b9208-103">In questo scenario [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene utilizzata la protezione del trasporto (HTTPS) per garantirne la riservatezza e l'integrità.</span><span class="sxs-lookup"><span data-stu-id="b9208-103">This [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="b9208-104">È necessario che il server sia autenticato con un certificato SSL (Secure Sockets Layer) e che il client ritenga attendibile il certificato del server.</span><span class="sxs-lookup"><span data-stu-id="b9208-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="b9208-105">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="b9208-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="b9208-106">Per un'applicazione di esempio, vedere [la sicurezza del trasporto WS](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="b9208-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b9208-107">sicurezza del trasporto, vedere [Cenni preliminari sulla sicurezza di trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9208-107"> transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b9208-108">utilizzo di un certificato con un servizio, vedere [utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) e [procedura: configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="b9208-108"> using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="b9208-109">![Utilizzando la sicurezza del trasporto con un client anonimo](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="b9208-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="b9208-110">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="b9208-110">Characteristic</span></span>|<span data-ttu-id="b9208-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9208-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b9208-112">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b9208-112">Security Mode</span></span>|<span data-ttu-id="b9208-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b9208-113">Transport</span></span>|  
|<span data-ttu-id="b9208-114">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b9208-114">Interoperability</span></span>|<span data-ttu-id="b9208-115">Con i servizi Web e i client esistenti</span><span class="sxs-lookup"><span data-stu-id="b9208-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="b9208-116">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="b9208-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="b9208-117">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="b9208-117">Authentication (Client)</span></span>|<span data-ttu-id="b9208-118">Yes</span><span class="sxs-lookup"><span data-stu-id="b9208-118">Yes</span></span><br /><br /> <span data-ttu-id="b9208-119">A livello di applicazione (nessun supporto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b9208-119">Application level (no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] support)</span></span>|  
|<span data-ttu-id="b9208-120">Integrità</span><span class="sxs-lookup"><span data-stu-id="b9208-120">Integrity</span></span>|<span data-ttu-id="b9208-121">Sì</span><span class="sxs-lookup"><span data-stu-id="b9208-121">Yes</span></span>|  
|<span data-ttu-id="b9208-122">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="b9208-122">Confidentiality</span></span>|<span data-ttu-id="b9208-123">Sì</span><span class="sxs-lookup"><span data-stu-id="b9208-123">Yes</span></span>|  
|<span data-ttu-id="b9208-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b9208-124">Transport</span></span>|<span data-ttu-id="b9208-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b9208-125">HTTPS</span></span>|  
|<span data-ttu-id="b9208-126">Binding</span><span class="sxs-lookup"><span data-stu-id="b9208-126">Binding</span></span>|<span data-ttu-id="b9208-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="b9208-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="b9208-128">Service</span><span class="sxs-lookup"><span data-stu-id="b9208-128">Service</span></span>  
 <span data-ttu-id="b9208-129">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b9208-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b9208-130">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9208-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b9208-131">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9208-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="b9208-132">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="b9208-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b9208-133">Codice</span><span class="sxs-lookup"><span data-stu-id="b9208-133">Code</span></span>  
 <span data-ttu-id="b9208-134">Nel codice seguente viene illustrato come creare un endpoint utilizzando la protezione del trasporto:</span><span class="sxs-lookup"><span data-stu-id="b9208-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="b9208-135">Configurazione</span><span class="sxs-lookup"><span data-stu-id="b9208-135">Configuration</span></span>  
 <span data-ttu-id="b9208-136">Nel codice seguente viene impostato lo stesso endpoint utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9208-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="b9208-137">Il client non viene autenticato da alcun meccanismo ed è pertanto anonimo.</span><span class="sxs-lookup"><span data-stu-id="b9208-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="b9208-138">Client</span><span class="sxs-lookup"><span data-stu-id="b9208-138">Client</span></span>  
 <span data-ttu-id="b9208-139">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b9208-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b9208-140">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9208-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b9208-141">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="b9208-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="b9208-142">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="b9208-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="b9208-143">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="b9208-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="b9208-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b9208-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="b9208-145">Codice</span><span class="sxs-lookup"><span data-stu-id="b9208-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="b9208-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="b9208-146">Configuration</span></span>  
 <span data-ttu-id="b9208-147">Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice.</span><span class="sxs-lookup"><span data-stu-id="b9208-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9208-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9208-148">See Also</span></span>  
 [<span data-ttu-id="b9208-149">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="b9208-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="b9208-150">Sicurezza del trasporto WS</span><span class="sxs-lookup"><span data-stu-id="b9208-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="b9208-151">Panoramica della sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="b9208-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="b9208-152">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="b9208-152">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
