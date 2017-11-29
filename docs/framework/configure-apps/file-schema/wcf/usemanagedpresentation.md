---
title: '&lt;useManagedPresentation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f99879ab80acddf1d50f5e5c734b8d6c975cb348
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="37e71-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="37e71-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="37e71-103">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="37e71-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="37e71-104">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="37e71-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="37e71-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="37e71-105">\<system.serviceModel></span></span>  
<span data-ttu-id="37e71-106">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="37e71-106">\<bindings></span></span>  
<span data-ttu-id="37e71-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="37e71-107">\<customBinding></span></span>  
<span data-ttu-id="37e71-108">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="37e71-108">\<binding></span></span>  
<span data-ttu-id="37e71-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="37e71-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37e71-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37e71-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37e71-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37e71-111">Attributes and Elements</span></span>  
 <span data-ttu-id="37e71-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37e71-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37e71-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="37e71-113">Attributes</span></span>  
 <span data-ttu-id="37e71-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="37e71-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37e71-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37e71-115">Child Elements</span></span>  
 <span data-ttu-id="37e71-116">None</span><span class="sxs-lookup"><span data-stu-id="37e71-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37e71-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37e71-117">Parent Elements</span></span>  
  
|<span data-ttu-id="37e71-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="37e71-118">Element</span></span>|<span data-ttu-id="37e71-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37e71-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37e71-120">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="37e71-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="37e71-121">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="37e71-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37e71-122">Note</span><span class="sxs-lookup"><span data-stu-id="37e71-122">Remarks</span></span>  
 <span data-ttu-id="37e71-123">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="37e71-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="37e71-124">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="37e71-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e71-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37e71-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="37e71-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="37e71-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="37e71-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="37e71-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="37e71-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="37e71-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="37e71-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="37e71-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
