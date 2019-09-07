---
title: <add>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 9c56cccd7a6f72a701e4b8652afecc2361e6218a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400681"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="cfe90-102">\<Aggiungi > dell' \<elemento > ClaimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="cfe90-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="cfe90-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="cfe90-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="cfe90-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="cfe90-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="cfe90-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfe90-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cfe90-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cfe90-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="cfe90-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="cfe90-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cfe90-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="cfe90-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="cfe90-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="cfe90-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="cfe90-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="cfe90-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cfe90-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfe90-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfe90-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfe90-115">Attributes and Elements</span></span>  
 <span data-ttu-id="cfe90-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfe90-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfe90-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfe90-117">Attributes</span></span>  
  
|<span data-ttu-id="cfe90-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfe90-118">Attribute</span></span>|<span data-ttu-id="cfe90-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfe90-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfe90-120">claimType</span><span class="sxs-lookup"><span data-stu-id="cfe90-120">claimType</span></span>|<span data-ttu-id="cfe90-121">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="cfe90-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="cfe90-122">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="cfe90-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="cfe90-123">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="cfe90-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="cfe90-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="cfe90-124">isOptional</span></span>|<span data-ttu-id="cfe90-125">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cfe90-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="cfe90-126">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="cfe90-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="cfe90-127">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="cfe90-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="cfe90-128">Ad esempio, è possibile richiedere obbligatoriamente che l'utente immetta nome, cognome e indirizzo, ma stabilire che il numero telefonico sia facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cfe90-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfe90-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfe90-129">Child Elements</span></span>  
 <span data-ttu-id="cfe90-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cfe90-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfe90-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfe90-131">Parent Elements</span></span>  
  
|<span data-ttu-id="cfe90-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfe90-132">Element</span></span>|<span data-ttu-id="cfe90-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfe90-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfe90-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="cfe90-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="cfe90-135">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="cfe90-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="cfe90-136">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="cfe90-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="cfe90-137">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cfe90-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="cfe90-138">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="cfe90-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="cfe90-139">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="cfe90-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfe90-140">Note</span><span class="sxs-lookup"><span data-stu-id="cfe90-140">Remarks</span></span>  
 <span data-ttu-id="cfe90-141">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cfe90-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="cfe90-142">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="cfe90-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="cfe90-143">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfe90-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="cfe90-144">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="cfe90-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfe90-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfe90-145">Example</span></span>  
 <span data-ttu-id="cfe90-146">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfe90-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cfe90-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfe90-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
