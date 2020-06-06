---
title: <EnableAmPmParseAdjustment> Elemento
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117364"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="edbc3-102">\<EnableAmPmParseAdjustment> Elemento</span><span class="sxs-lookup"><span data-stu-id="edbc3-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="edbc3-103">Determina se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data contenenti un indicatore giorno, mese, ora e AM/PM.</span><span class="sxs-lookup"><span data-stu-id="edbc3-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="edbc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edbc3-104">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edbc3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="edbc3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="edbc3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="edbc3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edbc3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="edbc3-107">Attributes</span></span>  
  
|<span data-ttu-id="edbc3-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="edbc3-108">Attribute</span></span>|<span data-ttu-id="edbc3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbc3-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="edbc3-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="edbc3-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="edbc3-111">Specifica se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="edbc3-111">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="edbc3-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="edbc3-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="edbc3-113">Valore</span><span class="sxs-lookup"><span data-stu-id="edbc3-113">Value</span></span>|<span data-ttu-id="edbc3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbc3-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="edbc3-115">0</span><span class="sxs-lookup"><span data-stu-id="edbc3-115">0</span></span>|<span data-ttu-id="edbc3-116">I metodi di analisi di data e ora non utilizzano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="edbc3-116">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="edbc3-117">1</span><span class="sxs-lookup"><span data-stu-id="edbc3-117">1</span></span>|<span data-ttu-id="edbc3-118">I metodi di analisi di data e ora usano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="edbc3-118">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edbc3-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="edbc3-119">Child Elements</span></span>  
 <span data-ttu-id="edbc3-120">No.</span><span class="sxs-lookup"><span data-stu-id="edbc3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edbc3-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="edbc3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="edbc3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="edbc3-122">Element</span></span>|<span data-ttu-id="edbc3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbc3-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="edbc3-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="edbc3-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="edbc3-125">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="edbc3-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edbc3-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="edbc3-126">Remarks</span></span>  
 <span data-ttu-id="edbc3-127">L' `<EnableAmPmParseAdjustment>` elemento controlla il modo in cui i metodi seguenti analizzano una stringa di data contenente un giorno e un mese numerici seguiti da un'ora e un indicatore AM/PM (ad esempio "4/10 6 am"):</span><span class="sxs-lookup"><span data-stu-id="edbc3-127">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="edbc3-128">Nessun altro modello è interessato.</span><span class="sxs-lookup"><span data-stu-id="edbc3-128">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="edbc3-129">L' `<EnableAmPmParseAdjustment>` elemento non ha alcun effetto sui <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> metodi,, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="edbc3-129">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="edbc3-130">In .NET Core e .NET Native le regole di analisi AM/PM modificate sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="edbc3-130">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="edbc3-131">Se la regola di regolazione dell'analisi non è abilitata, la prima cifra della stringa viene interpretata come ora del formato a 12 ore e il resto della stringa, ad eccezione dell'indicatore AM/PM, viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="edbc3-131">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="edbc3-132">La data e l'ora restituite dal metodo di analisi sono costituite dalla data corrente e dall'ora del giorno estratta dalla stringa di data.</span><span class="sxs-lookup"><span data-stu-id="edbc3-132">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="edbc3-133">Se la regola di regolazione dell'analisi è abilitata, il metodo di analisi interpreta il giorno e il mese come appartenente all'anno corrente e interpreta l'ora come ora del formato a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="edbc3-133">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="edbc3-134">Nella tabella seguente viene illustrata la differenza nel <xref:System.DateTime> valore quando il <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> metodo viene utilizzato per analizzare la stringa "" 4/10 6 am "con la `<EnableAmPmParseAdjustment>` proprietà dell'elemento `enabled` impostata su" 0 "o" 1 ".</span><span class="sxs-lookup"><span data-stu-id="edbc3-134">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="edbc3-135">Si presuppone che la data odierna sia il 5 gennaio 2017 e visualizzi la data come se fosse formattata usando la stringa di formato "G" delle impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="edbc3-135">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="edbc3-136">Nome lingua</span><span class="sxs-lookup"><span data-stu-id="edbc3-136">Culture name</span></span>|<span data-ttu-id="edbc3-137">Enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="edbc3-137">enabled="0"</span></span>|<span data-ttu-id="edbc3-138">Enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="edbc3-138">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="edbc3-139">it-IT</span><span class="sxs-lookup"><span data-stu-id="edbc3-139">en-US</span></span>|<span data-ttu-id="edbc3-140">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="edbc3-140">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="edbc3-141">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="edbc3-141">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="edbc3-142">en-GB</span><span class="sxs-lookup"><span data-stu-id="edbc3-142">en-GB</span></span>|<span data-ttu-id="edbc3-143">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="edbc3-143">5/1/2017 6:00:00</span></span>|<span data-ttu-id="edbc3-144">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="edbc3-144">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edbc3-145">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="edbc3-145">See also</span></span>

- [<span data-ttu-id="edbc3-146">\<runtime>Elemento</span><span class="sxs-lookup"><span data-stu-id="edbc3-146">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="edbc3-147">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="edbc3-147">\<configuration> Element</span></span>](../configuration-element.md)
