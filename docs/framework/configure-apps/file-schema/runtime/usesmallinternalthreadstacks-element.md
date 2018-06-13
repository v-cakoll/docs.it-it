---
title: '&lt;UseSmallInternalThreadStacks&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a11b9a008878e716e9b3d8cd54abe5eb4169672a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745487"
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a><span data-ttu-id="02b95-102">&lt;UseSmallInternalThreadStacks&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="02b95-102">&lt;UseSmallInternalThreadStacks&gt; Element</span></span>
<span data-ttu-id="02b95-103">Le richieste che common language runtime (CLR) ridurre la memoria utilizzano specificando le dimensioni dello stack esplicita quando crea determinati thread che utilizza internamente, anziché utilizzare la dimensione predefinita per tali thread.</span><span class="sxs-lookup"><span data-stu-id="02b95-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="02b95-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="02b95-104">\<configuration> Element</span></span>  
<span data-ttu-id="02b95-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="02b95-105">\<runtime> Element</span></span>  
<span data-ttu-id="02b95-106">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="02b95-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b95-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02b95-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02b95-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02b95-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02b95-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02b95-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02b95-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="02b95-110">Attributes</span></span>  
  
|<span data-ttu-id="02b95-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="02b95-111">Attribute</span></span>|<span data-ttu-id="02b95-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b95-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02b95-113">enabled</span><span class="sxs-lookup"><span data-stu-id="02b95-113">enabled</span></span>|<span data-ttu-id="02b95-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="02b95-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="02b95-115">Specifica se richiedere che le dimensioni dello stack esplicita uso CLR anziché la dimensione predefinita quando si crea determinati thread che utilizza internamente.</span><span class="sxs-lookup"><span data-stu-id="02b95-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="02b95-116">Le dimensioni dello stack esplicita sono inferiori alle dimensioni dello stack predefinito di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="02b95-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="02b95-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="02b95-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="02b95-118">Valore</span><span class="sxs-lookup"><span data-stu-id="02b95-118">Value</span></span>|<span data-ttu-id="02b95-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b95-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02b95-120">true</span><span class="sxs-lookup"><span data-stu-id="02b95-120">true</span></span>|<span data-ttu-id="02b95-121">Le dimensioni dello stack esplicita della richiesta.</span><span class="sxs-lookup"><span data-stu-id="02b95-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="02b95-122">False</span><span class="sxs-lookup"><span data-stu-id="02b95-122">false</span></span>|<span data-ttu-id="02b95-123">Utilizzare la dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="02b95-123">Use the default stack size.</span></span> <span data-ttu-id="02b95-124">Questo è il valore predefinito per il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02b95-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02b95-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02b95-125">Child Elements</span></span>  
 <span data-ttu-id="02b95-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="02b95-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02b95-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02b95-127">Parent Elements</span></span>  
  
|<span data-ttu-id="02b95-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="02b95-128">Element</span></span>|<span data-ttu-id="02b95-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b95-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02b95-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02b95-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02b95-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02b95-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02b95-132">Note</span><span class="sxs-lookup"><span data-stu-id="02b95-132">Remarks</span></span>  
 <span data-ttu-id="02b95-133">Questo elemento di configurazione viene utilizzato per richiedere l'utilizzo ridotto della memoria virtuale in un processo, poiché le dimensioni di esplicita di thread usati da CLR per i thread interni, se la richiesta è stata rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="02b95-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02b95-134">Questo elemento di configurazione è una richiesta di CLR anziché un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="02b95-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="02b95-135">Nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la richiesta viene rispettata solo per x86 architettura.</span><span class="sxs-lookup"><span data-stu-id="02b95-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="02b95-136">Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito da dimensioni dello stack esplicite che vengono sempre utilizzate per thread interni selezionati.</span><span class="sxs-lookup"><span data-stu-id="02b95-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="02b95-137">Specificare che questo elemento di configurazione negozia l'affidabilità di minore utilizzo della memoria virtuale se CLR soddisfa la richiesta, perché le dimensioni dello stack più piccole potrebbe potenzialmente stack overflow più probabile.</span><span class="sxs-lookup"><span data-stu-id="02b95-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b95-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="02b95-138">Example</span></span>  
 <span data-ttu-id="02b95-139">Nell'esempio seguente viene illustrato come richiedere che il Common Language Runtime Usa dimensioni esplicite dello stack per determinati thread che utilizza internamente.</span><span class="sxs-lookup"><span data-stu-id="02b95-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02b95-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02b95-140">See Also</span></span>  
 [<span data-ttu-id="02b95-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="02b95-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="02b95-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="02b95-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
