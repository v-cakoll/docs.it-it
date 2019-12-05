---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 0571c64eff5b38aafa37026fb2ba7f4aef778beb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802778"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="e3dc7-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="e3dc7-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="e3dc7-104">Invariant mode</span></span>

- <span data-ttu-id="e3dc7-105">Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere a dati e comportamenti specifici delle impostazioni cultura o se può accedere ai dati culturali.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="e3dc7-106">Impostazione predefinita: eseguire l'app con accesso ai dati culturali (`false`).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="e3dc7-107">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="e3dc7-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-108">Setting name</span></span> | <span data-ttu-id="e3dc7-109">Valori</span><span class="sxs-lookup"><span data-stu-id="e3dc7-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e3dc7-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="e3dc7-111">`false` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="e3dc7-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="e3dc7-112">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="e3dc7-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="e3dc7-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="e3dc7-114">`0` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="e3dc7-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="e3dc7-115">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="e3dc7-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="e3dc7-116">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="e3dc7-116">Era year ranges</span></span>

- <span data-ttu-id="e3dc7-117">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che hanno overflow di un intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="e3dc7-118">Impostazione predefinita: i controlli intervallo sono rilassati (`false`).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="e3dc7-119">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="e3dc7-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-120">Setting name</span></span> | <span data-ttu-id="e3dc7-121">Valori</span><span class="sxs-lookup"><span data-stu-id="e3dc7-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e3dc7-122">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="e3dc7-123">Controlli intervallo `false`-rilassato</span><span class="sxs-lookup"><span data-stu-id="e3dc7-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="e3dc7-124">`true`-overflow genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="e3dc7-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-125">**Environment variable**</span></span> | <span data-ttu-id="e3dc7-126">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-126">N/A</span></span> | <span data-ttu-id="e3dc7-127">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="e3dc7-128">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="e3dc7-128">Japanese date parsing</span></span>

- <span data-ttu-id="e3dc7-129">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="e3dc7-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="e3dc7-130">Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="e3dc7-131">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e3dc7-132">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-132">Setting name</span></span> | <span data-ttu-id="e3dc7-133">Valori</span><span class="sxs-lookup"><span data-stu-id="e3dc7-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e3dc7-134">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="e3dc7-135">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="e3dc7-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="e3dc7-136">è supportato solo `true` "1"</span><span class="sxs-lookup"><span data-stu-id="e3dc7-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="e3dc7-137">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-137">**Environment variable**</span></span> | <span data-ttu-id="e3dc7-138">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-138">N/A</span></span> | <span data-ttu-id="e3dc7-139">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="e3dc7-140">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="e3dc7-140">Japanese year format</span></span>

- <span data-ttu-id="e3dc7-141">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="e3dc7-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="e3dc7-142">Impostazione predefinita: formattare il primo anno come "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="e3dc7-143">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e3dc7-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e3dc7-144">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e3dc7-144">Setting name</span></span> | <span data-ttu-id="e3dc7-145">Valori</span><span class="sxs-lookup"><span data-stu-id="e3dc7-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e3dc7-146">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="e3dc7-147">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="e3dc7-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="e3dc7-148">`true`-formatta come numero</span><span class="sxs-lookup"><span data-stu-id="e3dc7-148">`true` - format as number</span></span> |
| <span data-ttu-id="e3dc7-149">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e3dc7-149">**Environment variable**</span></span> | <span data-ttu-id="e3dc7-150">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-150">N/A</span></span> | <span data-ttu-id="e3dc7-151">N/D</span><span class="sxs-lookup"><span data-stu-id="e3dc7-151">N/A</span></span> |
