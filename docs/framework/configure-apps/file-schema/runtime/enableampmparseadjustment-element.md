---
title: <EnableAmPmParseAdjustment> Elemento
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252622"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="ec3db-102">\<Elemento > EnableAmPmParseAdjustment</span><span class="sxs-lookup"><span data-stu-id="ec3db-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="ec3db-103">Determina se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data contenenti un indicatore giorno, mese, ora e AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ec3db-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
<span data-ttu-id="ec3db-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec3db-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec3db-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec3db-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ec3db-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<EnableAmPmParseAdjustment>**</span><span class="sxs-lookup"><span data-stu-id="ec3db-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec3db-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec3db-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec3db-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ec3db-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec3db-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ec3db-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec3db-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ec3db-110">Attributes</span></span>  
  
|<span data-ttu-id="ec3db-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ec3db-111">Attribute</span></span>|<span data-ttu-id="ec3db-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec3db-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ec3db-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ec3db-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ec3db-114">Specifica se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ec3db-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="ec3db-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="ec3db-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ec3db-116">Valore</span><span class="sxs-lookup"><span data-stu-id="ec3db-116">Value</span></span>|<span data-ttu-id="ec3db-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec3db-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec3db-118">0</span><span class="sxs-lookup"><span data-stu-id="ec3db-118">0</span></span>|<span data-ttu-id="ec3db-119">I metodi di analisi di data e ora non utilizzano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ec3db-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="ec3db-120">1</span><span class="sxs-lookup"><span data-stu-id="ec3db-120">1</span></span>|<span data-ttu-id="ec3db-121">I metodi di analisi di data e ora usano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ec3db-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec3db-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ec3db-122">Child Elements</span></span>  
 <span data-ttu-id="ec3db-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ec3db-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec3db-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ec3db-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ec3db-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec3db-125">Element</span></span>|<span data-ttu-id="ec3db-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec3db-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ec3db-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec3db-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ec3db-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ec3db-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec3db-129">Note</span><span class="sxs-lookup"><span data-stu-id="ec3db-129">Remarks</span></span>  
 <span data-ttu-id="ec3db-130">L' `<EnableAmPmParseAdjustment>` elemento controlla il modo in cui i metodi seguenti analizzano una stringa di data contenente un giorno e un mese numerici seguiti da un'ora e un indicatore AM/PM (ad esempio "4/10 6 am"):</span><span class="sxs-lookup"><span data-stu-id="ec3db-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="ec3db-131">Nessun altro modello è interessato.</span><span class="sxs-lookup"><span data-stu-id="ec3db-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="ec3db-132">L' `<EnableAmPmParseAdjustment>` elemento non ha alcun effetto <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>sui metodi <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ec3db-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec3db-133">In .NET Core e .NET Native le regole di analisi AM/PM modificate sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ec3db-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="ec3db-134">Se la regola di regolazione dell'analisi non è abilitata, la prima cifra della stringa viene interpretata come ora del formato a 12 ore e il resto della stringa, ad eccezione dell'indicatore AM/PM, viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ec3db-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="ec3db-135">La data e l'ora restituite dal metodo di analisi sono costituite dalla data corrente e dall'ora del giorno estratta dalla stringa di data.</span><span class="sxs-lookup"><span data-stu-id="ec3db-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="ec3db-136">Se la regola di regolazione dell'analisi è abilitata, il metodo di analisi interpreta il giorno e il mese come appartenente all'anno corrente e interpreta l'ora come ora del formato a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="ec3db-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="ec3db-137">Nella tabella seguente viene illustrata la differenza nel <xref:System.DateTime> valore quando il <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> metodo viene utilizzato per analizzare la stringa "" 4/10 6 am `enabled` "con la `<EnableAmPmParseAdjustment>` proprietà dell'elemento impostata su" 0 "o" 1 ".</span><span class="sxs-lookup"><span data-stu-id="ec3db-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="ec3db-138">Si presuppone che la data odierna sia il 5 gennaio 2017 e visualizzi la data come se fosse formattata usando la stringa di formato "G" delle impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="ec3db-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="ec3db-139">Nome delle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="ec3db-139">Culture name</span></span>|<span data-ttu-id="ec3db-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="ec3db-140">enabled="0"</span></span>|<span data-ttu-id="ec3db-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="ec3db-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="ec3db-142">en-US</span><span class="sxs-lookup"><span data-stu-id="ec3db-142">en-US</span></span>|<span data-ttu-id="ec3db-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ec3db-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="ec3db-144">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ec3db-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="ec3db-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="ec3db-145">en-GB</span></span>|<span data-ttu-id="ec3db-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ec3db-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="ec3db-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ec3db-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec3db-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec3db-148">See also</span></span>

- [<span data-ttu-id="ec3db-149">\<Elemento runtime ></span><span class="sxs-lookup"><span data-stu-id="ec3db-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="ec3db-150">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="ec3db-150">\<configuration> Element</span></span>](../configuration-element.md)
