---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118066"
---
# <a name="timeouts"></a><span data-ttu-id="30b90-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="30b90-101">\<timeOuts></span></span>
<span data-ttu-id="30b90-102">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="30b90-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="30b90-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="30b90-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="30b90-104">\<client></span><span class="sxs-lookup"><span data-stu-id="30b90-104">\<client></span></span>  
<span data-ttu-id="30b90-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="30b90-105">\<endpoint></span></span>  
<span data-ttu-id="30b90-106">\<host></span><span class="sxs-lookup"><span data-stu-id="30b90-106">\<host></span></span>  
<span data-ttu-id="30b90-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="30b90-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b90-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30b90-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30b90-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30b90-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30b90-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30b90-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30b90-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="30b90-111">Attributes</span></span>  
  
|<span data-ttu-id="30b90-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="30b90-112">Attribute</span></span>|<span data-ttu-id="30b90-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30b90-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="30b90-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="30b90-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="30b90-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="30b90-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30b90-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30b90-116">Child Elements</span></span>  
 <span data-ttu-id="30b90-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="30b90-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30b90-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30b90-118">Parent Elements</span></span>  
  
|<span data-ttu-id="30b90-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="30b90-119">Element</span></span>|<span data-ttu-id="30b90-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30b90-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30b90-121">\<host></span><span class="sxs-lookup"><span data-stu-id="30b90-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="30b90-122">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="30b90-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30b90-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b90-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="30b90-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="30b90-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
