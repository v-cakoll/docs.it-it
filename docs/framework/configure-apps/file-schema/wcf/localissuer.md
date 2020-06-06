---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397859"
---
# \<localIssuer>
<span data-ttu-id="37191-101">Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="37191-101">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="37191-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37191-102">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37191-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37191-103">Attributes and Elements</span></span>  
 <span data-ttu-id="37191-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37191-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37191-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="37191-105">Attributes</span></span>  
  
|<span data-ttu-id="37191-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="37191-106">Attribute</span></span>|<span data-ttu-id="37191-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37191-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37191-108">address</span><span class="sxs-lookup"><span data-stu-id="37191-108">address</span></span>|<span data-ttu-id="37191-109">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="37191-109">Required string.</span></span> <span data-ttu-id="37191-110">Specifica l'URI dell'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="37191-110">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="37191-111">binding</span><span class="sxs-lookup"><span data-stu-id="37191-111">binding</span></span>|<span data-ttu-id="37191-112">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="37191-112">Optional string.</span></span> <span data-ttu-id="37191-113">Una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="37191-113">One of the system-provided bindings.</span></span> <span data-ttu-id="37191-114">Per un elenco, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="37191-114">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="37191-115">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="37191-115">bindingConfiguration</span></span>|<span data-ttu-id="37191-116">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="37191-116">Optional string.</span></span> <span data-ttu-id="37191-117">Specifica una configurazione di associazione presente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="37191-117">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37191-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37191-118">Child Elements</span></span>  
  
|<span data-ttu-id="37191-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="37191-119">Element</span></span>|<span data-ttu-id="37191-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37191-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="37191-121">Specifica informazioni sull'identità per l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="37191-121">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="37191-122">Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale.</span><span class="sxs-lookup"><span data-stu-id="37191-122">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="37191-123">È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="37191-123">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37191-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37191-124">Parent Elements</span></span>  
  
|<span data-ttu-id="37191-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="37191-125">Element</span></span>|<span data-ttu-id="37191-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37191-126">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="37191-127">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="37191-127">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37191-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="37191-128">Remarks</span></span>  
 <span data-ttu-id="37191-129">Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="37191-129">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="37191-130">Quando non <xref:System.ServiceModel.WSFederationHttpBinding> fornisce un URL per il servizio token di sicurezza o quando l'indirizzo dell'emittente di un'associazione federata è `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null` , il canale Windows Communication Foundation (WCF) del client usa i valori specificati da `address` e `binding` per comunicare con il servizio token di sicurezza per ottenere il token emesso.</span><span class="sxs-lookup"><span data-stu-id="37191-130">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="37191-131">Per altre informazioni sulla configurazione di un'autorità emittente locale, vedere [procedura: configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="37191-131">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37191-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="37191-132">Example</span></span>  
 <span data-ttu-id="37191-133">Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="37191-133">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37191-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="37191-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="37191-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="37191-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="37191-136">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="37191-136">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="37191-137">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="37191-137">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="37191-138">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="37191-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="37191-139">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="37191-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="37191-140">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="37191-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="37191-141">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="37191-141">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="37191-142">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="37191-142">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="37191-143">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="37191-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
