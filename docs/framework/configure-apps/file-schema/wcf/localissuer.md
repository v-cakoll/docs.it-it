---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9118d1462d4790bb457fc8dc2f7c74b6e69de43a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749114"
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="27a93-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="27a93-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="27a93-103">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="27a93-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="27a93-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27a93-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="27a93-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="27a93-105">\<behaviors></span></span>  
<span data-ttu-id="27a93-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="27a93-106">endpointBehaviors section</span></span>  
<span data-ttu-id="27a93-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="27a93-107">\<behavior></span></span>  
<span data-ttu-id="27a93-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="27a93-108">\<clientCredentials></span></span>  
<span data-ttu-id="27a93-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="27a93-109">\<issuedToken></span></span>  
<span data-ttu-id="27a93-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="27a93-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a93-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27a93-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27a93-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="27a93-112">Attributes and Elements</span></span>  
 <span data-ttu-id="27a93-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="27a93-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27a93-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="27a93-114">Attributes</span></span>  
  
|<span data-ttu-id="27a93-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="27a93-115">Attribute</span></span>|<span data-ttu-id="27a93-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27a93-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27a93-117">address</span><span class="sxs-lookup"><span data-stu-id="27a93-117">address</span></span>|<span data-ttu-id="27a93-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="27a93-118">Required string.</span></span> <span data-ttu-id="27a93-119">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="27a93-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="27a93-120">associazione</span><span class="sxs-lookup"><span data-stu-id="27a93-120">binding</span></span>|<span data-ttu-id="27a93-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="27a93-121">Optional string.</span></span> <span data-ttu-id="27a93-122">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="27a93-122">One of the system-provided bindings.</span></span> <span data-ttu-id="27a93-123">Per un elenco, vedere [associazioni fornite dal sistema](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="27a93-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="27a93-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="27a93-124">bindingConfiguration</span></span>|<span data-ttu-id="27a93-125">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="27a93-125">Optional string.</span></span> <span data-ttu-id="27a93-126">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27a93-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27a93-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27a93-127">Child Elements</span></span>  
  
|<span data-ttu-id="27a93-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="27a93-128">Element</span></span>|<span data-ttu-id="27a93-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27a93-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27a93-130">\<identità ></span><span class="sxs-lookup"><span data-stu-id="27a93-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="27a93-131">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="27a93-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="27a93-132">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="27a93-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="27a93-133">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="27a93-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="27a93-134">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="27a93-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27a93-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27a93-135">Parent Elements</span></span>  
  
|<span data-ttu-id="27a93-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="27a93-136">Element</span></span>|<span data-ttu-id="27a93-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27a93-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27a93-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="27a93-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="27a93-139">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="27a93-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27a93-140">Note</span><span class="sxs-lookup"><span data-stu-id="27a93-140">Remarks</span></span>  
 <span data-ttu-id="27a93-141">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="27a93-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="27a93-142">Quando il <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce un URL per il servizio token di sicurezza o quando è l'indirizzo dell'emittente di un'associazione federativa http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous o `null`, il canale del client Windows Communication Foundation (WCF) utilizza i valori specificati dal `address`e `binding` per comunicare con il servizio token di sicurezza per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="27a93-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="27a93-143">Per ulteriori informazioni sulla configurazione di un emittente locale, vedere [procedura: configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="27a93-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27a93-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="27a93-144">Example</span></span>  
 <span data-ttu-id="27a93-145">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="27a93-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27a93-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27a93-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="27a93-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="27a93-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="27a93-148">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="27a93-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="27a93-149">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="27a93-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="27a93-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="27a93-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="27a93-151">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="27a93-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="27a93-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="27a93-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="27a93-153">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="27a93-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="27a93-154">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="27a93-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="27a93-155">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="27a93-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
