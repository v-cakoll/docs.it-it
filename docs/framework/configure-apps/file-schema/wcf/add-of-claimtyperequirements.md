---
title: <add> di <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 53da9dacbd3277bd8b608296a1515e3da7296f1c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398375"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="73e6b-102">\<aggiungere > di \<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="73e6b-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="73e6b-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="73e6b-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="73e6b-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="73e6b-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="73e6b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73e6b-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="73e6b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="73e6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="73e6b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="73e6b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="73e6b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="73e6b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="73e6b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="73e6b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="73e6b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="73e6b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e6b-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73e6b-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73e6b-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="73e6b-115">Attributes and Elements</span></span>  
 <span data-ttu-id="73e6b-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="73e6b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73e6b-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="73e6b-117">Attributes</span></span>  
  
|<span data-ttu-id="73e6b-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="73e6b-118">Attribute</span></span>|<span data-ttu-id="73e6b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73e6b-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73e6b-120">claimType</span><span class="sxs-lookup"><span data-stu-id="73e6b-120">claimType</span></span>|<span data-ttu-id="73e6b-121">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="73e6b-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="73e6b-122">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="73e6b-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="73e6b-123">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="73e6b-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="73e6b-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="73e6b-124">isOptional</span></span>|<span data-ttu-id="73e6b-125">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="73e6b-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="73e6b-126">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="73e6b-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="73e6b-127">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="73e6b-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="73e6b-128">Ad esempio, è possibile richiedere obbligatoriamente che l'utente immetta nome, cognome e indirizzo, ma stabilire che il numero telefonico sia facoltativo.</span><span class="sxs-lookup"><span data-stu-id="73e6b-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73e6b-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="73e6b-129">Child Elements</span></span>  
 <span data-ttu-id="73e6b-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="73e6b-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73e6b-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="73e6b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="73e6b-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="73e6b-132">Element</span></span>|<span data-ttu-id="73e6b-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73e6b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73e6b-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="73e6b-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="73e6b-135">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="73e6b-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="73e6b-136">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="73e6b-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="73e6b-137">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="73e6b-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="73e6b-138">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="73e6b-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73e6b-139">Note</span><span class="sxs-lookup"><span data-stu-id="73e6b-139">Remarks</span></span>  
 <span data-ttu-id="73e6b-140">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="73e6b-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="73e6b-141">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="73e6b-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="73e6b-142">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="73e6b-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="73e6b-143">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="73e6b-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73e6b-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="73e6b-144">Example</span></span>  
 <span data-ttu-id="73e6b-145">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="73e6b-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73e6b-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e6b-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="73e6b-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="73e6b-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="73e6b-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="73e6b-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="73e6b-149">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="73e6b-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="73e6b-150">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="73e6b-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="73e6b-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="73e6b-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="73e6b-152">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="73e6b-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="73e6b-153">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="73e6b-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
