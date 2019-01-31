---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 62ce1bc179c7215d4988e4c6bda08025c3d3e5de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286312"
---
# <a name="callbackdebug"></a><span data-ttu-id="15da4-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="15da4-101">\<callbackDebug></span></span>
<span data-ttu-id="15da4-102">Specifica il debug del servizio per un oggetto di callback Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="15da4-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="15da4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="15da4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="15da4-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="15da4-104">\<behaviors></span></span>  
<span data-ttu-id="15da4-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="15da4-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="15da4-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15da4-106">\<behavior></span></span>  
<span data-ttu-id="15da4-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="15da4-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15da4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15da4-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="15da4-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="15da4-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15da4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="15da4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="15da4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="15da4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15da4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="15da4-112">Attributes</span></span>  
  
|<span data-ttu-id="15da4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="15da4-113">Attribute</span></span>|<span data-ttu-id="15da4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15da4-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="15da4-115">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="15da4-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="15da4-116">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="15da4-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="15da4-117">**Attenzione:**  La restituzione ai client di informazioni sulle eccezioni gestite può costituire un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="15da4-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="15da4-118">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="15da4-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15da4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="15da4-119">Child Elements</span></span>  
 <span data-ttu-id="15da4-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="15da4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15da4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="15da4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="15da4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="15da4-122">Element</span></span>|<span data-ttu-id="15da4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15da4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15da4-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15da4-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="15da4-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="15da4-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15da4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15da4-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
