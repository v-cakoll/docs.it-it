---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 01932fe2b7b7e699311e2c65ec8adaf0aef82dc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557903"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="7a519-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="7a519-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="7a519-103">Specifica il valore di timeout durante la propagazione delle transazioni dal server al client in un scenario di contratto di callback duplex.</span><span class="sxs-lookup"><span data-stu-id="7a519-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="7a519-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7a519-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7a519-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7a519-105">\<behaviors></span></span>  
<span data-ttu-id="7a519-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7a519-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7a519-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7a519-107">\<behavior></span></span>  
<span data-ttu-id="7a519-108">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="7a519-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a519-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a519-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="7a519-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="7a519-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a519-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7a519-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7a519-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7a519-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a519-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a519-113">Attributes</span></span>  
  
|<span data-ttu-id="7a519-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7a519-114">Attribute</span></span>|<span data-ttu-id="7a519-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a519-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="7a519-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale le transazioni devono essere completate o interrotte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a519-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="7a519-117">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="7a519-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a519-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a519-118">Child Elements</span></span>  
 <span data-ttu-id="7a519-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7a519-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a519-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7a519-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a519-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a519-121">Element</span></span>|<span data-ttu-id="7a519-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a519-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a519-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7a519-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7a519-124">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7a519-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a519-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a519-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
