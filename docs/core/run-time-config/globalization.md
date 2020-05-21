---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: 56228e9a6cb6dbab6a22bdc00d11212e1019776b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761967"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="263bc-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="263bc-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="263bc-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="263bc-104">Invariant mode</span></span>

- <span data-ttu-id="263bc-105">Determina se un'app .NET Core viene eseguita in modalità non variant di globalizzazione senza accedere a dati e comportamento specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="263bc-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="263bc-106">Se si omette questa impostazione, l'app viene eseguita con accesso ai dati culturali.</span><span class="sxs-lookup"><span data-stu-id="263bc-106">If you omit this setting, the app runs with access to cultural data.</span></span> <span data-ttu-id="263bc-107">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="263bc-107">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="263bc-108">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="263bc-108">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="263bc-109">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="263bc-109">Setting name</span></span> | <span data-ttu-id="263bc-110">Valori</span><span class="sxs-lookup"><span data-stu-id="263bc-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="263bc-111">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="263bc-111">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="263bc-112">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="263bc-112">`false` - access to cultural data</span></span><br/><span data-ttu-id="263bc-113">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="263bc-113">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="263bc-114">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="263bc-114">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="263bc-115">`false`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="263bc-115">`false` - access to cultural data</span></span><br/><span data-ttu-id="263bc-116">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="263bc-116">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="263bc-117">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="263bc-117">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="263bc-118">`0`-accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="263bc-118">`0` - access to cultural data</span></span><br/><span data-ttu-id="263bc-119">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="263bc-119">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="263bc-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="263bc-120">Examples</span></span>

<span data-ttu-id="263bc-121">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="263bc-121">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="263bc-122">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="263bc-122">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="263bc-123">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="263bc-123">Era year ranges</span></span>

- <span data-ttu-id="263bc-124">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che superano l'intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="263bc-124">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="263bc-125">Se si omette questa impostazione, i controlli intervallo sono rilassati.</span><span class="sxs-lookup"><span data-stu-id="263bc-125">If you omit this setting, range checks are relaxed.</span></span> <span data-ttu-id="263bc-126">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="263bc-126">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="263bc-127">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="263bc-127">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="263bc-128">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="263bc-128">Setting name</span></span> | <span data-ttu-id="263bc-129">Valori</span><span class="sxs-lookup"><span data-stu-id="263bc-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="263bc-130">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="263bc-130">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="263bc-131">`false`-Controlli intervallo rilassato</span><span class="sxs-lookup"><span data-stu-id="263bc-131">`false` - relaxed range checks</span></span><br/><span data-ttu-id="263bc-132">`true`-gli overflow generano un'eccezione</span><span class="sxs-lookup"><span data-stu-id="263bc-132">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="263bc-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="263bc-133">**Environment variable**</span></span> | <span data-ttu-id="263bc-134">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-134">N/A</span></span> | <span data-ttu-id="263bc-135">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-135">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="263bc-136">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="263bc-136">Japanese date parsing</span></span>

- <span data-ttu-id="263bc-137">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="263bc-137">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="263bc-138">Se si omette questa impostazione, le stringhe che contengono "1" o "Gannen" come analisi dell'anno hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="263bc-138">If you omit this setting, strings that contain either "1" or "Gannen" as the year parse successfully.</span></span> <span data-ttu-id="263bc-139">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="263bc-139">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="263bc-140">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="263bc-140">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="263bc-141">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="263bc-141">Setting name</span></span> | <span data-ttu-id="263bc-142">Valori</span><span class="sxs-lookup"><span data-stu-id="263bc-142">Values</span></span> |
| - | - | - |
| <span data-ttu-id="263bc-143">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="263bc-143">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="263bc-144">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="263bc-144">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="263bc-145">`true`-è supportato solo "1"</span><span class="sxs-lookup"><span data-stu-id="263bc-145">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="263bc-146">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="263bc-146">**Environment variable**</span></span> | <span data-ttu-id="263bc-147">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-147">N/A</span></span> | <span data-ttu-id="263bc-148">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-148">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="263bc-149">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="263bc-149">Japanese year format</span></span>

