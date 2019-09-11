---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854973"
---
# <a name="timeouts"></a><span data-ttu-id="782c7-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="782c7-101">\<timeOuts></span></span>
<span data-ttu-id="782c7-102">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="782c7-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="782c7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="782c7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="782c7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="782c7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="782c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dei servizi**](services.md)</span><span class="sxs-lookup"><span data-stu-id="782c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="782c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del servizio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="782c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="782c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> host**](host.md)</span><span class="sxs-lookup"><span data-stu-id="782c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="782c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<timeOut >**</span><span class="sxs-lookup"><span data-stu-id="782c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782c7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="782c7-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="782c7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="782c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="782c7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="782c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="782c7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="782c7-112">Attributes</span></span>  
  
|<span data-ttu-id="782c7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="782c7-113">Attribute</span></span>|<span data-ttu-id="782c7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="782c7-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="782c7-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="782c7-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="782c7-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="782c7-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="782c7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="782c7-117">Child Elements</span></span>  
 <span data-ttu-id="782c7-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="782c7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="782c7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="782c7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="782c7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="782c7-120">Element</span></span>|<span data-ttu-id="782c7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="782c7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="782c7-122">\<host></span><span class="sxs-lookup"><span data-stu-id="782c7-122">\<host></span></span>](host.md)|<span data-ttu-id="782c7-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="782c7-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="782c7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="782c7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="782c7-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="782c7-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
