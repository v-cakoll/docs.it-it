---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 7668c345181d7c08cfca9c5cb76b8addd76223ec
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506805"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="f1c6a-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="f1c6a-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="f1c6a-104">Invariant mode</span></span>

- <span data-ttu-id="f1c6a-105">Determina se un'app .NET Core viene eseguita in modalità non variant di globalizzazione senza accedere a dati e comportamento specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f1c6a-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="f1c6a-106">Impostazione predefinita: eseguire l'app con accesso ai dati culturali`false`().</span><span class="sxs-lookup"><span data-stu-id="f1c6a-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="f1c6a-107">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f1c6a-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="f1c6a-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-108">Setting name</span></span> | <span data-ttu-id="f1c6a-109">Valori</span><span class="sxs-lookup"><span data-stu-id="f1c6a-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1c6a-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="f1c6a-111">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="f1c6a-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="f1c6a-112">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="f1c6a-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="f1c6a-113">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="f1c6a-114">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="f1c6a-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="f1c6a-115">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="f1c6a-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="f1c6a-116">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="f1c6a-117">`0`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="f1c6a-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="f1c6a-118">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="f1c6a-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="f1c6a-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="f1c6a-119">Examples</span></span>

<span data-ttu-id="f1c6a-120">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="f1c6a-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="f1c6a-121">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="f1c6a-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="f1c6a-122">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="f1c6a-122">Era year ranges</span></span>

- <span data-ttu-id="f1c6a-123">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che superano l' <xref:System.ArgumentOutOfRangeException>intervallo di date di un'era generano una.</span><span class="sxs-lookup"><span data-stu-id="f1c6a-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="f1c6a-124">Impostazione predefinita: i controlli intervallo sono`false`rilassati ().</span><span class="sxs-lookup"><span data-stu-id="f1c6a-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="f1c6a-125">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="f1c6a-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="f1c6a-126">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-126">Setting name</span></span> | <span data-ttu-id="f1c6a-127">Valori</span><span class="sxs-lookup"><span data-stu-id="f1c6a-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1c6a-128">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="f1c6a-129">`false`-Controlli intervallo rilassato</span><span class="sxs-lookup"><span data-stu-id="f1c6a-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="f1c6a-130">`true`-gli overflow generano un'eccezione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="f1c6a-131">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-131">**Environment variable**</span></span> | <span data-ttu-id="f1c6a-132">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-132">N/A</span></span> | <span data-ttu-id="f1c6a-133">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="f1c6a-134">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="f1c6a-134">Japanese date parsing</span></span>

- <span data-ttu-id="f1c6a-135">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="f1c6a-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="f1c6a-136">Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).</span><span class="sxs-lookup"><span data-stu-id="f1c6a-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="f1c6a-137">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="f1c6a-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="f1c6a-138">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-138">Setting name</span></span> | <span data-ttu-id="f1c6a-139">Valori</span><span class="sxs-lookup"><span data-stu-id="f1c6a-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1c6a-140">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="f1c6a-141">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="f1c6a-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="f1c6a-142">`true`-è supportato solo "1"</span><span class="sxs-lookup"><span data-stu-id="f1c6a-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="f1c6a-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-143">**Environment variable**</span></span> | <span data-ttu-id="f1c6a-144">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-144">N/A</span></span> | <span data-ttu-id="f1c6a-145">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="f1c6a-146">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="f1c6a-146">Japanese year format</span></span>

- <span data-ttu-id="f1c6a-147">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="f1c6a-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="f1c6a-148">Impostazione predefinita: formattare il primo anno come "Gannen"`false`().</span><span class="sxs-lookup"><span data-stu-id="f1c6a-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="f1c6a-149">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="f1c6a-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="f1c6a-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1c6a-150">Setting name</span></span> | <span data-ttu-id="f1c6a-151">Valori</span><span class="sxs-lookup"><span data-stu-id="f1c6a-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1c6a-152">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="f1c6a-153">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="f1c6a-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="f1c6a-154">`true`-Formatta come numero</span><span class="sxs-lookup"><span data-stu-id="f1c6a-154">`true` - format as number</span></span> |
| <span data-ttu-id="f1c6a-155">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1c6a-155">**Environment variable**</span></span> | <span data-ttu-id="f1c6a-156">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-156">N/A</span></span> | <span data-ttu-id="f1c6a-157">N/D</span><span class="sxs-lookup"><span data-stu-id="f1c6a-157">N/A</span></span> |
