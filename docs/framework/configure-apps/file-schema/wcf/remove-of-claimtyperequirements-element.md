---
title: <remove>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399991"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="9a80f-102">\<remove>dell' \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="9a80f-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="9a80f-103">Specifica i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="9a80f-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="9a80f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a80f-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a80f-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a80f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9a80f-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a80f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a80f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a80f-107">Attributes</span></span>  
  
|<span data-ttu-id="9a80f-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="9a80f-108">Attribute</span></span>|<span data-ttu-id="9a80f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a80f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a80f-110">claimType</span><span class="sxs-lookup"><span data-stu-id="9a80f-110">claimType</span></span>|<span data-ttu-id="9a80f-111">URI che definisce il tipo di un'attestazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9a80f-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a80f-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a80f-112">Child Elements</span></span>  
 <span data-ttu-id="9a80f-113">No.</span><span class="sxs-lookup"><span data-stu-id="9a80f-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a80f-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a80f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9a80f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a80f-115">Element</span></span>|<span data-ttu-id="9a80f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a80f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="9a80f-117">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="9a80f-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="9a80f-118">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="9a80f-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="9a80f-119">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9a80f-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="9a80f-120">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="9a80f-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="9a80f-121">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="9a80f-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a80f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a80f-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
