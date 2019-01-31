---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 1134c4d5f18f60bb2986f4239a788b836fa9113e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287248"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="7ee0f-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="7ee0f-101">\<useManagedPresentation></span></span>
<span data-ttu-id="7ee0f-102">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="7ee0f-103">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="7ee0f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ee0f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7ee0f-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="7ee0f-105">\<bindings></span></span>  
<span data-ttu-id="7ee0f-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ee0f-106">\<customBinding></span></span>  
<span data-ttu-id="7ee0f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ee0f-107">\<binding></span></span>  
<span data-ttu-id="7ee0f-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="7ee0f-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee0f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ee0f-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ee0f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7ee0f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ee0f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ee0f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7ee0f-112">Attributes</span></span>  
 <span data-ttu-id="7ee0f-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ee0f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7ee0f-114">Child Elements</span></span>  
 <span data-ttu-id="7ee0f-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="7ee0f-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ee0f-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7ee0f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7ee0f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ee0f-117">Element</span></span>|<span data-ttu-id="7ee0f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ee0f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ee0f-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ee0f-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7ee0f-120">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ee0f-121">Note</span><span class="sxs-lookup"><span data-stu-id="7ee0f-121">Remarks</span></span>  
 <span data-ttu-id="7ee0f-122">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="7ee0f-123">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="7ee0f-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee0f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ee0f-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7ee0f-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7ee0f-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7ee0f-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7ee0f-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7ee0f-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7ee0f-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7ee0f-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ee0f-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
