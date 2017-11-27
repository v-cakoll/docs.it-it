---
title: '&lt;EnableAmPmParseAdjustment&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 44bd6297142b6f29d93e9a3bebdb89d32d4bf46a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="8c927-102">&lt;EnableAmPmParseAdjustment&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="8c927-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="8c927-103">Determina se data e ora di metodi di analisi utilizzare un set di regole adattato per analizzare le stringhe di data che contengono un giorno, mese, ora e indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="8c927-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="8c927-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c927-104">\<configuration></span></span>  
 <span data-ttu-id="8c927-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="8c927-105">\<runtime></span></span>  
<span data-ttu-id="8c927-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="8c927-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c927-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c927-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c927-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c927-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c927-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c927-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c927-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c927-110">Attributes</span></span>  
  
|<span data-ttu-id="8c927-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="8c927-111">Attribute</span></span>|<span data-ttu-id="8c927-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c927-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8c927-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c927-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8c927-114">Specifica se data e ora di metodi di analisi usare un set di regole adattato per analizzare le stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="8c927-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="8c927-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="8c927-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8c927-116">Valore</span><span class="sxs-lookup"><span data-stu-id="8c927-116">Value</span></span>|<span data-ttu-id="8c927-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c927-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c927-118">0</span><span class="sxs-lookup"><span data-stu-id="8c927-118">0</span></span>|<span data-ttu-id="8c927-119">Data e ora di metodi di analisi non utilizzano regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="8c927-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="8c927-120">1</span><span class="sxs-lookup"><span data-stu-id="8c927-120">1</span></span>|<span data-ttu-id="8c927-121">Data e ora di metodi di analisi utilizzare regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.</span><span class="sxs-lookup"><span data-stu-id="8c927-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c927-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c927-122">Child Elements</span></span>  
 <span data-ttu-id="8c927-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8c927-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c927-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c927-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8c927-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c927-125">Element</span></span>|<span data-ttu-id="8c927-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c927-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c927-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c927-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8c927-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c927-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c927-129">Note</span><span class="sxs-lookup"><span data-stu-id="8c927-129">Remarks</span></span>  
 <span data-ttu-id="8c927-130">Il `<EnableAmPmParseAdjustment>` elemento determina come i metodi seguenti analizzano una stringa di data che contiene un valore numerico del giorno e mese seguita da un'ora e un indicatore AM/PM (ad esempio "4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="8c927-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="8c927-131">Altri schemi non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="8c927-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="8c927-132">Il `<EnableAmPmParseAdjustment>` elemento non ha alcun effetto <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> metodi.</span><span class="sxs-lookup"><span data-stu-id="8c927-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c927-133">In .NET Core e .NET Native, le regole di analisi di AM/PM rettificate sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c927-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="8c927-134">Se la regola di rettifica analisi non è abilitata, la prima cifra della stringa viene interpretata come l'ora dell'orologio di 12 ore e il resto della stringa, ad eccezione di indicatore AM/PM viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="8c927-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="8c927-135">Data e ora restituito dal metodo di analisi costituito dalla data corrente e l'ora del giorno estratto dalla stringa di Data.</span><span class="sxs-lookup"><span data-stu-id="8c927-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="8c927-136">Se è abilitata la regola di rettifica analisi, l'analisi del metodo interpretare il giorno e mese come appartenente all'anno corrente e interpretare l'ora come ora dell'orologio di 12 ore.</span><span class="sxs-lookup"><span data-stu-id="8c927-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="8c927-137">Nella tabella seguente viene illustrata la differenza di <xref:System.DateTime> valore quando il <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> metodo viene utilizzato per analizzare la stringa "" 4/10 6 AM"con il `<EnableAmPmParseAdjustment>` dell'elemento `enabled` proprietà è impostata su"0"o"1".</span><span class="sxs-lookup"><span data-stu-id="8c927-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="8c927-138">Si presuppone che data è il 5 gennaio January 2017 e Visualizza la data come se viene formattato con una stringa di formato "G" le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="8c927-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="8c927-139">Nome delle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="8c927-139">Culture name</span></span>|<span data-ttu-id="8c927-140">attivato = "0"</span><span class="sxs-lookup"><span data-stu-id="8c927-140">enabled="0"</span></span>|<span data-ttu-id="8c927-141">attivato = "1"</span><span class="sxs-lookup"><span data-stu-id="8c927-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="8c927-142">it-IT</span><span class="sxs-lookup"><span data-stu-id="8c927-142">en-US</span></span>|<span data-ttu-id="8c927-143">5/1/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8c927-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="8c927-144">10/4/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8c927-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="8c927-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="8c927-145">en-GB</span></span>|<span data-ttu-id="8c927-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="8c927-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="8c927-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="8c927-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c927-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c927-148">See Also</span></span>  
 [<span data-ttu-id="8c927-149">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="8c927-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [<span data-ttu-id="8c927-150">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="8c927-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
