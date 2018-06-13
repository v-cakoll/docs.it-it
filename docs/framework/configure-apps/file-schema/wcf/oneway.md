---
title: '&lt;oneWay&gt;'
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f9a5631501b3879463606f526485314efd5eff2b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746722"
---
# <a name="ltonewaygt"></a><span data-ttu-id="b3d90-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="b3d90-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="b3d90-103">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b3d90-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="b3d90-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b3d90-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b3d90-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="b3d90-105">\<bindings></span></span>  
<span data-ttu-id="b3d90-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b3d90-106">\<customBinding></span></span>  
<span data-ttu-id="b3d90-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3d90-107">\<binding></span></span>  
<span data-ttu-id="b3d90-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="b3d90-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3d90-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3d90-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3d90-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3d90-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b3d90-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3d90-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3d90-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3d90-112">Attributes</span></span>  
  
|<span data-ttu-id="b3d90-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b3d90-113">Attribute</span></span>|<span data-ttu-id="b3d90-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3d90-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="b3d90-115">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b3d90-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="b3d90-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b3d90-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="b3d90-117">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="b3d90-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3d90-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3d90-118">Child Elements</span></span>  
  
|<span data-ttu-id="b3d90-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3d90-119">Element</span></span>|<span data-ttu-id="b3d90-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3d90-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3d90-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="b3d90-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="b3d90-122">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="b3d90-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3d90-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3d90-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b3d90-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3d90-124">Element</span></span>|<span data-ttu-id="b3d90-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3d90-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3d90-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3d90-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b3d90-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b3d90-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3d90-128">Note</span><span class="sxs-lookup"><span data-stu-id="b3d90-128">Remarks</span></span>  
 <span data-ttu-id="b3d90-129">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="b3d90-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="b3d90-130">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b3d90-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="b3d90-131">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="b3d90-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="b3d90-132">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="b3d90-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d90-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3d90-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="b3d90-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b3d90-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b3d90-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b3d90-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b3d90-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b3d90-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b3d90-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b3d90-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
