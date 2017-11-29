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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 93b89787795cb58644b79ae4795e7a036741e138
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="ab2e3-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="ab2e3-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="ab2e3-103">Specifica il debug del servizio per un oggetto di callback [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab2e3-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="ab2e3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ab2e3-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-105">\<behaviors></span></span>  
<span data-ttu-id="ab2e3-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ab2e3-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-107">\<behavior></span></span>  
<span data-ttu-id="ab2e3-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab2e3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab2e3-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="ab2e3-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab2e3-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab2e3-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ab2e3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ab2e3-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab2e3-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ab2e3-113">Attributes</span></span>  
  
|<span data-ttu-id="ab2e3-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ab2e3-114">Attribute</span></span>|<span data-ttu-id="ab2e3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab2e3-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="ab2e3-116">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="ab2e3-117">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="ab2e3-118">**Attenzione:** la restituzione ai client informazioni sulle eccezioni gestite può costituire un rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="ab2e3-119">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab2e3-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ab2e3-120">Child Elements</span></span>  
 <span data-ttu-id="ab2e3-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab2e3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ab2e3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ab2e3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab2e3-123">Element</span></span>|<span data-ttu-id="ab2e3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab2e3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab2e3-125">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ab2e3-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ab2e3-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab2e3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab2e3-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
