---
title: '&lt;TimeSpan_LegacyFormatMode&gt; elemento'
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
ms.openlocfilehash: 0faf2876680ef5ec3fc7373cae9f81eb091f47a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="b7dd7-102">&lt;TimeSpan_LegacyFormatMode&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="b7dd7-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="b7dd7-103">Determina se il runtime deve mantenere il comportamento legacy in operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> valori.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="b7dd7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b7dd7-104">\<configuration></span></span>  
<span data-ttu-id="b7dd7-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b7dd7-105">\<runtime></span></span>  
<span data-ttu-id="b7dd7-106"><TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="b7dd7-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7dd7-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7dd7-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7dd7-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b7dd7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b7dd7-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7dd7-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b7dd7-110">Attributes</span></span>  
  
|<span data-ttu-id="b7dd7-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b7dd7-111">Attribute</span></span>|<span data-ttu-id="b7dd7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7dd7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b7dd7-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7dd7-114">Specifica se il runtime utilizza il comportamento della formattazione legacy con <xref:System.TimeSpan?displayProperty=nameWithType> valori.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b7dd7-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b7dd7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b7dd7-116">Valore</span><span class="sxs-lookup"><span data-stu-id="b7dd7-116">Value</span></span>|<span data-ttu-id="b7dd7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7dd7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b7dd7-118">Il runtime non consente di ripristinare il comportamento della formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="b7dd7-119">Il runtime consente di ripristinare il comportamento della formattazione legacy.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7dd7-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b7dd7-120">Child Elements</span></span>  
 <span data-ttu-id="b7dd7-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7dd7-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b7dd7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b7dd7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7dd7-123">Element</span></span>|<span data-ttu-id="b7dd7-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7dd7-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7dd7-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b7dd7-126">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7dd7-127">Note</span><span class="sxs-lookup"><span data-stu-id="b7dd7-127">Remarks</span></span>  
 <span data-ttu-id="b7dd7-128">A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa il <xref:System.IFormattable> interfaccia e supporta operazioni di formattazione con stringhe di formato standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="b7dd7-129">Se un metodo di analisi viene rilevato un identificatore di formato non supportato o di una stringa di formato, viene generata una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="b7dd7-130">Nelle versioni precedenti di .NET Framework, il <xref:System.TimeSpan> struttura non ha implementato <xref:System.IFormattable> e non supporta le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="b7dd7-131">Tuttavia, molti sviluppatori erroneamente che <xref:System.TimeSpan> supportavano un set di stringhe di formato e utilizzati in [le operazioni di formattazione composita](../../../../../docs/standard/base-types/composite-formatting.md) con metodi come <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b7dd7-132">In genere, se un tipo implementa <xref:System.IFormattable> e stringhe, chiamate ai metodi di formattazione con formato non supportato normalmente generano stringhe di formato supporta un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="b7dd7-133">Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable>, il runtime ignorata la stringa di formato e invece chiamato il <xref:System.TimeSpan.ToString?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="b7dd7-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b7dd7-134">Ciò significa che, anche se le stringhe di formato non aveva alcun effetto sull'operazione di formattazione, la loro presenza non ha restituito un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="b7dd7-135">Nei casi in cui il codice legacy passa un metodo e una stringa di formato non valido di formattazione composita e non è possibile ricompilare tale codice, è possibile utilizzare il `<TimeSpan_LegacyFormatMode>` elemento da ripristinare legacy <xref:System.TimeSpan> comportamento.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="b7dd7-136">Quando si imposta la `enabled` attributo dell'elemento `true`, in una chiamata a risultati dei metodi di formattazione composita <xref:System.TimeSpan.ToString?displayProperty=nameWithType> anziché <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>e un <xref:System.FormatException> non viene generata.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7dd7-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7dd7-137">Example</span></span>  
 <span data-ttu-id="b7dd7-138">Nell'esempio seguente viene creata un'istanza di un <xref:System.TimeSpan> oggetto e tenta di formattarla con il <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> metodo utilizzando una stringa di formato standard non supportata.</span><span class="sxs-lookup"><span data-stu-id="b7dd7-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="b7dd7-139">Quando si esegue l'esempio sul [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] o in una versione precedente, viene visualizzato il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b7dd7-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="b7dd7-140">È notevolmente differente dall'output dell'esempio eseguito in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="b7dd7-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="b7dd7-141">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e, successivamente, si esegue l'esempio in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o versioni successive, l'output è identico a quello prodotto dall'esempio quando viene eseguito in [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7dd7-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7dd7-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7dd7-142">See Also</span></span>  
 [<span data-ttu-id="b7dd7-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b7dd7-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b7dd7-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b7dd7-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
