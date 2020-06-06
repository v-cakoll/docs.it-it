---
title: <clear>dell' <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400533"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="cffcf-102">\<clear>dell' \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="cffcf-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="cffcf-103">Specifica tutti i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="cffcf-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="cffcf-104">Ciò consente di assicurare che la raccolta sia inizialmente vuota.</span><span class="sxs-lookup"><span data-stu-id="cffcf-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="cffcf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cffcf-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cffcf-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cffcf-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cffcf-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cffcf-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cffcf-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="cffcf-108">Attributes</span></span>  
 <span data-ttu-id="cffcf-109">No.</span><span class="sxs-lookup"><span data-stu-id="cffcf-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cffcf-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cffcf-110">Child Elements</span></span>  
 <span data-ttu-id="cffcf-111">No.</span><span class="sxs-lookup"><span data-stu-id="cffcf-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cffcf-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cffcf-112">Parent Elements</span></span>  
  
|<span data-ttu-id="cffcf-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cffcf-113">Element</span></span>|<span data-ttu-id="cffcf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cffcf-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="cffcf-115">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="cffcf-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="cffcf-116">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="cffcf-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="cffcf-117">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cffcf-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="cffcf-118">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="cffcf-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="cffcf-119">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="cffcf-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cffcf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cffcf-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
