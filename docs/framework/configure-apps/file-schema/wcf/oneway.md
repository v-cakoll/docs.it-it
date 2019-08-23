---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f4a9422f4385e37a61ec85d680fcf7743a57bc0c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932936"
---
# <a name="oneway"></a><span data-ttu-id="b3ea6-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b3ea6-101">\<oneWay></span></span>
<span data-ttu-id="b3ea6-102">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="b3ea6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b3ea6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b3ea6-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="b3ea6-104">\<bindings></span></span>  
<span data-ttu-id="b3ea6-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b3ea6-105">\<customBinding></span></span>  
<span data-ttu-id="b3ea6-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3ea6-106">\<binding></span></span>  
<span data-ttu-id="b3ea6-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b3ea6-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ea6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3ea6-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3ea6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3ea6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b3ea6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3ea6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3ea6-111">Attributes</span></span>  
  
|<span data-ttu-id="b3ea6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="b3ea6-112">Attribute</span></span>|<span data-ttu-id="b3ea6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3ea6-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="b3ea6-114">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="b3ea6-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="b3ea6-116">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3ea6-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3ea6-117">Child Elements</span></span>  
  
|<span data-ttu-id="b3ea6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3ea6-118">Element</span></span>|<span data-ttu-id="b3ea6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3ea6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3ea6-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="b3ea6-120">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="b3ea6-121">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3ea6-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3ea6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b3ea6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3ea6-123">Element</span></span>|<span data-ttu-id="b3ea6-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b3ea6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3ea6-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3ea6-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b3ea6-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3ea6-127">Note</span><span class="sxs-lookup"><span data-stu-id="b3ea6-127">Remarks</span></span>  
 <span data-ttu-id="b3ea6-128">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="b3ea6-129">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="b3ea6-130">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="b3ea6-131">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="b3ea6-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ea6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3ea6-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b3ea6-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b3ea6-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b3ea6-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b3ea6-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b3ea6-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b3ea6-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b3ea6-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b3ea6-136">\<customBinding></span></span>](custombinding.md)
