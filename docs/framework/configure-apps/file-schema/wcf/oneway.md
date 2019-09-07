---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f12969d8b752e54916b45c3d0e64f114971b8944
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397658"
---
# <a name="oneway"></a><span data-ttu-id="207ae-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="207ae-101">\<oneWay></span></span>
<span data-ttu-id="207ae-102">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="207ae-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="207ae-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="207ae-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="207ae-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="207ae-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="207ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="207ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="207ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="207ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="207ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="207ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="207ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oneWay**</span><span class="sxs-lookup"><span data-stu-id="207ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="207ae-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="207ae-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="207ae-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="207ae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="207ae-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="207ae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="207ae-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="207ae-112">Attributes</span></span>  
  
|<span data-ttu-id="207ae-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="207ae-113">Attribute</span></span>|<span data-ttu-id="207ae-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="207ae-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="207ae-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="207ae-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="207ae-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="207ae-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="207ae-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="207ae-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="207ae-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="207ae-118">Child Elements</span></span>  
  
|<span data-ttu-id="207ae-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="207ae-119">Element</span></span>|<span data-ttu-id="207ae-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="207ae-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="207ae-121">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="207ae-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="207ae-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="207ae-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="207ae-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="207ae-123">Parent Elements</span></span>  
  
|<span data-ttu-id="207ae-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="207ae-124">Element</span></span>|<span data-ttu-id="207ae-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="207ae-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="207ae-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="207ae-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="207ae-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="207ae-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="207ae-128">Note</span><span class="sxs-lookup"><span data-stu-id="207ae-128">Remarks</span></span>  
 <span data-ttu-id="207ae-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="207ae-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="207ae-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="207ae-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="207ae-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="207ae-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="207ae-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="207ae-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207ae-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="207ae-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="207ae-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="207ae-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="207ae-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="207ae-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="207ae-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="207ae-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="207ae-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="207ae-137">\<customBinding></span></span>](custombinding.md)
