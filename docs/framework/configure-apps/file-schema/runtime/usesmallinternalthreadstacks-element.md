---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 2fd776ce8605e6dcf288dcb3852ded16638a1873
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73114929"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="0482d-102">\<UseSmallInternalThreadStacks> Elemento</span><span class="sxs-lookup"><span data-stu-id="0482d-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="0482d-103">Richiede che i Common Language Runtime (CLR) riducano l'utilizzo della memoria specificando dimensioni dello stack esplicite quando vengono creati determinati thread utilizzati internamente, anziché utilizzare le dimensioni predefinite dello stack per quei thread.</span><span class="sxs-lookup"><span data-stu-id="0482d-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a><span data-ttu-id="0482d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0482d-104">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0482d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0482d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0482d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0482d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0482d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0482d-107">Attributes</span></span>  
  
|<span data-ttu-id="0482d-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0482d-108">Attribute</span></span>|<span data-ttu-id="0482d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0482d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0482d-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="0482d-110">enabled</span></span>|<span data-ttu-id="0482d-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0482d-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="0482d-112">Specifica se richiedere che CLR usi dimensioni dello stack esplicite invece delle dimensioni predefinite dello stack quando crea determinati thread che usa internamente.</span><span class="sxs-lookup"><span data-stu-id="0482d-112">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="0482d-113">Le dimensioni dello stack esplicite sono inferiori alle dimensioni predefinite dello stack di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="0482d-113">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0482d-114">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0482d-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="0482d-115">Valore</span><span class="sxs-lookup"><span data-stu-id="0482d-115">Value</span></span>|<span data-ttu-id="0482d-116">Description</span><span class="sxs-lookup"><span data-stu-id="0482d-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0482d-117">true</span><span class="sxs-lookup"><span data-stu-id="0482d-117">true</span></span>|<span data-ttu-id="0482d-118">Richiedere dimensioni dello stack esplicite.</span><span class="sxs-lookup"><span data-stu-id="0482d-118">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="0482d-119">false</span><span class="sxs-lookup"><span data-stu-id="0482d-119">false</span></span>|<span data-ttu-id="0482d-120">Utilizzare le dimensioni predefinite dello stack.</span><span class="sxs-lookup"><span data-stu-id="0482d-120">Use the default stack size.</span></span> <span data-ttu-id="0482d-121">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0482d-121">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0482d-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0482d-122">Child Elements</span></span>  
 <span data-ttu-id="0482d-123">No.</span><span class="sxs-lookup"><span data-stu-id="0482d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0482d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0482d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0482d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0482d-125">Element</span></span>|<span data-ttu-id="0482d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0482d-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0482d-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0482d-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0482d-128">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0482d-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0482d-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="0482d-129">Remarks</span></span>  
 <span data-ttu-id="0482d-130">Questo elemento di configurazione viene utilizzato per richiedere un utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni dei thread esplicite utilizzate da CLR per i thread interni, se la richiesta viene rispettata, sono inferiori alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="0482d-130">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0482d-131">Questo elemento di configurazione è una richiesta a CLR anziché a un requisito assoluto.</span><span class="sxs-lookup"><span data-stu-id="0482d-131">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="0482d-132">Nel .NET Framework 4, la richiesta viene rispettata solo per l'architettura x86.</span><span class="sxs-lookup"><span data-stu-id="0482d-132">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="0482d-133">Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito dalle dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interni selezionati.</span><span class="sxs-lookup"><span data-stu-id="0482d-133">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="0482d-134">La specifica di questo elemento di configurazione consente di compromettere l'affidabilità per un utilizzo di memoria virtuale inferiore se CLR rispetta la richiesta, perché le dimensioni dello stack più piccole potrebbero causare un overflow più probabile dello stack.</span><span class="sxs-lookup"><span data-stu-id="0482d-134">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0482d-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="0482d-135">Example</span></span>  
 <span data-ttu-id="0482d-136">Nell'esempio seguente viene illustrato come richiedere che CLR utilizzi dimensioni dello stack esplicite per determinati thread utilizzati internamente.</span><span class="sxs-lookup"><span data-stu-id="0482d-136">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0482d-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0482d-137">See also</span></span>

- [<span data-ttu-id="0482d-138">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0482d-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0482d-139">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0482d-139">Configuration File Schema</span></span>](../index.md)
