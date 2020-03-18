---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni di runtime che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio la modalità di analisi delle date in giapponese.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733462"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="93078-103">Opzioni di configurazione in fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="93078-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="93078-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="93078-104">Invariant mode</span></span>

- <span data-ttu-id="93078-105">Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere ai dati e al comportamento specifici delle impostazioni cultura o se ha accesso ai dati culturali.</span><span class="sxs-lookup"><span data-stu-id="93078-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="93078-106">Impostazione predefinita: eseguire l'app`false`con accesso ai dati culturali ( ).</span><span class="sxs-lookup"><span data-stu-id="93078-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="93078-107">Per ulteriori informazioni, vedere [Modalità invariante di globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="93078-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="93078-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="93078-108">Setting name</span></span> | <span data-ttu-id="93078-109">Valori</span><span class="sxs-lookup"><span data-stu-id="93078-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="93078-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="93078-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="93078-111">`false`- accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="93078-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="93078-112">`true`- eseguire in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="93078-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="93078-113">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="93078-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="93078-114">`false`- accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="93078-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="93078-115">`true`- eseguire in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="93078-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="93078-116">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="93078-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="93078-117">`0`- accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="93078-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="93078-118">`1`- eseguire in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="93078-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="93078-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="93078-119">Examples</span></span>

<span data-ttu-id="93078-120">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="93078-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="93078-121">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="93078-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="93078-122">Intervalli dell'anno era</span><span class="sxs-lookup"><span data-stu-id="93078-122">Era year ranges</span></span>

- <span data-ttu-id="93078-123">Determina se i controlli dell'intervallo per i calendari che supportano più <xref:System.ArgumentOutOfRangeException>ere sono rilassati o se le date che causano un overflow nell'intervallo di date di un'era generano un' .</span><span class="sxs-lookup"><span data-stu-id="93078-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="93078-124">Impostazione predefinita: i`false`controlli di intervallo sono rilassati ( ).</span><span class="sxs-lookup"><span data-stu-id="93078-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="93078-125">Per ulteriori informazioni, vedere [Calendari, ere e intervalli di date: Controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="93078-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="93078-126">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="93078-126">Setting name</span></span> | <span data-ttu-id="93078-127">Valori</span><span class="sxs-lookup"><span data-stu-id="93078-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="93078-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="93078-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="93078-129">`false`- rilassati controlli a distanza</span><span class="sxs-lookup"><span data-stu-id="93078-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="93078-130">`true`- Gli overflow causano un'eccezione- overflow strame an exception</span><span class="sxs-lookup"><span data-stu-id="93078-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="93078-131">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="93078-131">**Environment variable**</span></span> | <span data-ttu-id="93078-132">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-132">N/A</span></span> | <span data-ttu-id="93078-133">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="93078-134">Analisi data giapponese</span><span class="sxs-lookup"><span data-stu-id="93078-134">Japanese date parsing</span></span>

- <span data-ttu-id="93078-135">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzato correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="93078-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="93078-136">Impostazione predefinita: analizza le stringhe che contengono "1"`false`o "Gannen" come anno ( ).</span><span class="sxs-lookup"><span data-stu-id="93078-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="93078-137">Per ulteriori informazioni, consultate [Rappresentare le date nei calendari con più ere.](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)</span><span class="sxs-lookup"><span data-stu-id="93078-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="93078-138">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="93078-138">Setting name</span></span> | <span data-ttu-id="93078-139">Valori</span><span class="sxs-lookup"><span data-stu-id="93078-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="93078-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="93078-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="93078-141">`false`- "Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="93078-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="93078-142">`true`- è supportato solo "1"</span><span class="sxs-lookup"><span data-stu-id="93078-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="93078-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="93078-143">**Environment variable**</span></span> | <span data-ttu-id="93078-144">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-144">N/A</span></span> | <span data-ttu-id="93078-145">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="93078-146">Formato anno giapponese</span><span class="sxs-lookup"><span data-stu-id="93078-146">Japanese year format</span></span>

- <span data-ttu-id="93078-147">Determina se il primo anno di un'era del calendario giapponese viene formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="93078-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="93078-148">Impostazione predefinita: formattare il primo anno`false`come "Gannen" ( ).</span><span class="sxs-lookup"><span data-stu-id="93078-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="93078-149">Per ulteriori informazioni, consultate [Rappresentare le date nei calendari con più ere.](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)</span><span class="sxs-lookup"><span data-stu-id="93078-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="93078-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="93078-150">Setting name</span></span> | <span data-ttu-id="93078-151">Valori</span><span class="sxs-lookup"><span data-stu-id="93078-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="93078-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="93078-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="93078-153">`false`- formato come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="93078-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="93078-154">`true`- formato come numero</span><span class="sxs-lookup"><span data-stu-id="93078-154">`true` - format as number</span></span> |
| <span data-ttu-id="93078-155">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="93078-155">**Environment variable**</span></span> | <span data-ttu-id="93078-156">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-156">N/A</span></span> | <span data-ttu-id="93078-157">N/D</span><span class="sxs-lookup"><span data-stu-id="93078-157">N/A</span></span> |
