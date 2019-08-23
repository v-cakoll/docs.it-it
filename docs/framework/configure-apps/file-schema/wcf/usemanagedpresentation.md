---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940619"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="5ead3-101">\<> useManagedPresentation</span><span class="sxs-lookup"><span data-stu-id="5ead3-101">\<useManagedPresentation></span></span>
<span data-ttu-id="5ead3-102">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="5ead3-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="5ead3-103">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="5ead3-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="5ead3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5ead3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5ead3-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="5ead3-105">\<bindings></span></span>  
<span data-ttu-id="5ead3-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5ead3-106">\<customBinding></span></span>  
<span data-ttu-id="5ead3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ead3-107">\<binding></span></span>  
<span data-ttu-id="5ead3-108">\<> useManagedPresentation</span><span class="sxs-lookup"><span data-stu-id="5ead3-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ead3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ead3-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ead3-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5ead3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5ead3-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5ead3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ead3-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5ead3-112">Attributes</span></span>  
 <span data-ttu-id="5ead3-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5ead3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ead3-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5ead3-114">Child Elements</span></span>  
 <span data-ttu-id="5ead3-115">Nessuna</span><span class="sxs-lookup"><span data-stu-id="5ead3-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ead3-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5ead3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5ead3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ead3-117">Element</span></span>|<span data-ttu-id="5ead3-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5ead3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ead3-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ead3-119">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="5ead3-120">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5ead3-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ead3-121">Note</span><span class="sxs-lookup"><span data-stu-id="5ead3-121">Remarks</span></span>  
 <span data-ttu-id="5ead3-122">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="5ead3-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="5ead3-123">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="5ead3-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ead3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ead3-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5ead3-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5ead3-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ead3-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5ead3-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5ead3-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5ead3-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5ead3-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5ead3-128">\<customBinding></span></span>](custombinding.md)
