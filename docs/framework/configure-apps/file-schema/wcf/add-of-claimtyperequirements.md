---
title: <add> di <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153087"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="d0eda-102">\<add> di \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="d0eda-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="d0eda-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="d0eda-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="d0eda-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="d0eda-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d0eda-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0eda-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0eda-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d0eda-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d0eda-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d0eda-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0eda-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="d0eda-108">Attributes</span></span>  
  
|<span data-ttu-id="d0eda-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="d0eda-109">Attribute</span></span>|<span data-ttu-id="d0eda-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0eda-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0eda-111">claimType</span><span class="sxs-lookup"><span data-stu-id="d0eda-111">claimType</span></span>|<span data-ttu-id="d0eda-112">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="d0eda-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="d0eda-113">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="d0eda-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="d0eda-114">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="d0eda-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="d0eda-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="d0eda-115">isOptional</span></span>|<span data-ttu-id="d0eda-116">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d0eda-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="d0eda-117">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d0eda-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="d0eda-118">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="d0eda-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="d0eda-119">Ad esempio, se si richiede all'utente di immettere il nome, il cognome e l'indirizzo, ma si decide che il numero di telefono è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d0eda-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0eda-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d0eda-120">Child Elements</span></span>  
 <span data-ttu-id="d0eda-121">No.</span><span class="sxs-lookup"><span data-stu-id="d0eda-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0eda-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d0eda-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d0eda-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0eda-123">Element</span></span>|<span data-ttu-id="d0eda-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0eda-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="d0eda-125">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="d0eda-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="d0eda-126">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d0eda-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d0eda-127">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="d0eda-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d0eda-128">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="d0eda-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0eda-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="d0eda-129">Remarks</span></span>  
 <span data-ttu-id="d0eda-130">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d0eda-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d0eda-131">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="d0eda-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d0eda-132">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d0eda-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="d0eda-133">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="d0eda-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0eda-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0eda-134">Example</span></span>  
 <span data-ttu-id="d0eda-135">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d0eda-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0eda-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d0eda-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="d0eda-137">Binding</span><span class="sxs-lookup"><span data-stu-id="d0eda-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d0eda-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="d0eda-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d0eda-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d0eda-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="d0eda-140">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d0eda-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d0eda-141">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d0eda-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
