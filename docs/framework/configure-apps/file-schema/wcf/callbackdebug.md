---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 5bd2356c3bb798e948341cb3c4ba504ac886ed44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145081"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="e51c1-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="e51c1-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="e51c1-103">Specifica il debug del servizio per un oggetto di callback Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e51c1-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="e51c1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e51c1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e51c1-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e51c1-105">\<behaviors></span></span>  
<span data-ttu-id="e51c1-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e51c1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e51c1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e51c1-107">\<behavior></span></span>  
<span data-ttu-id="e51c1-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="e51c1-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e51c1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e51c1-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="e51c1-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="e51c1-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e51c1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e51c1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e51c1-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e51c1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e51c1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e51c1-113">Attributes</span></span>  
  
|<span data-ttu-id="e51c1-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e51c1-114">Attribute</span></span>|<span data-ttu-id="e51c1-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e51c1-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="e51c1-116">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="e51c1-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="e51c1-117">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="e51c1-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="e51c1-118">**Attenzione:**  La restituzione ai client di informazioni sulle eccezioni gestite può costituire un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e51c1-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="e51c1-119">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="e51c1-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e51c1-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e51c1-120">Child Elements</span></span>  
 <span data-ttu-id="e51c1-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e51c1-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e51c1-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e51c1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e51c1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e51c1-123">Element</span></span>|<span data-ttu-id="e51c1-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e51c1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e51c1-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e51c1-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e51c1-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e51c1-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e51c1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e51c1-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
