---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9833d768b84faaf6e1dcf8c9cb8b00b92adc3d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144826"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="6defd-102">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="6defd-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="6defd-103">Le richieste che common language runtime (CLR) ridurre la memoria usano specificando le dimensioni dello stack esplicite quando crea determinati thread usati internamente, invece di usare le dimensioni predefinite dello stack per tali thread.</span><span class="sxs-lookup"><span data-stu-id="6defd-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="6defd-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="6defd-104">\<configuration> Element</span></span>  
<span data-ttu-id="6defd-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="6defd-105">\<runtime> Element</span></span>  
<span data-ttu-id="6defd-106">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="6defd-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6defd-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6defd-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6defd-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6defd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6defd-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6defd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6defd-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6defd-110">Attributes</span></span>  
  
|<span data-ttu-id="6defd-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6defd-111">Attribute</span></span>|<span data-ttu-id="6defd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6defd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6defd-113">enabled</span><span class="sxs-lookup"><span data-stu-id="6defd-113">enabled</span></span>|<span data-ttu-id="6defd-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6defd-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6defd-115">Specifica se richiedere che le dimensioni dello stack esplicita utilizzare CLR anziché le dimensioni predefinite dello stack quando crea determinati thread usati internamente.</span><span class="sxs-lookup"><span data-stu-id="6defd-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="6defd-116">Le dimensioni dello stack esplicita sono inferiori alle dimensioni dello stack predefinito pari a 1 MB.</span><span class="sxs-lookup"><span data-stu-id="6defd-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6defd-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="6defd-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="6defd-118">Valore</span><span class="sxs-lookup"><span data-stu-id="6defd-118">Value</span></span>|<span data-ttu-id="6defd-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6defd-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6defd-120">true</span><span class="sxs-lookup"><span data-stu-id="6defd-120">true</span></span>|<span data-ttu-id="6defd-121">Le dimensioni dello stack esplicita della richiesta.</span><span class="sxs-lookup"><span data-stu-id="6defd-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="6defd-122">False</span><span class="sxs-lookup"><span data-stu-id="6defd-122">false</span></span>|<span data-ttu-id="6defd-123">Usare le dimensioni predefinite dello stack.</span><span class="sxs-lookup"><span data-stu-id="6defd-123">Use the default stack size.</span></span> <span data-ttu-id="6defd-124">Questo è il valore predefinito per il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6defd-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6defd-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6defd-125">Child Elements</span></span>  
 <span data-ttu-id="6defd-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6defd-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6defd-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6defd-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6defd-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="6defd-128">Element</span></span>|<span data-ttu-id="6defd-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6defd-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6defd-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6defd-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6defd-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6defd-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6defd-132">Note</span><span class="sxs-lookup"><span data-stu-id="6defd-132">Remarks</span></span>  
 <span data-ttu-id="6defd-133">Questo elemento di configurazione viene usato per richiedere l'utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni di thread espliciti usati da CLR per i thread interni, se la richiesta verrà rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="6defd-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6defd-134">Questo elemento di configurazione è una richiesta a Common Language Runtime anziché a un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="6defd-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="6defd-135">Nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la richiesta verrà rispettata solo per x86 architettura.</span><span class="sxs-lookup"><span data-stu-id="6defd-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="6defd-136">Questo elemento potrebbe essere completamente ignorato nelle versioni future di CLR o sostituito da dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interno selezionato.</span><span class="sxs-lookup"><span data-stu-id="6defd-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="6defd-137">Specifica di che questo elemento di configurazione è necessaria una affidabilità per l'utilizzo di memoria virtuale più piccolo se CLR soddisfa la richiesta, perché di dimensioni inferiori dello stack potrebbe potenzialmente stack overflow più probabile.</span><span class="sxs-lookup"><span data-stu-id="6defd-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6defd-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="6defd-138">Example</span></span>  
 <span data-ttu-id="6defd-139">Nell'esempio seguente viene illustrato come richiedere che il CLR Usa dimensioni esplicite dello stack per determinati thread usati internamente.</span><span class="sxs-lookup"><span data-stu-id="6defd-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6defd-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6defd-140">See also</span></span>

- [<span data-ttu-id="6defd-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6defd-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6defd-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6defd-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
