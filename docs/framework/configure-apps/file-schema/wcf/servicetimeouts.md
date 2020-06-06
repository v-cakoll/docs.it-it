---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399555"
---
# \<serviceTimeouts>
<span data-ttu-id="34eae-101">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="34eae-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="34eae-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34eae-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="34eae-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="34eae-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34eae-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="34eae-104">Attributes and Elements</span></span>  
 <span data-ttu-id="34eae-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="34eae-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34eae-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="34eae-106">Attributes</span></span>  
  
|<span data-ttu-id="34eae-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="34eae-107">Attribute</span></span>|<span data-ttu-id="34eae-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34eae-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="34eae-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="34eae-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="34eae-110">Il valore predefinito è "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="34eae-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34eae-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34eae-111">Child Elements</span></span>  
 <span data-ttu-id="34eae-112">No.</span><span class="sxs-lookup"><span data-stu-id="34eae-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34eae-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="34eae-113">Parent Elements</span></span>  
  
|<span data-ttu-id="34eae-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="34eae-114">Element</span></span>|<span data-ttu-id="34eae-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34eae-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="34eae-116">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="34eae-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34eae-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34eae-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
