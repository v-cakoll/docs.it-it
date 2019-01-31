---
title: <add> di <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 6971837ef2e68de54179daaf225394b9de769987
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275587"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="7d655-102">\<aggiungere > di \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="7d655-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="7d655-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="7d655-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="7d655-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="7d655-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="7d655-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7d655-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d655-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="7d655-106">\<bindings></span></span>  
<span data-ttu-id="7d655-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="7d655-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="7d655-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d655-108">\<binding></span></span>  
<span data-ttu-id="7d655-109">\<security></span><span class="sxs-lookup"><span data-stu-id="7d655-109">\<security></span></span>  
<span data-ttu-id="7d655-110">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="7d655-110">\<message></span></span>  
<span data-ttu-id="7d655-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7d655-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d655-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d655-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d655-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d655-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7d655-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d655-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d655-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d655-115">Attributes</span></span>  
  
|<span data-ttu-id="7d655-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d655-116">Attribute</span></span>|<span data-ttu-id="7d655-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d655-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d655-118">claimType</span><span class="sxs-lookup"><span data-stu-id="7d655-118">claimType</span></span>|<span data-ttu-id="7d655-119">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="7d655-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="7d655-120">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="7d655-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="7d655-121">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="7d655-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="7d655-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="7d655-122">isOptional</span></span>|<span data-ttu-id="7d655-123">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7d655-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="7d655-124">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="7d655-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="7d655-125">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="7d655-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="7d655-126">Ad esempio, è possibile richiedere obbligatoriamente che l'utente immetta nome, cognome e indirizzo, ma stabilire che il numero telefonico sia facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7d655-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d655-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d655-127">Child Elements</span></span>  
 <span data-ttu-id="7d655-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7d655-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d655-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d655-129">Parent Elements</span></span>  
  
|<span data-ttu-id="7d655-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d655-130">Element</span></span>|<span data-ttu-id="7d655-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d655-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d655-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7d655-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="7d655-133">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7d655-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7d655-134">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7d655-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7d655-135">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7d655-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7d655-136">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="7d655-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7d655-137">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="7d655-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d655-138">Note</span><span class="sxs-lookup"><span data-stu-id="7d655-138">Remarks</span></span>  
 <span data-ttu-id="7d655-139">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7d655-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7d655-140">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="7d655-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7d655-141">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7d655-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="7d655-142">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="7d655-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d655-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d655-143">Example</span></span>  
 <span data-ttu-id="7d655-144">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7d655-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d655-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d655-145">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
