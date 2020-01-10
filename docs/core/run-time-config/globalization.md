---
title: Impostazioni di configurazione della globalizzazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano gli aspetti di globalizzazione di un'app .NET Core, ad esempio il modo in cui analizza le date giapponesi.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740535"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="6e522-103">Opzioni di configurazione della fase di esecuzione per la globalizzazione</span><span class="sxs-lookup"><span data-stu-id="6e522-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="6e522-104">Modalità invariante</span><span class="sxs-lookup"><span data-stu-id="6e522-104">Invariant mode</span></span>

- <span data-ttu-id="6e522-105">Determina se un'app .NET Core viene eseguita in modalità invariante di globalizzazione senza accedere a dati e comportamenti specifici delle impostazioni cultura o se può accedere ai dati culturali.</span><span class="sxs-lookup"><span data-stu-id="6e522-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="6e522-106">Impostazione predefinita: eseguire l'app con accesso ai dati culturali (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e522-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="6e522-107">Per altre informazioni, vedere [modalità invariante per la globalizzazione di .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6e522-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="6e522-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6e522-108">Setting name</span></span> | <span data-ttu-id="6e522-109">Valori</span><span class="sxs-lookup"><span data-stu-id="6e522-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="6e522-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="6e522-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="6e522-111">`false` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="6e522-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="6e522-112">`true`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="6e522-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="6e522-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6e522-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="6e522-114">`0` l'accesso ai dati culturali</span><span class="sxs-lookup"><span data-stu-id="6e522-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="6e522-115">`1`-esecuzione in modalità invariante</span><span class="sxs-lookup"><span data-stu-id="6e522-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="6e522-116">Intervalli di anni dell'era</span><span class="sxs-lookup"><span data-stu-id="6e522-116">Era year ranges</span></span>

- <span data-ttu-id="6e522-117">Determina se i controlli di intervallo per i calendari che supportano più ere sono rilassati o se le date che hanno overflow di un intervallo di date di un'era generano una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="6e522-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="6e522-118">Impostazione predefinita: i controlli intervallo sono rilassati (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e522-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="6e522-119">Per altre informazioni, vedere [calendari, ere e intervalli di date: controlli intervallo rilassato](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="6e522-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="6e522-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6e522-120">Setting name</span></span> | <span data-ttu-id="6e522-121">Valori</span><span class="sxs-lookup"><span data-stu-id="6e522-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="6e522-122">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="6e522-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="6e522-123">Controlli intervallo `false`-rilassato</span><span class="sxs-lookup"><span data-stu-id="6e522-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="6e522-124">`true`-overflow genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="6e522-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="6e522-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6e522-125">**Environment variable**</span></span> | <span data-ttu-id="6e522-126">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-126">N/A</span></span> | <span data-ttu-id="6e522-127">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="6e522-128">Analisi della data giapponese</span><span class="sxs-lookup"><span data-stu-id="6e522-128">Japanese date parsing</span></span>

- <span data-ttu-id="6e522-129">Determina se una stringa che contiene "1" o "Gannen" come l'anno viene analizzata correttamente o se è supportato solo "1".</span><span class="sxs-lookup"><span data-stu-id="6e522-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="6e522-130">Impostazione predefinita: analizza le stringhe che contengono "1" o "Gannen" come anno (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e522-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="6e522-131">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="6e522-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="6e522-132">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6e522-132">Setting name</span></span> | <span data-ttu-id="6e522-133">Valori</span><span class="sxs-lookup"><span data-stu-id="6e522-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="6e522-134">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="6e522-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="6e522-135">`false`-"Gannen" o "1" è supportato</span><span class="sxs-lookup"><span data-stu-id="6e522-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="6e522-136">è supportato solo `true` "1"</span><span class="sxs-lookup"><span data-stu-id="6e522-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="6e522-137">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6e522-137">**Environment variable**</span></span> | <span data-ttu-id="6e522-138">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-138">N/A</span></span> | <span data-ttu-id="6e522-139">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="6e522-140">Formato dell'anno giapponese</span><span class="sxs-lookup"><span data-stu-id="6e522-140">Japanese year format</span></span>

- <span data-ttu-id="6e522-141">Determina se il primo anno di un'era del calendario giapponese è formattato come "Gannen" o come numero.</span><span class="sxs-lookup"><span data-stu-id="6e522-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="6e522-142">Impostazione predefinita: formattare il primo anno come "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e522-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="6e522-143">Per altre informazioni, vedere [rappresentare date in calendari con più ere](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="6e522-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="6e522-144">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6e522-144">Setting name</span></span> | <span data-ttu-id="6e522-145">Valori</span><span class="sxs-lookup"><span data-stu-id="6e522-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="6e522-146">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="6e522-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="6e522-147">`false`-Format come "Gannen"</span><span class="sxs-lookup"><span data-stu-id="6e522-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="6e522-148">`true`-formatta come numero</span><span class="sxs-lookup"><span data-stu-id="6e522-148">`true` - format as number</span></span> |
| <span data-ttu-id="6e522-149">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6e522-149">**Environment variable**</span></span> | <span data-ttu-id="6e522-150">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-150">N/A</span></span> | <span data-ttu-id="6e522-151">N/D</span><span class="sxs-lookup"><span data-stu-id="6e522-151">N/A</span></span> |
