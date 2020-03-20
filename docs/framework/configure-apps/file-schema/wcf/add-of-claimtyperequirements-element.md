---
title: <add>dell'elemento <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153100"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="a6114-102">\<aggiungere> \<dell'elemento> claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="a6114-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="a6114-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="a6114-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="a6114-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="a6114-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="a6114-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a6114-106">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a6114-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<associazioni>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a6114-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a6114-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di associazione**</span><span class="sxs-lookup"><span data-stu-id="a6114-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a6114-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di sicurezza**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="a6114-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>dei messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a6114-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="a6114-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="a6114-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="a6114-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a6114-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6114-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6114-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6114-115">Attributes and Elements</span></span>  
 <span data-ttu-id="a6114-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6114-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6114-117">Attributes</span><span class="sxs-lookup"><span data-stu-id="a6114-117">Attributes</span></span>  
  
|<span data-ttu-id="a6114-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="a6114-118">Attribute</span></span>|<span data-ttu-id="a6114-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6114-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6114-120">claimType</span><span class="sxs-lookup"><span data-stu-id="a6114-120">claimType</span></span>|<span data-ttu-id="a6114-121">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="a6114-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="a6114-122">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="a6114-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="a6114-123">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="a6114-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="a6114-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="a6114-124">isOptional</span></span>|<span data-ttu-id="a6114-125">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6114-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="a6114-126">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="a6114-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="a6114-127">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="a6114-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="a6114-128">Ad esempio, se si richiede all'utente di immettere il nome, il cognome e l'indirizzo, ma si decide che il numero di telefono è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6114-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6114-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6114-129">Child Elements</span></span>  
 <span data-ttu-id="a6114-130">No.</span><span class="sxs-lookup"><span data-stu-id="a6114-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6114-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6114-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a6114-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6114-132">Element</span></span>|<span data-ttu-id="a6114-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6114-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6114-134">\<>claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="a6114-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="a6114-135">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="a6114-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="a6114-136">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="a6114-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="a6114-137">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a6114-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="a6114-138">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="a6114-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="a6114-139">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="a6114-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6114-140">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a6114-140">Remarks</span></span>  
 <span data-ttu-id="a6114-141">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a6114-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="a6114-142">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="a6114-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="a6114-143">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a6114-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="a6114-144">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="a6114-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6114-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6114-145">Example</span></span>  
 <span data-ttu-id="a6114-146">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a6114-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="a6114-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6114-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
