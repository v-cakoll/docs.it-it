---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: a60e1e16b9b41cc5df4ded51cc05d6109dd7b3dc
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147707"
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="1445a-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="1445a-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="1445a-103">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="1445a-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="1445a-104">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="1445a-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="1445a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1445a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1445a-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1445a-106">\<bindings></span></span>  
<span data-ttu-id="1445a-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1445a-107">\<customBinding></span></span>  
<span data-ttu-id="1445a-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="1445a-108">\<binding></span></span>  
<span data-ttu-id="1445a-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="1445a-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1445a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1445a-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1445a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1445a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1445a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1445a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1445a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1445a-113">Attributes</span></span>  
 <span data-ttu-id="1445a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1445a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1445a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1445a-115">Child Elements</span></span>  
 <span data-ttu-id="1445a-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="1445a-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1445a-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1445a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1445a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1445a-118">Element</span></span>|<span data-ttu-id="1445a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1445a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1445a-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="1445a-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1445a-121">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1445a-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1445a-122">Note</span><span class="sxs-lookup"><span data-stu-id="1445a-122">Remarks</span></span>  
 <span data-ttu-id="1445a-123">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="1445a-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="1445a-124">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="1445a-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1445a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1445a-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1445a-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1445a-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1445a-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1445a-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1445a-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1445a-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1445a-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1445a-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
