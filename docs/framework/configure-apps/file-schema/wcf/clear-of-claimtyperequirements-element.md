---
title: <clear>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400533"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="51c3e-102">\<Cancella > dell' \<elemento > ClaimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="51c3e-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="51c3e-103">Specifica tutti i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="51c3e-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="51c3e-104">Ciò consente di assicurare che la raccolta sia inizialmente vuota.</span><span class="sxs-lookup"><span data-stu-id="51c3e-104">This ensures that the collection starts empty.</span></span>  
  
<span data-ttu-id="51c3e-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="51c3e-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="51c3e-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="51c3e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="51c3e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="51c3e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="51c3e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="51c3e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="51c3e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="51c3e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="51c3e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Cancella >**</span><span class="sxs-lookup"><span data-stu-id="51c3e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c3e-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51c3e-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51c3e-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="51c3e-115">Attributes and Elements</span></span>  
 <span data-ttu-id="51c3e-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="51c3e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51c3e-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="51c3e-117">Attributes</span></span>  
 <span data-ttu-id="51c3e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="51c3e-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51c3e-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="51c3e-119">Child Elements</span></span>  
 <span data-ttu-id="51c3e-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="51c3e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51c3e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="51c3e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="51c3e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="51c3e-122">Element</span></span>|<span data-ttu-id="51c3e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51c3e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51c3e-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="51c3e-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="51c3e-125">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="51c3e-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="51c3e-126">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="51c3e-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="51c3e-127">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="51c3e-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="51c3e-128">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="51c3e-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="51c3e-129">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="51c3e-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51c3e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c3e-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
