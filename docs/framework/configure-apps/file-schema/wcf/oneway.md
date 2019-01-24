---
title: '&lt;oneWay&gt;'
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: c909bce5b54976a215a59ca8fd9f097f574acd80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600297"
---
# <a name="ltonewaygt"></a><span data-ttu-id="5dcaa-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="5dcaa-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="5dcaa-103">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="5dcaa-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5dcaa-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5dcaa-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="5dcaa-105">\<bindings></span></span>  
<span data-ttu-id="5dcaa-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5dcaa-106">\<customBinding></span></span>  
<span data-ttu-id="5dcaa-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5dcaa-107">\<binding></span></span>  
<span data-ttu-id="5dcaa-108">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="5dcaa-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dcaa-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dcaa-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dcaa-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5dcaa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5dcaa-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dcaa-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5dcaa-112">Attributes</span></span>  
  
|<span data-ttu-id="5dcaa-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5dcaa-113">Attribute</span></span>|<span data-ttu-id="5dcaa-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dcaa-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="5dcaa-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="5dcaa-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="5dcaa-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5dcaa-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5dcaa-118">Child Elements</span></span>  
  
|<span data-ttu-id="5dcaa-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dcaa-119">Element</span></span>|<span data-ttu-id="5dcaa-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dcaa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dcaa-121">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="5dcaa-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="5dcaa-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dcaa-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5dcaa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5dcaa-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dcaa-124">Element</span></span>|<span data-ttu-id="5dcaa-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dcaa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dcaa-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="5dcaa-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5dcaa-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dcaa-128">Note</span><span class="sxs-lookup"><span data-stu-id="5dcaa-128">Remarks</span></span>  
 <span data-ttu-id="5dcaa-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="5dcaa-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="5dcaa-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="5dcaa-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="5dcaa-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcaa-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dcaa-133">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5dcaa-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5dcaa-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5dcaa-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5dcaa-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5dcaa-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5dcaa-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5dcaa-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5dcaa-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
