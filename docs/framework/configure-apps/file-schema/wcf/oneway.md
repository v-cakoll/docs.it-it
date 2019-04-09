---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: bfda2b9d7b3aa5219a3e4c344347d3b10419a7bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102414"
---
# <a name="oneway"></a><span data-ttu-id="771fa-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="771fa-101">\<oneWay></span></span>
<span data-ttu-id="771fa-102">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="771fa-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="771fa-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="771fa-103">\<system.serviceModel></span></span>  
<span data-ttu-id="771fa-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="771fa-104">\<bindings></span></span>  
<span data-ttu-id="771fa-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="771fa-105">\<customBinding></span></span>  
<span data-ttu-id="771fa-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="771fa-106">\<binding></span></span>  
<span data-ttu-id="771fa-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="771fa-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="771fa-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="771fa-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="771fa-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="771fa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="771fa-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="771fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="771fa-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="771fa-111">Attributes</span></span>  
  
|<span data-ttu-id="771fa-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="771fa-112">Attribute</span></span>|<span data-ttu-id="771fa-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="771fa-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="771fa-114">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="771fa-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="771fa-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="771fa-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="771fa-116">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="771fa-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="771fa-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="771fa-117">Child Elements</span></span>  
  
|<span data-ttu-id="771fa-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="771fa-118">Element</span></span>|<span data-ttu-id="771fa-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="771fa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="771fa-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="771fa-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="771fa-121">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="771fa-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="771fa-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="771fa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="771fa-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="771fa-123">Element</span></span>|<span data-ttu-id="771fa-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="771fa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="771fa-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="771fa-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="771fa-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="771fa-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="771fa-127">Note</span><span class="sxs-lookup"><span data-stu-id="771fa-127">Remarks</span></span>  
 <span data-ttu-id="771fa-128">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="771fa-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="771fa-129">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="771fa-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="771fa-130">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="771fa-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="771fa-131">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="771fa-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771fa-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="771fa-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="771fa-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="771fa-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="771fa-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="771fa-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="771fa-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="771fa-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="771fa-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="771fa-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
