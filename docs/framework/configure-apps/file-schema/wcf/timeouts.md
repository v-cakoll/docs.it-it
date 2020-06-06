---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854973"
---
# \<timeOuts>
<span data-ttu-id="fffeb-101">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fffeb-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="fffeb-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fffeb-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fffeb-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fffeb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="fffeb-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fffeb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fffeb-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="fffeb-105">Attributes</span></span>  
  
|<span data-ttu-id="fffeb-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="fffeb-106">Attribute</span></span>|<span data-ttu-id="fffeb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fffeb-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="fffeb-108">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fffeb-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="fffeb-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fffeb-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fffeb-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fffeb-110">Child Elements</span></span>  
 <span data-ttu-id="fffeb-111">No.</span><span class="sxs-lookup"><span data-stu-id="fffeb-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fffeb-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fffeb-112">Parent Elements</span></span>  
  
|<span data-ttu-id="fffeb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fffeb-113">Element</span></span>|<span data-ttu-id="fffeb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fffeb-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="fffeb-115">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fffeb-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fffeb-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fffeb-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="fffeb-117">Hosting</span><span class="sxs-lookup"><span data-stu-id="fffeb-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
