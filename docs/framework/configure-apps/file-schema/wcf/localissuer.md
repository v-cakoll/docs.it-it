---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 893ac2cb0e6c54beae68e2607c31564baafd95fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527549"
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="7034d-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="7034d-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="7034d-103">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7034d-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="7034d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7034d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7034d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7034d-105">\<behaviors></span></span>  
<span data-ttu-id="7034d-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="7034d-106">endpointBehaviors section</span></span>  
<span data-ttu-id="7034d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7034d-107">\<behavior></span></span>  
<span data-ttu-id="7034d-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7034d-108">\<clientCredentials></span></span>  
<span data-ttu-id="7034d-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7034d-109">\<issuedToken></span></span>  
<span data-ttu-id="7034d-110">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="7034d-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7034d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7034d-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7034d-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7034d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7034d-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7034d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7034d-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7034d-114">Attributes</span></span>  
  
|<span data-ttu-id="7034d-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="7034d-115">Attribute</span></span>|<span data-ttu-id="7034d-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7034d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7034d-117">address</span><span class="sxs-lookup"><span data-stu-id="7034d-117">address</span></span>|<span data-ttu-id="7034d-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="7034d-118">Required string.</span></span> <span data-ttu-id="7034d-119">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7034d-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="7034d-120">associazione</span><span class="sxs-lookup"><span data-stu-id="7034d-120">binding</span></span>|<span data-ttu-id="7034d-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7034d-121">Optional string.</span></span> <span data-ttu-id="7034d-122">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7034d-122">One of the system-provided bindings.</span></span> <span data-ttu-id="7034d-123">Per un elenco, vedere [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="7034d-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="7034d-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7034d-124">bindingConfiguration</span></span>|<span data-ttu-id="7034d-125">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7034d-125">Optional string.</span></span> <span data-ttu-id="7034d-126">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7034d-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7034d-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7034d-127">Child Elements</span></span>  
  
|<span data-ttu-id="7034d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="7034d-128">Element</span></span>|<span data-ttu-id="7034d-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7034d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7034d-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="7034d-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="7034d-131">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7034d-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="7034d-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="7034d-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="7034d-133">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7034d-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="7034d-134">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="7034d-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7034d-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7034d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7034d-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7034d-136">Element</span></span>|<span data-ttu-id="7034d-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7034d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7034d-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7034d-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="7034d-139">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7034d-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7034d-140">Note</span><span class="sxs-lookup"><span data-stu-id="7034d-140">Remarks</span></span>  
 <span data-ttu-id="7034d-141">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7034d-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="7034d-142">Quando la <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce un URL per il servizio token di sicurezza o quando è l'indirizzo dell'emittente di un'associazione federata `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, il canale del client Windows Communication Foundation (WCF) usa i valori specificati da `address`e `binding` per comunicare con il servizio token di sicurezza per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="7034d-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="7034d-143">Per altre informazioni su come configurare un emittente locale, vedere [come: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="7034d-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7034d-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7034d-144">Example</span></span>  
 <span data-ttu-id="7034d-145">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="7034d-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7034d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7034d-146">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="7034d-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7034d-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7034d-148">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="7034d-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7034d-149">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="7034d-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7034d-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7034d-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7034d-151">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7034d-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7034d-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="7034d-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7034d-153">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7034d-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="7034d-154">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="7034d-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7034d-155">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7034d-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
