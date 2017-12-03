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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be70abe745879b5d6f6e8cdde802a6403f90174b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="cb9dd-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="cb9dd-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="cb9dd-103">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="cb9dd-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cb9dd-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-105">\<bindings></span></span>  
<span data-ttu-id="cb9dd-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-106">\<customBinding></span></span>  
<span data-ttu-id="cb9dd-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-107">\<binding></span></span>  
<span data-ttu-id="cb9dd-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb9dd-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb9dd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb9dd-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cb9dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb9dd-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb9dd-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cb9dd-112">Attributes</span></span>  
  
|<span data-ttu-id="cb9dd-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cb9dd-113">Attribute</span></span>|<span data-ttu-id="cb9dd-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb9dd-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="cb9dd-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="cb9dd-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="cb9dd-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb9dd-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cb9dd-118">Child Elements</span></span>  
  
|<span data-ttu-id="cb9dd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb9dd-119">Element</span></span>|<span data-ttu-id="cb9dd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb9dd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb9dd-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="cb9dd-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb9dd-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cb9dd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cb9dd-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb9dd-124">Element</span></span>|<span data-ttu-id="cb9dd-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb9dd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb9dd-126">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cb9dd-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb9dd-128">Note</span><span class="sxs-lookup"><span data-stu-id="cb9dd-128">Remarks</span></span>  
 <span data-ttu-id="cb9dd-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="cb9dd-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="cb9dd-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="cb9dd-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="cb9dd-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9dd-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb9dd-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="cb9dd-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cb9dd-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cb9dd-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="cb9dd-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="cb9dd-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cb9dd-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="cb9dd-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cb9dd-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
