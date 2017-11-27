---
title: '&lt;oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 79dd5dd0ca383cebc5f08f3e12c6c6261d11a02a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="c91d5-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="c91d5-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="c91d5-103">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c91d5-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="c91d5-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c91d5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c91d5-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="c91d5-105">\<bindings></span></span>  
<span data-ttu-id="c91d5-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c91d5-106">\<customBinding></span></span>  
<span data-ttu-id="c91d5-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="c91d5-107">\<binding></span></span>  
<span data-ttu-id="c91d5-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="c91d5-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c91d5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c91d5-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c91d5-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c91d5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c91d5-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c91d5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c91d5-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c91d5-112">Attributes</span></span>  
  
|<span data-ttu-id="c91d5-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c91d5-113">Attribute</span></span>|<span data-ttu-id="c91d5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c91d5-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="c91d5-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c91d5-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="c91d5-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="c91d5-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="c91d5-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="c91d5-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c91d5-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c91d5-118">Child Elements</span></span>  
  
|<span data-ttu-id="c91d5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c91d5-119">Element</span></span>|<span data-ttu-id="c91d5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c91d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c91d5-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="c91d5-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="c91d5-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="c91d5-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c91d5-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c91d5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c91d5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c91d5-124">Element</span></span>|<span data-ttu-id="c91d5-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c91d5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c91d5-126">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="c91d5-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c91d5-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c91d5-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c91d5-128">Note</span><span class="sxs-lookup"><span data-stu-id="c91d5-128">Remarks</span></span>  
 <span data-ttu-id="c91d5-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="c91d5-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="c91d5-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c91d5-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="c91d5-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="c91d5-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="c91d5-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="c91d5-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c91d5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c91d5-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c91d5-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c91d5-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c91d5-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="c91d5-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c91d5-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c91d5-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c91d5-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c91d5-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
