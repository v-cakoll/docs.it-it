---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735949"
---
# \<useManagedPresentation>
<span data-ttu-id="702aa-101">Elemento di associazione usato per comunicare con un servizio token di sicurezza CardSpace che supporta il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="702aa-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="702aa-102">Questo elemento non ha attributo e è presente come un'opzione vuota.</span><span class="sxs-lookup"><span data-stu-id="702aa-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="702aa-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="702aa-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="702aa-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="702aa-104">Attributes and Elements</span></span>  
 <span data-ttu-id="702aa-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="702aa-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="702aa-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="702aa-106">Attributes</span></span>  
 <span data-ttu-id="702aa-107">No.</span><span class="sxs-lookup"><span data-stu-id="702aa-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="702aa-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="702aa-108">Child Elements</span></span>  
 <span data-ttu-id="702aa-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="702aa-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="702aa-110">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="702aa-110">Parent Elements</span></span>  
  
|<span data-ttu-id="702aa-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="702aa-111">Element</span></span>|<span data-ttu-id="702aa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="702aa-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="702aa-113">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="702aa-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="702aa-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="702aa-114">Remarks</span></span>  
 <span data-ttu-id="702aa-115">Questo elemento viene usato da un provider di identità per dichiarare nei relativi criteri il fatto che supporti il profilo CardSpace di WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="702aa-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="702aa-116">I provider di identità che pubblicano questo tipo di asserzione di criteri devono essere in grado di pubblicare token basati su tale profilo CardSpace.</span><span class="sxs-lookup"><span data-stu-id="702aa-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="702aa-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="702aa-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="702aa-118">Binding</span><span class="sxs-lookup"><span data-stu-id="702aa-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="702aa-119">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="702aa-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="702aa-120">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="702aa-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
