---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 8a8a352380fe6eedb41ead089405e7b79fad29fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272776"
---
# <a name="timeouts"></a><span data-ttu-id="75281-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="75281-101">\<timeOuts></span></span>
<span data-ttu-id="75281-102">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="75281-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="75281-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="75281-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="75281-104">\<client></span><span class="sxs-lookup"><span data-stu-id="75281-104">\<client></span></span>  
<span data-ttu-id="75281-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="75281-105">\<endpoint></span></span>  
<span data-ttu-id="75281-106">\<host></span><span class="sxs-lookup"><span data-stu-id="75281-106">\<host></span></span>  
<span data-ttu-id="75281-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="75281-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75281-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75281-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75281-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75281-109">Attributes and Elements</span></span>  
 <span data-ttu-id="75281-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75281-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75281-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="75281-111">Attributes</span></span>  
  
|<span data-ttu-id="75281-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="75281-112">Attribute</span></span>|<span data-ttu-id="75281-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75281-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="75281-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="75281-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="75281-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="75281-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75281-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75281-116">Child Elements</span></span>  
 <span data-ttu-id="75281-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="75281-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75281-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75281-118">Parent Elements</span></span>  
  
|<span data-ttu-id="75281-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="75281-119">Element</span></span>|<span data-ttu-id="75281-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75281-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75281-121">\<host></span><span class="sxs-lookup"><span data-stu-id="75281-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="75281-122">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="75281-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75281-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75281-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="75281-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="75281-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
