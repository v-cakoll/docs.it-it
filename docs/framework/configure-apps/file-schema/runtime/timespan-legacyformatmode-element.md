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
ms.openlocfilehash: f16a2bbd2470b4aec9e95ab67ccb0e736c4c6d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920685"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="f31f2-102">\<Elemento > TimeSpan_LegacyFormatMode</span><span class="sxs-lookup"><span data-stu-id="f31f2-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="f31f2-103">Determina se il runtime conserva il comportamento legacy nelle operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> i valori.</span><span class="sxs-lookup"><span data-stu-id="f31f2-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="f31f2-104">\<> di configurazione </span><span class="sxs-lookup"><span data-stu-id="f31f2-104">\<configuration></span></span>\
<span data-ttu-id="f31f2-105">\<> runtime </span><span class="sxs-lookup"><span data-stu-id="f31f2-105">\<runtime></span></span>\
<span data-ttu-id="f31f2-106">\<TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="f31f2-106">\<TimeSpan_LegacyFormatMode></span></span>

## <a name="syntax"></a><span data-ttu-id="f31f2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f31f2-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f31f2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f31f2-108">Attributes and Elements</span></span>

<span data-ttu-id="f31f2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f31f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f31f2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f31f2-110">Attributes</span></span>

|<span data-ttu-id="f31f2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f31f2-111">Attribute</span></span>|<span data-ttu-id="f31f2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31f2-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f31f2-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f31f2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f31f2-114">Specifica se il runtime usa il comportamento di formattazione <xref:System.TimeSpan?displayProperty=nameWithType> legacy con i valori.</span><span class="sxs-lookup"><span data-stu-id="f31f2-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f31f2-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f31f2-115">enabled Attribute</span></span>

|<span data-ttu-id="f31f2-116">Valore</span><span class="sxs-lookup"><span data-stu-id="f31f2-116">Value</span></span>|<span data-ttu-id="f31f2-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31f2-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f31f2-118">Il runtime non ripristina il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f31f2-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="f31f2-119">Il runtime ripristina il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f31f2-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f31f2-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f31f2-120">Child Elements</span></span>

<span data-ttu-id="f31f2-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f31f2-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f31f2-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f31f2-122">Parent Elements</span></span>

|<span data-ttu-id="f31f2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f31f2-123">Element</span></span>|<span data-ttu-id="f31f2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f31f2-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f31f2-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f31f2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f31f2-126">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31f2-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f31f2-127">Note</span><span class="sxs-lookup"><span data-stu-id="f31f2-127">Remarks</span></span>

<span data-ttu-id="f31f2-128">A partire da .NET Framework 4, la <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa l' <xref:System.IFormattable> interfaccia e supporta le operazioni di formattazione con stringhe di formato standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f31f2-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="f31f2-129">Se un metodo di analisi rileva un identificatore di formato non supportato o una stringa di formato, viene generata un' <xref:System.FormatException>eccezione.</span><span class="sxs-lookup"><span data-stu-id="f31f2-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="f31f2-130">Nelle versioni precedenti del .NET Framework la struttura non <xref:System.TimeSpan> implementava <xref:System.IFormattable> e non supportava le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="f31f2-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="f31f2-131">Tuttavia, molti sviluppatori presumevano erroneamente che <xref:System.TimeSpan> supportivano un set di stringhe di formato e le usavano in [operazioni di formattazione composita](../../../../standard/base-types/composite-formatting.md) <xref:System.String.Format%2A?displayProperty=nameWithType>con metodi come.</span><span class="sxs-lookup"><span data-stu-id="f31f2-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f31f2-132">In genere, se un tipo implementa <xref:System.IFormattable> e supporta le stringhe di formato, le chiamate ai metodi di formattazione con stringhe di formato non <xref:System.FormatException>supportate in genere generano una.</span><span class="sxs-lookup"><span data-stu-id="f31f2-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="f31f2-133">Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable>, il runtime ignora la stringa di formato e chiama invece <xref:System.TimeSpan.ToString?displayProperty=nameWithType> il metodo.</span><span class="sxs-lookup"><span data-stu-id="f31f2-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f31f2-134">Ciò significa che, anche se le stringhe di formato non hanno effetto sull'operazione di formattazione, la loro presenza non ha <xref:System.FormatException>restituito un.</span><span class="sxs-lookup"><span data-stu-id="f31f2-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="f31f2-135">Per i casi in cui il codice legacy passa un metodo di formattazione composita e una stringa di formato non valida e tale codice non può essere ricompilato `<TimeSpan_LegacyFormatMode>` , è possibile usare l' <xref:System.TimeSpan> elemento per ripristinare il comportamento legacy.</span><span class="sxs-lookup"><span data-stu-id="f31f2-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="f31f2-136">Quando si imposta l' `enabled` attributo di questo elemento su `true`, il metodo di formattazione composita genera <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>una chiamata <xref:System.TimeSpan.ToString?displayProperty=nameWithType> a anziché e non viene <xref:System.FormatException> generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f31f2-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="f31f2-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="f31f2-137">Example</span></span>

<span data-ttu-id="f31f2-138">Nell'esempio seguente viene creata un' <xref:System.TimeSpan> istanza di un oggetto e viene effettuato un <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> tentativo di formattarlo con il metodo utilizzando una stringa di formato standard non supportata.</span><span class="sxs-lookup"><span data-stu-id="f31f2-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="f31f2-139">Quando si esegue l'esempio in .NET Framework 3,5 o in una versione precedente, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="f31f2-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="f31f2-140">Questa operazione è notevolmente diversa rispetto all'output se si esegue l'esempio in .NET Framework 4 o versione successiva:</span><span class="sxs-lookup"><span data-stu-id="f31f2-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="f31f2-141">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi si esegue l'esempio in .NET Framework 4 o versione successiva, l'output sarà identico a quello prodotto dall'esempio quando viene eseguito in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="f31f2-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f31f2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f31f2-142">See also</span></span>

- [<span data-ttu-id="f31f2-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f31f2-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f31f2-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f31f2-144">Configuration File Schema</span></span>](../index.md)
