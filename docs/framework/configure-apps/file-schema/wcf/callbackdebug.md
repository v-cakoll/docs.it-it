---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152269"
---
# <a name="callbackdebug"></a><span data-ttu-id="2b464-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="2b464-101">\<callbackDebug></span></span>
<span data-ttu-id="2b464-102">Specifica il debug del servizio per un oggetto di callback Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2b464-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="2b464-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2b464-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2b464-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2b464-104">\<behaviors></span></span>  
<span data-ttu-id="2b464-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2b464-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2b464-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2b464-106">\<behavior></span></span>  
<span data-ttu-id="2b464-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="2b464-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b464-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b464-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="2b464-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="2b464-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b464-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b464-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2b464-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b464-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b464-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b464-112">Attributes</span></span>  
  
|<span data-ttu-id="2b464-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2b464-113">Attribute</span></span>|<span data-ttu-id="2b464-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b464-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="2b464-115">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="2b464-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="2b464-116">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="2b464-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="2b464-117">**Attenzione:**  La restituzione ai client di informazioni sulle eccezioni gestite può costituire un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2b464-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="2b464-118">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2b464-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b464-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b464-119">Child Elements</span></span>  
 <span data-ttu-id="2b464-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2b464-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b464-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b464-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2b464-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b464-122">Element</span></span>|<span data-ttu-id="2b464-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b464-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b464-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2b464-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2b464-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b464-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b464-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b464-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
