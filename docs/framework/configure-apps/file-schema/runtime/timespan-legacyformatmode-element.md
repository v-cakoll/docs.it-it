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
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968902"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="0ae6b-102">\<TimeSpan_LegacyFormatMode> Elemento</span><span class="sxs-lookup"><span data-stu-id="0ae6b-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="0ae6b-103">Determina se il runtime conserva il comportamento legacy nelle operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> i valori.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a><span data-ttu-id="0ae6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ae6b-104">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0ae6b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ae6b-105">Attributes and Elements</span></span>

<span data-ttu-id="0ae6b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0ae6b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ae6b-107">Attributes</span></span>

|<span data-ttu-id="0ae6b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0ae6b-108">Attribute</span></span>|<span data-ttu-id="0ae6b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ae6b-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0ae6b-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0ae6b-111">Specifica se il runtime usa il comportamento di formattazione legacy con <xref:System.TimeSpan?displayProperty=nameWithType> i valori.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-111">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="0ae6b-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0ae6b-112">enabled Attribute</span></span>

|<span data-ttu-id="0ae6b-113">Valore</span><span class="sxs-lookup"><span data-stu-id="0ae6b-113">Value</span></span>|<span data-ttu-id="0ae6b-114">Description</span><span class="sxs-lookup"><span data-stu-id="0ae6b-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0ae6b-115">Il runtime non ripristina il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-115">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="0ae6b-116">Il runtime ripristina il comportamento di formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-116">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0ae6b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ae6b-117">Child Elements</span></span>

<span data-ttu-id="0ae6b-118">No.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0ae6b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ae6b-119">Parent Elements</span></span>

|<span data-ttu-id="0ae6b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ae6b-120">Element</span></span>|<span data-ttu-id="0ae6b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ae6b-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0ae6b-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0ae6b-123">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-123">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0ae6b-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="0ae6b-124">Remarks</span></span>

<span data-ttu-id="0ae6b-125">A partire da .NET Framework 4, la <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa l' <xref:System.IFormattable> interfaccia e supporta le operazioni di formattazione con stringhe di formato standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-125">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="0ae6b-126">Se un metodo di analisi rileva un identificatore di formato non supportato o una stringa di formato, viene generata un'eccezione <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="0ae6b-126">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="0ae6b-127">Nelle versioni precedenti del .NET Framework la <xref:System.TimeSpan> struttura non implementava e non <xref:System.IFormattable> supportava le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-127">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="0ae6b-128">Tuttavia, molti sviluppatori presumevano erroneamente che <xref:System.TimeSpan> supportivano un set di stringhe di formato e le usavano in [operazioni di formattazione composita](../../../../standard/base-types/composite-formatting.md) con metodi come <xref:System.String.Format%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0ae6b-128">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0ae6b-129">In genere, se un tipo implementa <xref:System.IFormattable> e supporta le stringhe di formato, le chiamate ai metodi di formattazione con stringhe di formato non supportate in genere generano una <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="0ae6b-129">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="0ae6b-130">Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable> , il runtime ignora la stringa di formato e chiama invece il <xref:System.TimeSpan.ToString?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-130">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0ae6b-131">Ciò significa che, anche se le stringhe di formato non hanno effetto sull'operazione di formattazione, la loro presenza non ha restituito un <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="0ae6b-131">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="0ae6b-132">Per i casi in cui il codice legacy passa un metodo di formattazione composita e una stringa di formato non valida e tale codice non può essere ricompilato, è possibile usare l' `<TimeSpan_LegacyFormatMode>` elemento per ripristinare il <xref:System.TimeSpan> comportamento legacy.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-132">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="0ae6b-133">Quando si imposta l' `enabled` attributo di questo elemento su `true` , il metodo di formattazione composita genera una chiamata a <xref:System.TimeSpan.ToString?displayProperty=nameWithType> anziché <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> e <xref:System.FormatException> non viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-133">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="0ae6b-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ae6b-134">Example</span></span>

<span data-ttu-id="0ae6b-135">Nell'esempio seguente viene creata un'istanza di un <xref:System.TimeSpan> oggetto e viene effettuato un tentativo di formattarlo con il <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> metodo utilizzando una stringa di formato standard non supportata.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-135">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="0ae6b-136">Quando si esegue l'esempio in .NET Framework 3,5 o in una versione precedente, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="0ae6b-136">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="0ae6b-137">Questa operazione è notevolmente diversa rispetto all'output se si esegue l'esempio in .NET Framework 4 o versione successiva:</span><span class="sxs-lookup"><span data-stu-id="0ae6b-137">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="0ae6b-138">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi si esegue l'esempio in .NET Framework 4 o versione successiva, l'output sarà identico a quello prodotto dall'esempio quando viene eseguito in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="0ae6b-138">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0ae6b-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0ae6b-139">See also</span></span>

- [<span data-ttu-id="0ae6b-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0ae6b-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0ae6b-141">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0ae6b-141">Configuration File Schema</span></span>](../index.md)
