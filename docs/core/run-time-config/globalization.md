---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733462"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="72c86-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="72c86-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="72c86-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="72c86-104">Invariant mode</span></span>

- <span data-ttu-id="72c86-105">Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere a dati e comportamenti specifici delle impostazioni cultura o se può accedere ai dati culturali.</span><span class="sxs-lookup"><span data-stu-id="72c86-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="72c86-106">Impostazione predefinita: eseguire l'app con accesso ai dati culturali (`false`).</span><span class="sxs-lookup"><span data-stu-id="72c86-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="72c86-107">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="72c86-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="72c86-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="72c86-108">Setting name</span></span> | <span data-ttu-id="72c86-109">Valori</span><span class="sxs-lookup"><span data-stu-id="72c86-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72c86-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="72c86-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="72c86-111">`false` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="72c86-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="72c86-112">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="72c86-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="72c86-113">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="72c86-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="72c86-114">`false` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="72c86-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="72c86-115">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="72c86-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="72c86-116">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="72c86-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="72c86-117">`0` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="72c86-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="72c86-118">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="72c86-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="72c86-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="72c86-119">Examples</span></span>

<span data-ttu-id="72c86-120">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="72c86-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="72c86-121">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="72c86-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="72c86-122">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="72c86-122">Era year ranges</span></span>

- <span data-ttu-id="72c86-123">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che hanno overflow di un intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="72c86-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="72c86-124">Impostazione predefinita: i controlli intervallo sono rilassati (`false`).</span><span class="sxs-lookup"><span data-stu-id="72c86-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="72c86-125">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="72c86-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="72c86-126">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="72c86-126">Setting name</span></span> | <span data-ttu-id="72c86-127">Valori</span><span class="sxs-lookup"><span data-stu-id="72c86-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72c86-128">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="72c86-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="72c86-129">Controlli intervallo `false`-rilassato</span><span class="sxs-lookup"><span data-stu-id="72c86-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="72c86-130">`true`-overflow genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="72c86-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="72c86-131">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="72c86-131">**Environment variable**</span></span> | <span data-ttu-id="72c86-132">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-132">N/A</span></span> | <span data-ttu-id="72c86-133">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="72c86-134">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="72c86-134">Japanese date parsing</span></span>

- <span data-ttu-id="72c86-135">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="72c86-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="72c86-136">Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).</span><span class="sxs-lookup"><span data-stu-id="72c86-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="72c86-137">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="72c86-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="72c86-138">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="72c86-138">Setting name</span></span> | <span data-ttu-id="72c86-139">Valori</span><span class="sxs-lookup"><span data-stu-id="72c86-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72c86-140">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="72c86-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="72c86-141">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="72c86-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="72c86-142">è supportato solo `true` "1"</span><span class="sxs-lookup"><span data-stu-id="72c86-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="72c86-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="72c86-143">**Environment variable**</span></span> | <span data-ttu-id="72c86-144">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-144">N/A</span></span> | <span data-ttu-id="72c86-145">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="72c86-146">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="72c86-146">Japanese year format</span></span>

- <span data-ttu-id="72c86-147">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="72c86-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="72c86-148">Impostazione predefinita: formattare il primo anno come "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="72c86-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="72c86-149">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="72c86-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="72c86-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="72c86-150">Setting name</span></span> | <span data-ttu-id="72c86-151">Valori</span><span class="sxs-lookup"><span data-stu-id="72c86-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72c86-152">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="72c86-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="72c86-153">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="72c86-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="72c86-154">`true`-formatta come numero</span><span class="sxs-lookup"><span data-stu-id="72c86-154">`true` - format as number</span></span> |
| <span data-ttu-id="72c86-155">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="72c86-155">**Environment variable**</span></span> | <span data-ttu-id="72c86-156">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-156">N/A</span></span> | <span data-ttu-id="72c86-157">N/D</span><span class="sxs-lookup"><span data-stu-id="72c86-157">N/A</span></span> |
