---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74678089bb1b19295983064eb7ad54fbf0a1e361
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663382"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="fa146-102">\<Elemento > UseSmallInternalThreadStacks</span><span class="sxs-lookup"><span data-stu-id="fa146-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="fa146-103">Richiede che i Common Language Runtime (CLR) riducano l'utilizzo della memoria specificando dimensioni dello stack esplicite quando vengono creati determinati thread utilizzati internamente, anziché utilizzare le dimensioni predefinite dello stack per quei thread.</span><span class="sxs-lookup"><span data-stu-id="fa146-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="fa146-104">\<Configuration >-elemento</span><span class="sxs-lookup"><span data-stu-id="fa146-104">\<configuration> Element</span></span>  
<span data-ttu-id="fa146-105">\<Elemento runtime ></span><span class="sxs-lookup"><span data-stu-id="fa146-105">\<runtime> Element</span></span>  
<span data-ttu-id="fa146-106">\<Elemento > UseSmallInternalThreadStacks</span><span class="sxs-lookup"><span data-stu-id="fa146-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa146-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa146-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa146-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fa146-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fa146-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fa146-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa146-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fa146-110">Attributes</span></span>  
  
|<span data-ttu-id="fa146-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="fa146-111">Attribute</span></span>|<span data-ttu-id="fa146-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa146-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa146-113">enabled</span><span class="sxs-lookup"><span data-stu-id="fa146-113">enabled</span></span>|<span data-ttu-id="fa146-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa146-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="fa146-115">Specifica se richiedere che CLR usi dimensioni dello stack esplicite invece delle dimensioni predefinite dello stack quando crea determinati thread che usa internamente.</span><span class="sxs-lookup"><span data-stu-id="fa146-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="fa146-116">Le dimensioni dello stack esplicite sono inferiori alle dimensioni predefinite dello stack di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="fa146-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fa146-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="fa146-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="fa146-118">Valore</span><span class="sxs-lookup"><span data-stu-id="fa146-118">Value</span></span>|<span data-ttu-id="fa146-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa146-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa146-120">true</span><span class="sxs-lookup"><span data-stu-id="fa146-120">true</span></span>|<span data-ttu-id="fa146-121">Richiedere dimensioni dello stack esplicite.</span><span class="sxs-lookup"><span data-stu-id="fa146-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="fa146-122">false</span><span class="sxs-lookup"><span data-stu-id="fa146-122">false</span></span>|<span data-ttu-id="fa146-123">Utilizzare le dimensioni predefinite dello stack.</span><span class="sxs-lookup"><span data-stu-id="fa146-123">Use the default stack size.</span></span> <span data-ttu-id="fa146-124">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa146-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa146-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fa146-125">Child Elements</span></span>  
 <span data-ttu-id="fa146-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fa146-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa146-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fa146-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fa146-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa146-128">Element</span></span>|<span data-ttu-id="fa146-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa146-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa146-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa146-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fa146-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fa146-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa146-132">Note</span><span class="sxs-lookup"><span data-stu-id="fa146-132">Remarks</span></span>  
 <span data-ttu-id="fa146-133">Questo elemento di configurazione viene utilizzato per richiedere un utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni dei thread esplicite utilizzate da CLR per i thread interni, se la richiesta viene rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="fa146-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa146-134">Questo elemento di configurazione è una richiesta a CLR anziché a un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="fa146-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="fa146-135">Nel .NET Framework 4, la richiesta viene rispettata solo per l'architettura x86.</span><span class="sxs-lookup"><span data-stu-id="fa146-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="fa146-136">Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito dalle dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interni selezionati.</span><span class="sxs-lookup"><span data-stu-id="fa146-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="fa146-137">La specifica di questo elemento di configurazione consente di compromettere l'affidabilità per un utilizzo di memoria virtuale inferiore se CLR rispetta la richiesta, perché le dimensioni dello stack più piccole potrebbero causare un overflow più probabile dello stack.</span><span class="sxs-lookup"><span data-stu-id="fa146-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa146-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa146-138">Example</span></span>  
 <span data-ttu-id="fa146-139">Nell'esempio seguente viene illustrato come richiedere che CLR utilizzi dimensioni dello stack esplicite per determinati thread utilizzati internamente.</span><span class="sxs-lookup"><span data-stu-id="fa146-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa146-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa146-140">See also</span></span>

- [<span data-ttu-id="fa146-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="fa146-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fa146-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="fa146-142">Configuration File Schema</span></span>](../index.md)
