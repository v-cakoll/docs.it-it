---
title: Elemento <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399503"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="13187-102">Elemento \<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="13187-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="13187-103">Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="13187-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="13187-104">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="13187-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="13187-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13187-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13187-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="13187-106">Attributes and Elements</span></span>  
 <span data-ttu-id="13187-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="13187-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13187-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="13187-108">Attributes</span></span>  
 <span data-ttu-id="13187-109">No.</span><span class="sxs-lookup"><span data-stu-id="13187-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13187-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="13187-110">Child Elements</span></span>  
 <span data-ttu-id="13187-111">No.</span><span class="sxs-lookup"><span data-stu-id="13187-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13187-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="13187-112">Parent Elements</span></span>  
  
|<span data-ttu-id="13187-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="13187-113">Element</span></span>|<span data-ttu-id="13187-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13187-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="13187-115">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="13187-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13187-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="13187-116">Remarks</span></span>  
 <span data-ttu-id="13187-117">Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="13187-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="13187-118">Windows Communication Foundation (WCF) rilascia un nuovo thread per la distribuzione per ogni canale accettato.</span><span class="sxs-lookup"><span data-stu-id="13187-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="13187-119">Se esistono molti canali, sussiste la possibilità di esaurire i thread.</span><span class="sxs-lookup"><span data-stu-id="13187-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13187-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13187-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
