---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397859"
---
# <a name="localissuer"></a><span data-ttu-id="7bf58-101">\<> localIssuer</span><span class="sxs-lookup"><span data-stu-id="7bf58-101">\<localIssuer></span></span>
<span data-ttu-id="7bf58-102">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7bf58-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="7bf58-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7bf58-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7bf58-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7bf58-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7bf58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7bf58-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="7bf58-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedToken**](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="7bf58-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="7bf58-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> localIssuer**</span><span class="sxs-lookup"><span data-stu-id="7bf58-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf58-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bf58-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bf58-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7bf58-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7bf58-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7bf58-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bf58-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7bf58-114">Attributes</span></span>  
  
|<span data-ttu-id="7bf58-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="7bf58-115">Attribute</span></span>|<span data-ttu-id="7bf58-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bf58-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7bf58-117">Address</span><span class="sxs-lookup"><span data-stu-id="7bf58-117">address</span></span>|<span data-ttu-id="7bf58-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="7bf58-118">Required string.</span></span> <span data-ttu-id="7bf58-119">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7bf58-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="7bf58-120">binding</span><span class="sxs-lookup"><span data-stu-id="7bf58-120">binding</span></span>|<span data-ttu-id="7bf58-121">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7bf58-121">Optional string.</span></span> <span data-ttu-id="7bf58-122">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7bf58-122">One of the system-provided bindings.</span></span> <span data-ttu-id="7bf58-123">Per un elenco, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="7bf58-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="7bf58-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7bf58-124">bindingConfiguration</span></span>|<span data-ttu-id="7bf58-125">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7bf58-125">Optional string.</span></span> <span data-ttu-id="7bf58-126">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7bf58-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bf58-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7bf58-127">Child Elements</span></span>  
  
|<span data-ttu-id="7bf58-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="7bf58-128">Element</span></span>|<span data-ttu-id="7bf58-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bf58-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bf58-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="7bf58-130">\<identity></span></span>](identity.md)|<span data-ttu-id="7bf58-131">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7bf58-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="7bf58-132">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="7bf58-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="7bf58-133">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7bf58-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="7bf58-134">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="7bf58-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7bf58-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7bf58-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7bf58-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7bf58-136">Element</span></span>|<span data-ttu-id="7bf58-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bf58-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bf58-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7bf58-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="7bf58-139">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7bf58-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bf58-140">Note</span><span class="sxs-lookup"><span data-stu-id="7bf58-140">Remarks</span></span>  
 <span data-ttu-id="7bf58-141">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7bf58-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="7bf58-142">Quando non fornisce un URL per il servizio token di sicurezza o quando l'indirizzo dell'emittente di un'associazione federata è `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, il canale Windows Communication Foundation (WCF) del client usa i valori specificati da <xref:System.ServiceModel.WSFederationHttpBinding> `address` e`binding` per comunicare con il servizio token di servizio per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="7bf58-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="7bf58-143">Per ulteriori informazioni sulla configurazione di un'autorità emittente locale, [vedere Procedura: Configurare un'autorità emittente](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)locale.</span><span class="sxs-lookup"><span data-stu-id="7bf58-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bf58-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bf58-144">Example</span></span>  
 <span data-ttu-id="7bf58-145">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="7bf58-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7bf58-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bf58-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="7bf58-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7bf58-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7bf58-148">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="7bf58-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7bf58-149">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="7bf58-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7bf58-150">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7bf58-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7bf58-151">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7bf58-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7bf58-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="7bf58-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7bf58-153">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7bf58-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7bf58-154">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="7bf58-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7bf58-155">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7bf58-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
