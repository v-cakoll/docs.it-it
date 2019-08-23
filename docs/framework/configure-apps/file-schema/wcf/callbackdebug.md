---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926314"
---
# <a name="callbackdebug"></a><span data-ttu-id="91f68-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="91f68-101">\<callbackDebug></span></span>
<span data-ttu-id="91f68-102">Specifica il debug del servizio per un oggetto callback di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="91f68-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="91f68-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91f68-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="91f68-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="91f68-104">\<behaviors></span></span>  
<span data-ttu-id="91f68-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="91f68-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="91f68-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="91f68-106">\<behavior></span></span>  
<span data-ttu-id="91f68-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="91f68-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f68-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91f68-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="91f68-109">Type</span><span class="sxs-lookup"><span data-stu-id="91f68-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91f68-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91f68-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91f68-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91f68-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91f68-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="91f68-112">Attributes</span></span>  
  
|<span data-ttu-id="91f68-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="91f68-113">Attribute</span></span>|<span data-ttu-id="91f68-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91f68-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="91f68-115">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="91f68-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="91f68-116">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="91f68-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="91f68-117">**Attenzione:**  La restituzione ai client di informazioni sulle eccezioni gestite può costituire un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="91f68-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="91f68-118">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="91f68-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91f68-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91f68-119">Child Elements</span></span>  
 <span data-ttu-id="91f68-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="91f68-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91f68-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91f68-121">Parent Elements</span></span>  
  
|<span data-ttu-id="91f68-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="91f68-122">Element</span></span>|<span data-ttu-id="91f68-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91f68-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91f68-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="91f68-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="91f68-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="91f68-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91f68-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91f68-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
