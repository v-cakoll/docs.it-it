---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 269500324ad1beaa0b519fa17d251ee942276faa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269068"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="2d94a-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="2d94a-101">\<callbackTimeouts></span></span>
<span data-ttu-id="2d94a-102">Specifica il valore di timeout durante la propagazione delle transazioni dal server al client in un scenario di contratto di callback duplex.</span><span class="sxs-lookup"><span data-stu-id="2d94a-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="2d94a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d94a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d94a-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2d94a-104">\<behaviors></span></span>  
<span data-ttu-id="2d94a-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2d94a-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2d94a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d94a-106">\<behavior></span></span>  
<span data-ttu-id="2d94a-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="2d94a-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d94a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d94a-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="2d94a-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="2d94a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d94a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2d94a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d94a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2d94a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d94a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2d94a-112">Attributes</span></span>  
  
|<span data-ttu-id="2d94a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2d94a-113">Attribute</span></span>|<span data-ttu-id="2d94a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d94a-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="2d94a-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale le transazioni devono essere completate o interrotte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2d94a-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="2d94a-116">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="2d94a-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d94a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2d94a-117">Child Elements</span></span>  
 <span data-ttu-id="2d94a-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2d94a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d94a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2d94a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2d94a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d94a-120">Element</span></span>|<span data-ttu-id="2d94a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d94a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d94a-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d94a-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2d94a-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2d94a-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d94a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d94a-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
