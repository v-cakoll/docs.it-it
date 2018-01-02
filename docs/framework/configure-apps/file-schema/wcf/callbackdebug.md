---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccb48efcdd1924ade27220a685e146a7f5eeef76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="2783f-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="2783f-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="2783f-103">Specifica il debug del servizio per un oggetto di callback [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2783f-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="2783f-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2783f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2783f-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="2783f-105">\<behaviors></span></span>  
<span data-ttu-id="2783f-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2783f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2783f-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2783f-107">\<behavior></span></span>  
<span data-ttu-id="2783f-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="2783f-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2783f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2783f-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="2783f-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="2783f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2783f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2783f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2783f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2783f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2783f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2783f-113">Attributes</span></span>  
  
|<span data-ttu-id="2783f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2783f-114">Attribute</span></span>|<span data-ttu-id="2783f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2783f-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="2783f-116">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="2783f-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="2783f-117">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="2783f-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="2783f-118">**Attenzione:** la restituzione ai client informazioni sulle eccezioni gestite può costituire un rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2783f-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="2783f-119">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2783f-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2783f-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2783f-120">Child Elements</span></span>  
 <span data-ttu-id="2783f-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2783f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2783f-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2783f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2783f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2783f-123">Element</span></span>|<span data-ttu-id="2783f-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2783f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2783f-125">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2783f-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2783f-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2783f-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2783f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2783f-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
