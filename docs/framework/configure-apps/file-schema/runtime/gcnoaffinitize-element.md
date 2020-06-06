---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84004738"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="cfdf4-102">Elemento \<GCNoAffinitize></span><span class="sxs-lookup"><span data-stu-id="cfdf4-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="cfdf4-103">Specifica se creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="cfdf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfdf4-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cfdf4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfdf4-105">Attributes and elements</span></span>

<span data-ttu-id="cfdf4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cfdf4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfdf4-107">Attributes</span></span>

|<span data-ttu-id="cfdf4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfdf4-108">Attribute</span></span>|<span data-ttu-id="cfdf4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfdf4-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cfdf4-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-110">Required attribute.</span></span><br /><br /><span data-ttu-id="cfdf4-111">Specifica se i thread o gli heap GC del server sono creata un'affinità con i processori disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="cfdf4-112">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="cfdf4-112">enabled attribute</span></span>

|<span data-ttu-id="cfdf4-113">Valore</span><span class="sxs-lookup"><span data-stu-id="cfdf4-113">Value</span></span>|<span data-ttu-id="cfdf4-114">Description</span><span class="sxs-lookup"><span data-stu-id="cfdf4-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="cfdf4-115">Thread GC del server cui con CPU.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="cfdf4-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="cfdf4-117">Non creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cfdf4-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfdf4-118">Child elements</span></span>

<span data-ttu-id="cfdf4-119">No.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cfdf4-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfdf4-120">Parent elements</span></span>

|<span data-ttu-id="cfdf4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfdf4-121">Element</span></span>|<span data-ttu-id="cfdf4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfdf4-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cfdf4-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cfdf4-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cfdf4-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="cfdf4-125">Remarks</span></span>

<span data-ttu-id="cfdf4-126">Per impostazione predefinita, i thread GC del server sono creata un'affinità con le rispettive CPU.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="cfdf4-127">Ogni processore disponibile del sistema dispone di un proprio heap GC e di un thread.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="cfdf4-128">Si tratta in genere dell'impostazione preferita perché ottimizza l'utilizzo della cache.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="cfdf4-129">A partire da .NET Framework 4.6.2, impostando l'attributo dell'elemento **GCNoAffinitize** `enabled` su `true` , è possibile specificare che i thread GC del server e le CPU non devono essere strettamente accoppiati.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="cfdf4-130">È possibile specificare solo l'elemento di configurazione **GCNoAffinitize** per non creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="cfdf4-131">È anche possibile usarlo insieme all'elemento [GCHeapCount](gcheapcount-element.md) per controllare il numero di heap e thread GC usati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="cfdf4-132">Se l' `enabled` attributo dell'elemento **GCNoAffinitize** è `false` (valore predefinito), è anche possibile usare l'elemento [GCHeapCount](gcheapcount-element.md) per specificare il numero di thread e heap GC, insieme all'elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) per specificare i processori a cui sono creata un'affinità i thread GC e gli heap.</span><span class="sxs-lookup"><span data-stu-id="cfdf4-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="cfdf4-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfdf4-133">Example</span></span>

<span data-ttu-id="cfdf4-134">L'esempio seguente non creare affinità tra i thread GC del server:</span><span class="sxs-lookup"><span data-stu-id="cfdf4-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="cfdf4-135">L'esempio seguente non creare affinità tra i thread GC del server e limita il numero di heap GC/thread a 10:</span><span class="sxs-lookup"><span data-stu-id="cfdf4-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cfdf4-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="cfdf4-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cfdf4-137">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="cfdf4-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="cfdf4-138">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="cfdf4-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="cfdf4-139">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="cfdf4-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="cfdf4-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="cfdf4-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cfdf4-141">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="cfdf4-141">Configuration File Schema</span></span>](../index.md)
