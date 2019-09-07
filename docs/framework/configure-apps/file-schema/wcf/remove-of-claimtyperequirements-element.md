---
title: <remove>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399991"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="85c56-102">\<rimuovere > dell' \<elemento > ClaimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="85c56-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="85c56-103">Specifica i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="85c56-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="85c56-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85c56-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="85c56-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="85c56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="85c56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="85c56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="85c56-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="85c56-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="85c56-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="85c56-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="85c56-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="85c56-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c56-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85c56-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85c56-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="85c56-114">Attributes and Elements</span></span>  
 <span data-ttu-id="85c56-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="85c56-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85c56-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="85c56-116">Attributes</span></span>  
  
|<span data-ttu-id="85c56-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="85c56-117">Attribute</span></span>|<span data-ttu-id="85c56-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85c56-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85c56-119">claimType</span><span class="sxs-lookup"><span data-stu-id="85c56-119">claimType</span></span>|<span data-ttu-id="85c56-120">URI che definisce il tipo di un'attestazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="85c56-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85c56-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="85c56-121">Child Elements</span></span>  
 <span data-ttu-id="85c56-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="85c56-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85c56-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="85c56-123">Parent Elements</span></span>  
  
|<span data-ttu-id="85c56-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="85c56-124">Element</span></span>|<span data-ttu-id="85c56-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="85c56-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85c56-126">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="85c56-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="85c56-127">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="85c56-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="85c56-128">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="85c56-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="85c56-129">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="85c56-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="85c56-130">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="85c56-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="85c56-131">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="85c56-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85c56-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85c56-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
