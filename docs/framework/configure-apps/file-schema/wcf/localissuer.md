---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122876"
---
# <a name="localissuer"></a><span data-ttu-id="7683d-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="7683d-101">\<localIssuer></span></span>
<span data-ttu-id="7683d-102">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7683d-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="7683d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7683d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7683d-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7683d-104">\<behaviors></span></span>  
<span data-ttu-id="7683d-105">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="7683d-105">endpointBehaviors section</span></span>  
<span data-ttu-id="7683d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7683d-106">\<behavior></span></span>  
<span data-ttu-id="7683d-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7683d-107">\<clientCredentials></span></span>  
<span data-ttu-id="7683d-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7683d-108">\<issuedToken></span></span>  
<span data-ttu-id="7683d-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="7683d-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7683d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7683d-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7683d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7683d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7683d-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7683d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7683d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7683d-113">Attributes</span></span>  
  
|<span data-ttu-id="7683d-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7683d-114">Attribute</span></span>|<span data-ttu-id="7683d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7683d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7683d-116">indirizzo</span><span class="sxs-lookup"><span data-stu-id="7683d-116">address</span></span>|<span data-ttu-id="7683d-117">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="7683d-117">Required string.</span></span> <span data-ttu-id="7683d-118">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7683d-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="7683d-119">binding</span><span class="sxs-lookup"><span data-stu-id="7683d-119">binding</span></span>|<span data-ttu-id="7683d-120">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7683d-120">Optional string.</span></span> <span data-ttu-id="7683d-121">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7683d-121">One of the system-provided bindings.</span></span> <span data-ttu-id="7683d-122">Per un elenco, vedere [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="7683d-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="7683d-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7683d-123">bindingConfiguration</span></span>|<span data-ttu-id="7683d-124">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7683d-124">Optional string.</span></span> <span data-ttu-id="7683d-125">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7683d-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7683d-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7683d-126">Child Elements</span></span>  
  
|<span data-ttu-id="7683d-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="7683d-127">Element</span></span>|<span data-ttu-id="7683d-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7683d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7683d-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="7683d-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="7683d-130">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7683d-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="7683d-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="7683d-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="7683d-132">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7683d-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="7683d-133">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="7683d-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7683d-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7683d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="7683d-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="7683d-135">Element</span></span>|<span data-ttu-id="7683d-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7683d-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7683d-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7683d-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="7683d-138">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7683d-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7683d-139">Note</span><span class="sxs-lookup"><span data-stu-id="7683d-139">Remarks</span></span>  
 <span data-ttu-id="7683d-140">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7683d-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="7683d-141">Quando la <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce un URL per il servizio token di sicurezza o quando è l'indirizzo dell'emittente di un'associazione federata `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, il canale del client Windows Communication Foundation (WCF) usa i valori specificati da `address`e `binding` per comunicare con il servizio token di sicurezza per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="7683d-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="7683d-142">Per altre informazioni su come configurare un emittente locale, vedere [come: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="7683d-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7683d-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="7683d-143">Example</span></span>  
 <span data-ttu-id="7683d-144">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="7683d-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7683d-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7683d-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="7683d-146">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7683d-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7683d-147">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="7683d-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7683d-148">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="7683d-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7683d-149">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7683d-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7683d-150">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7683d-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7683d-151">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="7683d-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7683d-152">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7683d-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="7683d-153">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="7683d-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7683d-154">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7683d-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
