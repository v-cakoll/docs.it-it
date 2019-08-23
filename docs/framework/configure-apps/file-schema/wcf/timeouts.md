---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939191"
---
# <a name="timeouts"></a><span data-ttu-id="27dbd-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="27dbd-101">\<timeOuts></span></span>
<span data-ttu-id="27dbd-102">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="27dbd-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="27dbd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27dbd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="27dbd-104">\<client></span><span class="sxs-lookup"><span data-stu-id="27dbd-104">\<client></span></span>  
<span data-ttu-id="27dbd-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="27dbd-105">\<endpoint></span></span>  
<span data-ttu-id="27dbd-106">\<> host</span><span class="sxs-lookup"><span data-stu-id="27dbd-106">\<host></span></span>  
<span data-ttu-id="27dbd-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="27dbd-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27dbd-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27dbd-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27dbd-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="27dbd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27dbd-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="27dbd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27dbd-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="27dbd-111">Attributes</span></span>  
  
|<span data-ttu-id="27dbd-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="27dbd-112">Attribute</span></span>|<span data-ttu-id="27dbd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27dbd-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="27dbd-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="27dbd-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="27dbd-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="27dbd-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27dbd-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27dbd-116">Child Elements</span></span>  
 <span data-ttu-id="27dbd-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="27dbd-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27dbd-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27dbd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="27dbd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="27dbd-119">Element</span></span>|<span data-ttu-id="27dbd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27dbd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27dbd-121">\<host></span><span class="sxs-lookup"><span data-stu-id="27dbd-121">\<host></span></span>](host.md)|<span data-ttu-id="27dbd-122">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="27dbd-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27dbd-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27dbd-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="27dbd-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="27dbd-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
