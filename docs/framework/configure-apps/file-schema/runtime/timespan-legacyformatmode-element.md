---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e265fd1de6047cd53b0f8d1c20c8a9e87b3e813
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689674"
---
# <a name="timespanlegacyformatmode-element"></a><span data-ttu-id="1864d-102">\<TimeSpan_LegacyFormatMode > elemento</span><span class="sxs-lookup"><span data-stu-id="1864d-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="1864d-103">Determina se il runtime deve mantenere il comportamento legacy in operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> valori.</span><span class="sxs-lookup"><span data-stu-id="1864d-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="1864d-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="1864d-104">\<configuration>\\</span></span>
<span data-ttu-id="1864d-105">\<runtime>\\</span><span class="sxs-lookup"><span data-stu-id="1864d-105">\<runtime>\\</span></span>
<span data-ttu-id="1864d-106">\<TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="1864d-106">\<TimeSpan_LegacyFormatMode></span></span>

## <a name="syntax"></a><span data-ttu-id="1864d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1864d-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1864d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1864d-108">Attributes and Elements</span></span>

<span data-ttu-id="1864d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1864d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1864d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1864d-110">Attributes</span></span>

|<span data-ttu-id="1864d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1864d-111">Attribute</span></span>|<span data-ttu-id="1864d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1864d-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="1864d-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1864d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1864d-114">Specifica se il runtime usa il comportamento della formattazione legacy con <xref:System.TimeSpan?displayProperty=nameWithType> valori.</span><span class="sxs-lookup"><span data-stu-id="1864d-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="1864d-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="1864d-115">enabled Attribute</span></span>

|<span data-ttu-id="1864d-116">Valore</span><span class="sxs-lookup"><span data-stu-id="1864d-116">Value</span></span>|<span data-ttu-id="1864d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1864d-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="1864d-118">Il runtime non consente di ripristinare il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="1864d-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="1864d-119">Il runtime consente di ripristinare il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="1864d-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1864d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1864d-120">Child Elements</span></span>

<span data-ttu-id="1864d-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1864d-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1864d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1864d-122">Parent Elements</span></span>

|<span data-ttu-id="1864d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1864d-123">Element</span></span>|<span data-ttu-id="1864d-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1864d-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="1864d-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1864d-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="1864d-126">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1864d-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1864d-127">Note</span><span class="sxs-lookup"><span data-stu-id="1864d-127">Remarks</span></span>

<span data-ttu-id="1864d-128">A partire da .NET Framework 4, il <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa il <xref:System.IFormattable> interfaccia e supporta operazioni di formattazione con stringhe di formato standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1864d-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="1864d-129">Se un metodo di analisi viene rilevato un identificatore di formato non supportato o una stringa di formato, viene generata una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1864d-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="1864d-130">Nelle versioni precedenti di .NET Framework, il <xref:System.TimeSpan> struttura non ha implementato <xref:System.IFormattable> e non supporta le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="1864d-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="1864d-131">Tuttavia, molti sviluppatori ritengono erroneamente che <xref:System.TimeSpan> supportava un set di stringhe di formato e usato nella [operazioni di formattazione composita](../../../../../docs/standard/base-types/composite-formatting.md) con i metodi come <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1864d-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1864d-132">In genere, se un tipo implementa <xref:System.IFormattable> e supporta le stringhe, le chiamate ai metodi di formattazione con formato non supportato in genere generano stringhe di formato un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1864d-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="1864d-133">Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable>, il runtime ignorata la stringa di formato e invece chiamato il <xref:System.TimeSpan.ToString?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="1864d-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1864d-134">Ciò significa che, anche se le stringhe di formato non aveva alcun effetto sull'operazione di formattazione, la loro presenza non ha restituito un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1864d-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="1864d-135">Per i casi in cui il codice legacy passa un metodo e una stringa di formato non valido di formattazione composita, e non è possibile ricompilare tale codice, è possibile usare la `<TimeSpan_LegacyFormatMode>` elemento da ripristinare legacy <xref:System.TimeSpan> comportamento.</span><span class="sxs-lookup"><span data-stu-id="1864d-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="1864d-136">Quando si imposta la `enabled` attributo di questo elemento per `true`, i risultati dei metodi in una chiamata a di formattazione composita <xref:System.TimeSpan.ToString?displayProperty=nameWithType> anziché <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>e un <xref:System.FormatException> non viene generata.</span><span class="sxs-lookup"><span data-stu-id="1864d-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="1864d-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="1864d-137">Example</span></span>

<span data-ttu-id="1864d-138">Nell'esempio seguente crea un <xref:System.TimeSpan> oggetto e tenta di formattarla con il <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> metodo tramite una stringa di formato standard non è supportato.</span><span class="sxs-lookup"><span data-stu-id="1864d-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="1864d-139">Quando si esegue l'esempio in .NET Framework 3.5 o una versione precedente, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="1864d-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="1864d-140">È notevolmente differente dall'output se si esegue l'esempio di .NET Framework 4 o versione successiva:</span><span class="sxs-lookup"><span data-stu-id="1864d-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="1864d-141">Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e quindi eseguirla l'esempio di .NET Framework 4 o versione successiva, l'output è identico a quello prodotto dall'esempio quando viene eseguita in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="1864d-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="1864d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1864d-142">See also</span></span>

- [<span data-ttu-id="1864d-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1864d-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1864d-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1864d-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
