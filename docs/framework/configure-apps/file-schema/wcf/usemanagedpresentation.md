---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735949"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="8f430-101">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="8f430-101">\<useManagedPresentation></span></span>
<span data-ttu-id="8f430-102">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="8f430-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="8f430-103">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="8f430-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="8f430-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f430-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f430-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8f430-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8f430-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="8f430-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8f430-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="8f430-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8f430-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="8f430-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8f430-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useManagedPresentation >**</span><span class="sxs-lookup"><span data-stu-id="8f430-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f430-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f430-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f430-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8f430-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8f430-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8f430-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f430-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8f430-113">Attributes</span></span>  
 <span data-ttu-id="8f430-114">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="8f430-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f430-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8f430-115">Child Elements</span></span>  
 <span data-ttu-id="8f430-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8f430-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f430-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8f430-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8f430-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f430-118">Element</span></span>|<span data-ttu-id="8f430-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f430-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f430-120">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8f430-120">\<binding></span></span>](bindings.md)|<span data-ttu-id="8f430-121">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8f430-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f430-122">Note</span><span class="sxs-lookup"><span data-stu-id="8f430-122">Remarks</span></span>  
 <span data-ttu-id="8f430-123">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="8f430-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="8f430-124">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="8f430-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f430-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f430-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8f430-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8f430-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8f430-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="8f430-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8f430-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8f430-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8f430-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="8f430-129">\<customBinding></span></span>](custombinding.md)