- <span data-ttu-id="263bc-150">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="263bc-150">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="263bc-151">Se si omette questa impostazione, il primo anno viene formattato come "Gannen".</span><span class="sxs-lookup"><span data-stu-id="263bc-151">If you omit this setting, the first year is formatted as "Gannen".</span></span> <span data-ttu-id="263bc-152">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="263bc-152">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="263bc-153">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="263bc-153">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="263bc-154">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="263bc-154">Setting name</span></span> | <span data-ttu-id="263bc-155">Valori</span><span class="sxs-lookup"><span data-stu-id="263bc-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="263bc-156">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="263bc-156">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="263bc-157">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="263bc-157">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="263bc-158">`true`-Formatta come numero</span><span class="sxs-lookup"><span data-stu-id="263bc-158">`true` - format as number</span></span> |
| <span data-ttu-id="263bc-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="263bc-159">**Environment variable**</span></span> | <span data-ttu-id="263bc-160">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-160">N/A</span></span> | <span data-ttu-id="263bc-161">N/D</span><span class="sxs-lookup"><span data-stu-id="263bc-161">N/A</span></span> |

## <a name="nls"></a><span data-ttu-id="263bc-162">NLS</span><span class="sxs-lookup"><span data-stu-id="263bc-162">NLS</span></span>

- <span data-ttu-id="263bc-163">Determina se .NET usa le API di globalizzazione NLS (National Language Support) o i componenti internazionali per le app di globalizzazione (ICU) per le app di Windows.</span><span class="sxs-lookup"><span data-stu-id="263bc-163">Determines whether .NET uses National Language Support (NLS) or International Components for Unicode (ICU) globalization APIs for Windows apps.</span></span> <span data-ttu-id="263bc-164">.NET 5,0 e versioni successive usano le API di globalizzazione di ICU per impostazione predefinita in Windows 10 May 2019 Update e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="263bc-164">.NET 5.0 and later versions use ICU globalization APIs by default on Windows 10 May 2019 Update and later versions.</span></span>
- <span data-ttu-id="263bc-165">Se si omette questa impostazione, .NET usa le API di globalizzazione ICU per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="263bc-165">If you omit this setting, .NET uses ICU globalization APIs by default.</span></span> <span data-ttu-id="263bc-166">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="263bc-166">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="263bc-167">Per altre informazioni, vedere [API di globalizzazione usare le librerie di ICU in Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span><span class="sxs-lookup"><span data-stu-id="263bc-167">For more information, see [Globalization APIs use ICU libraries on Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span></span>

| | <span data-ttu-id="263bc-168">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="263bc-168">Setting name</span></span> | <span data-ttu-id="263bc-169">Valori</span><span class="sxs-lookup"><span data-stu-id="263bc-169">Values</span></span> | <span data-ttu-id="263bc-170">Introdotte</span><span class="sxs-lookup"><span data-stu-id="263bc-170">Introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="263bc-171">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="263bc-171">**runtimeconfig.json**</span></span> | `System.Globalization.UseNls` | <span data-ttu-id="263bc-172">`false`-Utilizzare le API di globalizzazione di ICU</span><span class="sxs-lookup"><span data-stu-id="263bc-172">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="263bc-173">`true`-Utilizzare le API di globalizzazione NLS</span><span class="sxs-lookup"><span data-stu-id="263bc-173">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="263bc-174">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="263bc-174">.NET 5.0</span></span> |
| <span data-ttu-id="263bc-175">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="263bc-175">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | <span data-ttu-id="263bc-176">`false`-Utilizzare le API di globalizzazione di ICU</span><span class="sxs-lookup"><span data-stu-id="263bc-176">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="263bc-177">`true`-Utilizzare le API di globalizzazione NLS</span><span class="sxs-lookup"><span data-stu-id="263bc-177">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="263bc-178">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="263bc-178">.NET 5.0</span></span> |
