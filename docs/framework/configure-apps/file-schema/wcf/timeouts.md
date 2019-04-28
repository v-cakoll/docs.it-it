---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758223"
---
# <a name="timeouts"></a><span data-ttu-id="57ccc-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="57ccc-101">\<timeOuts></span></span>
<span data-ttu-id="57ccc-102">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="57ccc-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="57ccc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="57ccc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="57ccc-104">\<client></span><span class="sxs-lookup"><span data-stu-id="57ccc-104">\<client></span></span>  
<span data-ttu-id="57ccc-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="57ccc-105">\<endpoint></span></span>  
<span data-ttu-id="57ccc-106">\<host></span><span class="sxs-lookup"><span data-stu-id="57ccc-106">\<host></span></span>  
<span data-ttu-id="57ccc-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="57ccc-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57ccc-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57ccc-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57ccc-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57ccc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57ccc-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57ccc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57ccc-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="57ccc-111">Attributes</span></span>  
  
|<span data-ttu-id="57ccc-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="57ccc-112">Attribute</span></span>|<span data-ttu-id="57ccc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57ccc-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="57ccc-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="57ccc-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="57ccc-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="57ccc-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57ccc-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57ccc-116">Child Elements</span></span>  
 <span data-ttu-id="57ccc-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="57ccc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57ccc-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57ccc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="57ccc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="57ccc-119">Element</span></span>|<span data-ttu-id="57ccc-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57ccc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57ccc-121">\<host></span><span class="sxs-lookup"><span data-stu-id="57ccc-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="57ccc-122">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="57ccc-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57ccc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57ccc-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="57ccc-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="57ccc-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
