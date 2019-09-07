---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400562"
---
# <a name="callbackdebug"></a><span data-ttu-id="30edc-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="30edc-101">\<callbackDebug></span></span>
<span data-ttu-id="30edc-102">Specifica il debug del servizio per un oggetto callback di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="30edc-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="30edc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30edc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30edc-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="30edc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="30edc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30edc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="30edc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30edc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="30edc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30edc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="30edc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> callbackDebug**</span><span class="sxs-lookup"><span data-stu-id="30edc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30edc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30edc-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="30edc-110">Type</span><span class="sxs-lookup"><span data-stu-id="30edc-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30edc-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30edc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="30edc-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30edc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30edc-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="30edc-113">Attributes</span></span>  
  
|<span data-ttu-id="30edc-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="30edc-114">Attribute</span></span>|<span data-ttu-id="30edc-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30edc-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="30edc-116">Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="30edc-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="30edc-117">Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="30edc-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="30edc-118">**Attenzione:**  La restituzione ai client di informazioni sulle eccezioni gestite può costituire un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="30edc-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="30edc-119">Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="30edc-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30edc-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30edc-120">Child Elements</span></span>  
 <span data-ttu-id="30edc-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="30edc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30edc-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30edc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="30edc-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="30edc-123">Element</span></span>|<span data-ttu-id="30edc-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30edc-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30edc-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="30edc-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="30edc-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="30edc-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30edc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30edc-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
