---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 2458cdd4d593637c2025047d5dd510f0f89b2a0f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423079"
---
# <a name="oneway"></a><span data-ttu-id="a277e-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="a277e-101">\<oneWay></span></span>
<span data-ttu-id="a277e-102">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a277e-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="a277e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a277e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a277e-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="a277e-104">\<bindings></span></span>  
<span data-ttu-id="a277e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a277e-105">\<customBinding></span></span>  
<span data-ttu-id="a277e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a277e-106">\<binding></span></span>  
<span data-ttu-id="a277e-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="a277e-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a277e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a277e-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a277e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a277e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a277e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a277e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a277e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a277e-111">Attributes</span></span>  
  
|<span data-ttu-id="a277e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a277e-112">Attribute</span></span>|<span data-ttu-id="a277e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a277e-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="a277e-114">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a277e-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="a277e-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a277e-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="a277e-116">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="a277e-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a277e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a277e-117">Child Elements</span></span>  
  
|<span data-ttu-id="a277e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a277e-118">Element</span></span>|<span data-ttu-id="a277e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a277e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a277e-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="a277e-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="a277e-121">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="a277e-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a277e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a277e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a277e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a277e-123">Element</span></span>|<span data-ttu-id="a277e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a277e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a277e-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="a277e-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a277e-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a277e-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a277e-127">Note</span><span class="sxs-lookup"><span data-stu-id="a277e-127">Remarks</span></span>  
 <span data-ttu-id="a277e-128">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="a277e-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="a277e-129">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a277e-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="a277e-130">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="a277e-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="a277e-131">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="a277e-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a277e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a277e-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a277e-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a277e-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a277e-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="a277e-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a277e-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a277e-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a277e-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a277e-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
