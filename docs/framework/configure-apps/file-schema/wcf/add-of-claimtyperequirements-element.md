---
title: <add>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153100"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="7275e-102">\<add>dell' \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="7275e-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="7275e-103">Specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="7275e-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="7275e-104">Ad esempio, i servizi definiscono requisiti per le credenziali in entrata affinché dispongano di un determinato set di tipi di attestazione.</span><span class="sxs-lookup"><span data-stu-id="7275e-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="7275e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7275e-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7275e-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7275e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7275e-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7275e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7275e-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="7275e-108">Attributes</span></span>  
  
|<span data-ttu-id="7275e-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="7275e-109">Attribute</span></span>|<span data-ttu-id="7275e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7275e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7275e-111">claimType</span><span class="sxs-lookup"><span data-stu-id="7275e-111">claimType</span></span>|<span data-ttu-id="7275e-112">URI che definisce il tipo di un'attestazione.</span><span class="sxs-lookup"><span data-stu-id="7275e-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="7275e-113">Ad esempio, per acquistare un prodotto da un sito Web, l'utente deve presentare una carta di credito valida avente un limite di credito sufficiente.</span><span class="sxs-lookup"><span data-stu-id="7275e-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="7275e-114">Il tipo di attestazione in questo caso è l'URI della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="7275e-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="7275e-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="7275e-115">isOptional</span></span>|<span data-ttu-id="7275e-116">Valore booleano che specifica se l'attestazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7275e-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="7275e-117">Impostare questo attributo su `false` se l'attestazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="7275e-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="7275e-118">Questo attributo può essere usato quando il servizio richiede alcune informazioni non obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="7275e-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="7275e-119">Ad esempio, se si richiede all'utente di immettere il nome, il cognome e l'indirizzo, ma si decide che il numero di telefono è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7275e-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7275e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7275e-120">Child Elements</span></span>  
 <span data-ttu-id="7275e-121">No.</span><span class="sxs-lookup"><span data-stu-id="7275e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7275e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7275e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7275e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="7275e-123">Element</span></span>|<span data-ttu-id="7275e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7275e-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="7275e-125">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7275e-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7275e-126">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7275e-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7275e-127">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7275e-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7275e-128">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="7275e-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7275e-129">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="7275e-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7275e-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="7275e-130">Remarks</span></span>  
 <span data-ttu-id="7275e-131">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7275e-131">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7275e-132">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="7275e-132">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7275e-133">Questo requisito si presenta in un criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7275e-133">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="7275e-134">Quando un client richiede credenziali da un servizio federato (ad esempio CardSpace), tale client inserisce i requisiti in una richiesta di token (RequestSecurityToken) affinché il servizio federato sia in grado di rilasciare le credenziali che soddisfano opportunamente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="7275e-134">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7275e-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="7275e-135">Example</span></span>  
 <span data-ttu-id="7275e-136">Nella configurazione seguente vengono aggiunti due requisiti di tipo di attestazione a un'associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7275e-136">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7275e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7275e-137">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
