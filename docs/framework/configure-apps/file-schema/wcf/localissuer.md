---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8836d9e57dd7c4d9cfdc20c5e4856e384e6d67b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="163f1-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="163f1-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="163f1-103">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="163f1-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="163f1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="163f1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="163f1-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="163f1-105">\<behaviors></span></span>  
<span data-ttu-id="163f1-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="163f1-106">endpointBehaviors section</span></span>  
<span data-ttu-id="163f1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="163f1-107">\<behavior></span></span>  
<span data-ttu-id="163f1-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="163f1-108">\<clientCredentials></span></span>  
<span data-ttu-id="163f1-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="163f1-109">\<issuedToken></span></span>  
<span data-ttu-id="163f1-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="163f1-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163f1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="163f1-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="163f1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="163f1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="163f1-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="163f1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="163f1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="163f1-114">Attributes</span></span>  
  
|<span data-ttu-id="163f1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="163f1-115">Attribute</span></span>|<span data-ttu-id="163f1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="163f1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="163f1-117">address</span><span class="sxs-lookup"><span data-stu-id="163f1-117">address</span></span>|<span data-ttu-id="163f1-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="163f1-118">Required string.</span></span> <span data-ttu-id="163f1-119">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="163f1-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="163f1-120">associazione</span><span class="sxs-lookup"><span data-stu-id="163f1-120">binding</span></span>|<span data-ttu-id="163f1-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="163f1-121">Optional string.</span></span> <span data-ttu-id="163f1-122">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="163f1-122">One of the system-provided bindings.</span></span> <span data-ttu-id="163f1-123">Per un elenco, vedere [associazioni fornite dal sistema](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="163f1-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="163f1-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="163f1-124">bindingConfiguration</span></span>|<span data-ttu-id="163f1-125">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="163f1-125">Optional string.</span></span> <span data-ttu-id="163f1-126">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="163f1-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="163f1-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="163f1-127">Child Elements</span></span>  
  
|<span data-ttu-id="163f1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="163f1-128">Element</span></span>|<span data-ttu-id="163f1-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="163f1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="163f1-130">\<identità ></span><span class="sxs-lookup"><span data-stu-id="163f1-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="163f1-131">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="163f1-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="163f1-132">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="163f1-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="163f1-133">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="163f1-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="163f1-134">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="163f1-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="163f1-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="163f1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="163f1-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="163f1-136">Element</span></span>|<span data-ttu-id="163f1-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="163f1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="163f1-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="163f1-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="163f1-139">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="163f1-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="163f1-140">Note</span><span class="sxs-lookup"><span data-stu-id="163f1-140">Remarks</span></span>  
 <span data-ttu-id="163f1-141">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="163f1-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="163f1-142">Se <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce un URL per il servizio token di sicurezza o se l'indirizzo dell'emittente di un'associazione federativa è http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous o `null`, il canale [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] del client usa il valore specificato da `address` e `binding` per comunicare con il servizio token di sicurezza e ottenere il token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="163f1-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="163f1-143">Per ulteriori informazioni sulla configurazione di un emittente locale, vedere [procedura: configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="163f1-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="163f1-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="163f1-144">Example</span></span>  
 <span data-ttu-id="163f1-145">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="163f1-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="163f1-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="163f1-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="163f1-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="163f1-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="163f1-148">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="163f1-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="163f1-149">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="163f1-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="163f1-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="163f1-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="163f1-151">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="163f1-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="163f1-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="163f1-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="163f1-153">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="163f1-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="163f1-154">Procedura: creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="163f1-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="163f1-155">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="163f1-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
