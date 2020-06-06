---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738785"
---
# \<oneWay>
<span data-ttu-id="90906-101">Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="90906-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="90906-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90906-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90906-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90906-103">Attributes and Elements</span></span>  
 <span data-ttu-id="90906-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90906-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90906-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="90906-105">Attributes</span></span>  
  
|<span data-ttu-id="90906-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="90906-106">Attribute</span></span>|<span data-ttu-id="90906-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90906-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="90906-108">Valore booleano che specifica se è attivato il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="90906-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="90906-109">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="90906-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="90906-110">Numero intero che specifica il numero massimo di canali che possono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="90906-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90906-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90906-111">Child Elements</span></span>  
  
|<span data-ttu-id="90906-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="90906-112">Element</span></span>|<span data-ttu-id="90906-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90906-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="90906-114">Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.</span><span class="sxs-lookup"><span data-stu-id="90906-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90906-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90906-115">Parent Elements</span></span>  
  
|<span data-ttu-id="90906-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="90906-116">Element</span></span>|<span data-ttu-id="90906-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90906-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="90906-118">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="90906-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90906-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="90906-119">Remarks</span></span>  
 <span data-ttu-id="90906-120">Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="90906-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="90906-121">Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="90906-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="90906-122">Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo.</span><span class="sxs-lookup"><span data-stu-id="90906-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="90906-123">Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.</span><span class="sxs-lookup"><span data-stu-id="90906-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90906-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="90906-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="90906-125">Binding</span><span class="sxs-lookup"><span data-stu-id="90906-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="90906-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="90906-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="90906-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="90906-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
