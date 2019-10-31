---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 2fd776ce8605e6dcf288dcb3852ded16638a1873
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114929"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="13dc5-102">\<elemento > UseSmallInternalThreadStacks</span><span class="sxs-lookup"><span data-stu-id="13dc5-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="13dc5-103">Richiede che i Common Language Runtime (CLR) riducano l'utilizzo della memoria specificando dimensioni dello stack esplicite quando vengono creati determinati thread utilizzati internamente, anziché utilizzare le dimensioni predefinite dello stack per quei thread.</span><span class="sxs-lookup"><span data-stu-id="13dc5-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
<span data-ttu-id="13dc5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13dc5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13dc5-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="13dc5-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="13dc5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseSmallInternalThreadStacks >**</span><span class="sxs-lookup"><span data-stu-id="13dc5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13dc5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13dc5-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13dc5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="13dc5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="13dc5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="13dc5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13dc5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="13dc5-110">Attributes</span></span>  
  
|<span data-ttu-id="13dc5-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="13dc5-111">Attribute</span></span>|<span data-ttu-id="13dc5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13dc5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13dc5-113">enabled</span><span class="sxs-lookup"><span data-stu-id="13dc5-113">enabled</span></span>|<span data-ttu-id="13dc5-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13dc5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="13dc5-115">Specifica se richiedere che CLR usi dimensioni dello stack esplicite invece delle dimensioni predefinite dello stack quando crea determinati thread che usa internamente.</span><span class="sxs-lookup"><span data-stu-id="13dc5-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="13dc5-116">Le dimensioni dello stack esplicite sono inferiori alle dimensioni predefinite dello stack di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="13dc5-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="13dc5-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="13dc5-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="13dc5-118">Value</span><span class="sxs-lookup"><span data-stu-id="13dc5-118">Value</span></span>|<span data-ttu-id="13dc5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13dc5-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13dc5-120">true</span><span class="sxs-lookup"><span data-stu-id="13dc5-120">true</span></span>|<span data-ttu-id="13dc5-121">Richiedere dimensioni dello stack esplicite.</span><span class="sxs-lookup"><span data-stu-id="13dc5-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="13dc5-122">False</span><span class="sxs-lookup"><span data-stu-id="13dc5-122">false</span></span>|<span data-ttu-id="13dc5-123">Utilizzare le dimensioni predefinite dello stack.</span><span class="sxs-lookup"><span data-stu-id="13dc5-123">Use the default stack size.</span></span> <span data-ttu-id="13dc5-124">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="13dc5-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13dc5-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="13dc5-125">Child Elements</span></span>  
 <span data-ttu-id="13dc5-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="13dc5-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13dc5-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="13dc5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="13dc5-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="13dc5-128">Element</span></span>|<span data-ttu-id="13dc5-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13dc5-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="13dc5-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="13dc5-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="13dc5-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="13dc5-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13dc5-132">Note</span><span class="sxs-lookup"><span data-stu-id="13dc5-132">Remarks</span></span>  
 <span data-ttu-id="13dc5-133">Questo elemento di configurazione viene utilizzato per richiedere un utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni dei thread esplicite utilizzate da CLR per i thread interni, se la richiesta viene rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="13dc5-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="13dc5-134">Questo elemento di configurazione è una richiesta a CLR anziché a un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="13dc5-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="13dc5-135">Nel .NET Framework 4, la richiesta viene rispettata solo per l'architettura x86.</span><span class="sxs-lookup"><span data-stu-id="13dc5-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="13dc5-136">Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito dalle dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interni selezionati.</span><span class="sxs-lookup"><span data-stu-id="13dc5-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="13dc5-137">La specifica di questo elemento di configurazione consente di compromettere l'affidabilità per un utilizzo di memoria virtuale inferiore se CLR rispetta la richiesta, perché le dimensioni dello stack più piccole potrebbero causare un overflow più probabile dello stack.</span><span class="sxs-lookup"><span data-stu-id="13dc5-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13dc5-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="13dc5-138">Example</span></span>  
 <span data-ttu-id="13dc5-139">Nell'esempio seguente viene illustrato come richiedere che CLR utilizzi dimensioni dello stack esplicite per determinati thread utilizzati internamente.</span><span class="sxs-lookup"><span data-stu-id="13dc5-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13dc5-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13dc5-140">See also</span></span>

- [<span data-ttu-id="13dc5-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="13dc5-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="13dc5-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="13dc5-142">Configuration File Schema</span></span>](../index.md)
