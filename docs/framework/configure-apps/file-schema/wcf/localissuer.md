---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 4ec5a99139112ae600c1c2bc44feb6d3f62da1e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931731"
---
# <a name="localissuer"></a><span data-ttu-id="0a22b-101">\<> localIssuer</span><span class="sxs-lookup"><span data-stu-id="0a22b-101">\<localIssuer></span></span>
<span data-ttu-id="0a22b-102">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0a22b-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="0a22b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0a22b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a22b-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="0a22b-104">\<behaviors></span></span>  
<span data-ttu-id="0a22b-105">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="0a22b-105">endpointBehaviors section</span></span>  
<span data-ttu-id="0a22b-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="0a22b-106">\<behavior></span></span>  
<span data-ttu-id="0a22b-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0a22b-107">\<clientCredentials></span></span>  
<span data-ttu-id="0a22b-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="0a22b-108">\<issuedToken></span></span>  
<span data-ttu-id="0a22b-109">\<> localIssuer</span><span class="sxs-lookup"><span data-stu-id="0a22b-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a22b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a22b-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a22b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0a22b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a22b-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0a22b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a22b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0a22b-113">Attributes</span></span>  
  
|<span data-ttu-id="0a22b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0a22b-114">Attribute</span></span>|<span data-ttu-id="0a22b-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0a22b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a22b-116">Address</span><span class="sxs-lookup"><span data-stu-id="0a22b-116">address</span></span>|<span data-ttu-id="0a22b-117">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0a22b-117">Required string.</span></span> <span data-ttu-id="0a22b-118">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="0a22b-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="0a22b-119">binding</span><span class="sxs-lookup"><span data-stu-id="0a22b-119">binding</span></span>|<span data-ttu-id="0a22b-120">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0a22b-120">Optional string.</span></span> <span data-ttu-id="0a22b-121">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="0a22b-121">One of the system-provided bindings.</span></span> <span data-ttu-id="0a22b-122">Per un elenco, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="0a22b-122">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="0a22b-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a22b-123">bindingConfiguration</span></span>|<span data-ttu-id="0a22b-124">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0a22b-124">Optional string.</span></span> <span data-ttu-id="0a22b-125">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a22b-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a22b-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0a22b-126">Child Elements</span></span>  
  
|<span data-ttu-id="0a22b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a22b-127">Element</span></span>|<span data-ttu-id="0a22b-128">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0a22b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a22b-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="0a22b-129">\<identity></span></span>](identity.md)|<span data-ttu-id="0a22b-130">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="0a22b-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="0a22b-131">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="0a22b-131">\<headers></span></span>](headers-element.md)|<span data-ttu-id="0a22b-132">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="0a22b-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="0a22b-133">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="0a22b-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a22b-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0a22b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0a22b-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a22b-135">Element</span></span>|<span data-ttu-id="0a22b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a22b-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a22b-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="0a22b-137">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="0a22b-138">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="0a22b-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a22b-139">Note</span><span class="sxs-lookup"><span data-stu-id="0a22b-139">Remarks</span></span>  
 <span data-ttu-id="0a22b-140">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0a22b-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="0a22b-141">Quando non fornisce un URL per il servizio token di sicurezza o quando l'indirizzo dell'emittente di un'associazione federata è `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, il canale Windows Communication Foundation (WCF) del client usa i valori specificati da <xref:System.ServiceModel.WSFederationHttpBinding> `address` e`binding` per comunicare con il servizio token di servizio per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="0a22b-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="0a22b-142">Per ulteriori informazioni sulla configurazione di un'autorità emittente locale, [vedere Procedura: Configurare un'autorità emittente](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)locale.</span><span class="sxs-lookup"><span data-stu-id="0a22b-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a22b-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a22b-143">Example</span></span>  
 <span data-ttu-id="0a22b-144">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="0a22b-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0a22b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a22b-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="0a22b-146">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0a22b-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0a22b-147">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="0a22b-147">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0a22b-148">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="0a22b-148">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0a22b-149">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0a22b-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0a22b-150">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="0a22b-150">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0a22b-151">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="0a22b-151">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0a22b-152">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="0a22b-152">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0a22b-153">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="0a22b-153">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0a22b-154">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="0a22b-154">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
