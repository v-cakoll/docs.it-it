---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: 2561e66e6d18cb4036b0719f7e34ea66540fe095
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703122"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="a0f65-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="a0f65-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="a0f65-104">Invariant mode</span></span>

- <span data-ttu-id="a0f65-105">Determina se un'app .NET Core viene eseguita in modalità non variant di globalizzazione senza accedere a dati e comportamento specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a0f65-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="a0f65-106">Impostazione predefinita: eseguire l'app con accesso ai dati culturali ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="a0f65-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="a0f65-107">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a0f65-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="a0f65-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-108">Setting name</span></span> | <span data-ttu-id="a0f65-109">Valori</span><span class="sxs-lookup"><span data-stu-id="a0f65-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a0f65-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="a0f65-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="a0f65-111">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="a0f65-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="a0f65-112">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="a0f65-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="a0f65-113">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="a0f65-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="a0f65-114">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="a0f65-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="a0f65-115">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="a0f65-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="a0f65-116">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a0f65-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="a0f65-117">`0`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="a0f65-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="a0f65-118">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="a0f65-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="a0f65-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="a0f65-119">Examples</span></span>

<span data-ttu-id="a0f65-120">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="a0f65-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="a0f65-121">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="a0f65-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="a0f65-122">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="a0f65-122">Era year ranges</span></span>

- <span data-ttu-id="a0f65-123">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che superano l'intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="a0f65-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="a0f65-124">Impostazione predefinita: i controlli intervallo sono rilassati ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="a0f65-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="a0f65-125">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="a0f65-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="a0f65-126">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-126">Setting name</span></span> | <span data-ttu-id="a0f65-127">Valori</span><span class="sxs-lookup"><span data-stu-id="a0f65-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a0f65-128">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="a0f65-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="a0f65-129">`false`-Controlli intervallo rilassato</span><span class="sxs-lookup"><span data-stu-id="a0f65-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="a0f65-130">`true`-gli overflow generano un'eccezione</span><span class="sxs-lookup"><span data-stu-id="a0f65-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="a0f65-131">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a0f65-131">**Environment variable**</span></span> | <span data-ttu-id="a0f65-132">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-132">N/A</span></span> | <span data-ttu-id="a0f65-133">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="a0f65-134">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="a0f65-134">Japanese date parsing</span></span>

- <span data-ttu-id="a0f65-135">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="a0f65-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="a0f65-136">Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="a0f65-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="a0f65-137">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="a0f65-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="a0f65-138">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-138">Setting name</span></span> | <span data-ttu-id="a0f65-139">Valori</span><span class="sxs-lookup"><span data-stu-id="a0f65-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a0f65-140">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="a0f65-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="a0f65-141">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="a0f65-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="a0f65-142">`true`-è supportato solo "1"</span><span class="sxs-lookup"><span data-stu-id="a0f65-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="a0f65-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a0f65-143">**Environment variable**</span></span> | <span data-ttu-id="a0f65-144">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-144">N/A</span></span> | <span data-ttu-id="a0f65-145">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="a0f65-146">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="a0f65-146">Japanese year format</span></span>

- <span data-ttu-id="a0f65-147">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="a0f65-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="a0f65-148">Impostazione predefinita: formattare il primo anno come "Gannen" ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="a0f65-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="a0f65-149">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="a0f65-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="a0f65-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-150">Setting name</span></span> | <span data-ttu-id="a0f65-151">Valori</span><span class="sxs-lookup"><span data-stu-id="a0f65-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a0f65-152">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="a0f65-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="a0f65-153">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="a0f65-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="a0f65-154">`true`-Formatta come numero</span><span class="sxs-lookup"><span data-stu-id="a0f65-154">`true` - format as number</span></span> |
| <span data-ttu-id="a0f65-155">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a0f65-155">**Environment variable**</span></span> | <span data-ttu-id="a0f65-156">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-156">N/A</span></span> | <span data-ttu-id="a0f65-157">N/D</span><span class="sxs-lookup"><span data-stu-id="a0f65-157">N/A</span></span> |

## <a name="nls"></a><span data-ttu-id="a0f65-158">NLS</span><span class="sxs-lookup"><span data-stu-id="a0f65-158">NLS</span></span>

- <span data-ttu-id="a0f65-159">Determina se .NET usa le API di globalizzazione NLS (National Language Support) o i componenti internazionali per le app di globalizzazione (ICU) per le app di Windows.</span><span class="sxs-lookup"><span data-stu-id="a0f65-159">Determines whether .NET uses National Language Support (NLS) or International Components for Unicode (ICU) globalization APIs for Windows apps.</span></span> <span data-ttu-id="a0f65-160">.NET 5,0 e versioni successive usano le API di globalizzazione di ICU per impostazione predefinita in Windows 10 May 2019 Update e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a0f65-160">.NET 5.0 and later versions use ICU globalization APIs by default on Windows 10 May 2019 Update and later versions.</span></span>
- <span data-ttu-id="a0f65-161">Se si omette questa impostazione, .NET usa le API di globalizzazione ICU per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a0f65-161">If you omit this setting, .NET uses ICU globalization APIs by default.</span></span> <span data-ttu-id="a0f65-162">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="a0f65-162">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="a0f65-163">Per altre informazioni, vedere [API di globalizzazione usare le librerie di ICU in Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span><span class="sxs-lookup"><span data-stu-id="a0f65-163">For more information, see [Globalization APIs use ICU libraries on Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span></span>

| | <span data-ttu-id="a0f65-164">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a0f65-164">Setting name</span></span> | <span data-ttu-id="a0f65-165">Valori</span><span class="sxs-lookup"><span data-stu-id="a0f65-165">Values</span></span> | <span data-ttu-id="a0f65-166">Introdotte</span><span class="sxs-lookup"><span data-stu-id="a0f65-166">Introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="a0f65-167">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="a0f65-167">**runtimeconfig.json**</span></span> | `System.Globalization.UseNls` | <span data-ttu-id="a0f65-168">`false`-Utilizzare le API di globalizzazione di ICU</span><span class="sxs-lookup"><span data-stu-id="a0f65-168">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="a0f65-169">`true`-Utilizzare le API di globalizzazione NLS</span><span class="sxs-lookup"><span data-stu-id="a0f65-169">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="a0f65-170">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a0f65-170">.NET 5.0</span></span> |
| <span data-ttu-id="a0f65-171">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a0f65-171">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | <span data-ttu-id="a0f65-172">`false`-Utilizzare le API di globalizzazione di ICU</span><span class="sxs-lookup"><span data-stu-id="a0f65-172">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="a0f65-173">`true`-Utilizzare le API di globalizzazione NLS</span><span class="sxs-lookup"><span data-stu-id="a0f65-173">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="a0f65-174">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a0f65-174">.NET 5.0</span></span> |
