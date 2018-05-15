---
title: '&lt;add&gt; di &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: b4f9275fdc36ea3c7ba79c6609f039c3b1f4c3ed
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltclaimtyperequirementsgt"></a><span data-ttu-id="5216c-102">&lt;add&gt; di &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="5216c-102">&lt;add&gt; of &lt;claimTypeRequirements&gt;</span></span>
<span data-ttu-id="5216c-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="5216c-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="5216c-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="5216c-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="5216c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5216c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5216c-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="5216c-106">\<bindings></span></span>  
<span data-ttu-id="5216c-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5216c-107">\<customBinding></span></span>  
<span data-ttu-id="5216c-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="5216c-108">\<binding></span></span>  
<span data-ttu-id="5216c-109">\<security></span><span class="sxs-lookup"><span data-stu-id="5216c-109">\<security></span></span>  
<span data-ttu-id="5216c-110">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="5216c-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="5216c-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5216c-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5216c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5216c-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <add claimType="URI"  
           isOptional="Boolean" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5216c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5216c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5216c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5216c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5216c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="5216c-115">Attributes</span></span>  
  
|<span data-ttu-id="5216c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="5216c-116">Attribute</span></span>|<span data-ttu-id="5216c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5216c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5216c-118">claimType</span><span class="sxs-lookup"><span data-stu-id="5216c-118">claimType</span></span>|<span data-ttu-id="5216c-119">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="5216c-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="5216c-120">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="5216c-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="5216c-121">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="5216c-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="5216c-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="5216c-122">isOptional</span></span>|<span data-ttu-id="5216c-123">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="5216c-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="5216c-124">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5216c-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="5216c-125">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="5216c-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="5216c-126">Ad esempio, è possibile richiedere obbligatoriamente che l'utente immetta nome, cognome e indirizzo, ma stabilire che il numero telefonico sia facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5216c-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5216c-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5216c-127">Child Elements</span></span>  
 <span data-ttu-id="5216c-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5216c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5216c-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5216c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5216c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="5216c-130">Element</span></span>|<span data-ttu-id="5216c-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5216c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5216c-132">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5216c-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="5216c-133">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="5216c-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="5216c-134">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="5216c-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="5216c-135">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="5216c-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="5216c-136">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="5216c-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5216c-137">Note</span><span class="sxs-lookup"><span data-stu-id="5216c-137">Remarks</span></span>  
 <span data-ttu-id="5216c-138">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="5216c-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="5216c-139">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="5216c-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="5216c-140">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5216c-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="5216c-141">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="5216c-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5216c-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="5216c-142">Example</span></span>  
 <span data-ttu-id="5216c-143">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5216c-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>  
    <wsFederationHttpBinding>  
      <binding name="myFederatedBinding">  
        <security mode="Message">  
          <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">  
            <claimTypeRequirements>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress"/>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"    
optional="true" />  
            </claims>  
          </message>  
        </security>  
      </binding>  
    </wsFederationHttpBinding>  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5216c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5216c-144">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="5216c-145">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5216c-145">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)  
 [<span data-ttu-id="5216c-146">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5216c-146">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5216c-147">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5216c-147">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="5216c-148">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5216c-148">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="5216c-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5216c-149">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="5216c-150">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5216c-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="5216c-151">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5216c-151">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
