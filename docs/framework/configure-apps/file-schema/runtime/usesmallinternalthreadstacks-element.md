---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ee4df12a017429de333dd4e93df27973b658dad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920676"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="473d1-102">\<Elemento > UseSmallInternalThreadStacks</span><span class="sxs-lookup"><span data-stu-id="473d1-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="473d1-103">Richiede che i Common Language Runtime (CLR) riducano l'utilizzo della memoria specificando dimensioni dello stack esplicite quando vengono creati determinati thread utilizzati internamente, anziché utilizzare le dimensioni predefinite dello stack per quei thread.</span><span class="sxs-lookup"><span data-stu-id="473d1-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="473d1-104">\<Configuration >-elemento</span><span class="sxs-lookup"><span data-stu-id="473d1-104">\<configuration> Element</span></span>  
<span data-ttu-id="473d1-105">\<Elemento runtime ></span><span class="sxs-lookup"><span data-stu-id="473d1-105">\<runtime> Element</span></span>  
<span data-ttu-id="473d1-106">\<Elemento > UseSmallInternalThreadStacks</span><span class="sxs-lookup"><span data-stu-id="473d1-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473d1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="473d1-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="473d1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="473d1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="473d1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="473d1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="473d1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="473d1-110">Attributes</span></span>  
  
|<span data-ttu-id="473d1-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="473d1-111">Attribute</span></span>|<span data-ttu-id="473d1-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="473d1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="473d1-113">enabled</span><span class="sxs-lookup"><span data-stu-id="473d1-113">enabled</span></span>|<span data-ttu-id="473d1-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="473d1-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="473d1-115">Specifica se richiedere che CLR usi dimensioni dello stack esplicite invece delle dimensioni predefinite dello stack quando crea determinati thread che usa internamente.</span><span class="sxs-lookup"><span data-stu-id="473d1-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="473d1-116">Le dimensioni dello stack esplicite sono inferiori alle dimensioni predefinite dello stack di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="473d1-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="473d1-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="473d1-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="473d1-118">Valore</span><span class="sxs-lookup"><span data-stu-id="473d1-118">Value</span></span>|<span data-ttu-id="473d1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="473d1-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="473d1-120">true</span><span class="sxs-lookup"><span data-stu-id="473d1-120">true</span></span>|<span data-ttu-id="473d1-121">Richiedere dimensioni dello stack esplicite.</span><span class="sxs-lookup"><span data-stu-id="473d1-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="473d1-122">false</span><span class="sxs-lookup"><span data-stu-id="473d1-122">false</span></span>|<span data-ttu-id="473d1-123">Utilizzare le dimensioni predefinite dello stack.</span><span class="sxs-lookup"><span data-stu-id="473d1-123">Use the default stack size.</span></span> <span data-ttu-id="473d1-124">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="473d1-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="473d1-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="473d1-125">Child Elements</span></span>  
 <span data-ttu-id="473d1-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="473d1-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="473d1-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="473d1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="473d1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="473d1-128">Element</span></span>|<span data-ttu-id="473d1-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="473d1-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="473d1-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="473d1-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="473d1-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="473d1-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="473d1-132">Note</span><span class="sxs-lookup"><span data-stu-id="473d1-132">Remarks</span></span>  
 <span data-ttu-id="473d1-133">Questo elemento di configurazione viene utilizzato per richiedere un utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni dei thread esplicite utilizzate da CLR per i thread interni, se la richiesta viene rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="473d1-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="473d1-134">Questo elemento di configurazione è una richiesta a CLR anziché a un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="473d1-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="473d1-135">Nel .NET Framework 4, la richiesta viene rispettata solo per l'architettura x86.</span><span class="sxs-lookup"><span data-stu-id="473d1-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="473d1-136">Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito dalle dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interni selezionati.</span><span class="sxs-lookup"><span data-stu-id="473d1-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="473d1-137">La specifica di questo elemento di configurazione consente di compromettere l'affidabilità per un utilizzo di memoria virtuale inferiore se CLR rispetta la richiesta, perché le dimensioni dello stack più piccole potrebbero causare un overflow più probabile dello stack.</span><span class="sxs-lookup"><span data-stu-id="473d1-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="473d1-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="473d1-138">Example</span></span>  
 <span data-ttu-id="473d1-139">Nell'esempio seguente viene illustrato come richiedere che CLR utilizzi dimensioni dello stack esplicite per determinati thread utilizzati internamente.</span><span class="sxs-lookup"><span data-stu-id="473d1-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="473d1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="473d1-140">See also</span></span>

- [<span data-ttu-id="473d1-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="473d1-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="473d1-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="473d1-142">Configuration File Schema</span></span>](../index.md)
