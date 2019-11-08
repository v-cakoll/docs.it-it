---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738785"
---
# <a name="oneway"></a><span data-ttu-id="84993-101">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="84993-101">\<oneWay></span></span>
<span data-ttu-id="84993-102">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="84993-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="84993-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="84993-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="84993-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="84993-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="84993-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="84993-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="84993-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="84993-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="84993-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="84993-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="84993-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**oneWay** ></span><span class="sxs-lookup"><span data-stu-id="84993-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84993-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84993-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84993-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="84993-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84993-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="84993-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84993-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="84993-112">Attributes</span></span>  
  
|<span data-ttu-id="84993-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="84993-113">Attribute</span></span>|<span data-ttu-id="84993-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84993-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="84993-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="84993-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="84993-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="84993-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="84993-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="84993-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84993-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="84993-118">Child Elements</span></span>  
  
|<span data-ttu-id="84993-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="84993-119">Element</span></span>|<span data-ttu-id="84993-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84993-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84993-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="84993-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="84993-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="84993-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84993-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="84993-123">Parent Elements</span></span>  
  
|<span data-ttu-id="84993-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="84993-124">Element</span></span>|<span data-ttu-id="84993-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84993-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84993-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="84993-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="84993-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="84993-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84993-128">Note</span><span class="sxs-lookup"><span data-stu-id="84993-128">Remarks</span></span>  
 <span data-ttu-id="84993-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="84993-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="84993-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="84993-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="84993-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="84993-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="84993-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="84993-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84993-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84993-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="84993-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="84993-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="84993-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="84993-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="84993-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="84993-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="84993-137">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="84993-137">\<customBinding></span></span>](custombinding.md)
