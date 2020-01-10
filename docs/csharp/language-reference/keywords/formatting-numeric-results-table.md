---
title: Tabella di formattazione dei risultati numerici - Riferimenti per C#
description: Informazioni sulle stringhe in formato numerico standard di C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: eb93f0a4f3c66e9f7b295366a77b9fb099fc3a1e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713503"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="936f3-103">Tabella di formattazione dei risultati numerici (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="936f3-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="936f3-104">Nella tabella seguente vengono descritti gli identificatori di formato supportati per la formattazione dei risultati numerici.</span><span class="sxs-lookup"><span data-stu-id="936f3-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="936f3-105">Il risultato formattato nell'ultima colonna corrisponde al valore <xref:System.Globalization.CultureInfo> "en-US".</span><span class="sxs-lookup"><span data-stu-id="936f3-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="936f3-106">Identificatore di formato</span><span class="sxs-lookup"><span data-stu-id="936f3-106">Format specifier</span></span>|<span data-ttu-id="936f3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="936f3-107">Description</span></span>|<span data-ttu-id="936f3-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="936f3-108">Examples</span></span>|<span data-ttu-id="936f3-109">Risultato</span><span class="sxs-lookup"><span data-stu-id="936f3-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="936f3-110">C o c</span><span class="sxs-lookup"><span data-stu-id="936f3-110">C or c</span></span>|<span data-ttu-id="936f3-111">Valuta</span><span class="sxs-lookup"><span data-stu-id="936f3-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="936f3-112">\\$2,50</span><span class="sxs-lookup"><span data-stu-id="936f3-112">\\$2.50</span></span><br /><br /> <span data-ttu-id="936f3-113">(\\$2,50)</span><span class="sxs-lookup"><span data-stu-id="936f3-113">(\\$2.50)</span></span>|  
|<span data-ttu-id="936f3-114">D o d</span><span class="sxs-lookup"><span data-stu-id="936f3-114">D or d</span></span>|<span data-ttu-id="936f3-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="936f3-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="936f3-116">00025</span><span class="sxs-lookup"><span data-stu-id="936f3-116">00025</span></span>|  
|<span data-ttu-id="936f3-117">E o e</span><span class="sxs-lookup"><span data-stu-id="936f3-117">E or e</span></span>|<span data-ttu-id="936f3-118">Esponenziale</span><span class="sxs-lookup"><span data-stu-id="936f3-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="936f3-119">2,50E+005</span><span class="sxs-lookup"><span data-stu-id="936f3-119">2.50E+005</span></span>|  
|<span data-ttu-id="936f3-120">F o f</span><span class="sxs-lookup"><span data-stu-id="936f3-120">F or f</span></span>|<span data-ttu-id="936f3-121">A virgola fissa</span><span class="sxs-lookup"><span data-stu-id="936f3-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="936f3-122">2.50</span><span class="sxs-lookup"><span data-stu-id="936f3-122">2.50</span></span><br /><br /> <span data-ttu-id="936f3-123">3\.</span><span class="sxs-lookup"><span data-stu-id="936f3-123">3</span></span>|  
|<span data-ttu-id="936f3-124">G o g</span><span class="sxs-lookup"><span data-stu-id="936f3-124">G or g</span></span>|<span data-ttu-id="936f3-125">Generale</span><span class="sxs-lookup"><span data-stu-id="936f3-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="936f3-126">2.5</span><span class="sxs-lookup"><span data-stu-id="936f3-126">2.5</span></span>|  
|<span data-ttu-id="936f3-127">N o n</span><span class="sxs-lookup"><span data-stu-id="936f3-127">N or n</span></span>|<span data-ttu-id="936f3-128">Numerico</span><span class="sxs-lookup"><span data-stu-id="936f3-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="936f3-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="936f3-129">2,500,000.00</span></span>|  
|<span data-ttu-id="936f3-130">P o p</span><span class="sxs-lookup"><span data-stu-id="936f3-130">P or p</span></span>|<span data-ttu-id="936f3-131">Percentuale</span><span class="sxs-lookup"><span data-stu-id="936f3-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="936f3-132">25,00%</span><span class="sxs-lookup"><span data-stu-id="936f3-132">25.00%</span></span>|  
|<span data-ttu-id="936f3-133">R o r</span><span class="sxs-lookup"><span data-stu-id="936f3-133">R or r</span></span>|<span data-ttu-id="936f3-134">Round trip</span><span class="sxs-lookup"><span data-stu-id="936f3-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="936f3-135">2.5</span><span class="sxs-lookup"><span data-stu-id="936f3-135">2.5</span></span>|  
|<span data-ttu-id="936f3-136">X o x</span><span class="sxs-lookup"><span data-stu-id="936f3-136">X or x</span></span>|<span data-ttu-id="936f3-137">Esadecimale</span><span class="sxs-lookup"><span data-stu-id="936f3-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="936f3-138">FA</span><span class="sxs-lookup"><span data-stu-id="936f3-138">FA</span></span><br /><br /> <span data-ttu-id="936f3-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="936f3-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="936f3-140">Note</span><span class="sxs-lookup"><span data-stu-id="936f3-140">Remarks</span></span>

<span data-ttu-id="936f3-141">Usare un identificatore di formato per creare una stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="936f3-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="936f3-142">La stringa di formato ha il formato seguente: `Axx`, dove</span><span class="sxs-lookup"><span data-stu-id="936f3-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="936f3-143">`A` è l'identificatore di formato, che controlla il tipo di formattazione applicato al valore numerico.</span><span class="sxs-lookup"><span data-stu-id="936f3-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="936f3-144">`xx` è l'identificatore di precisione, che controlla il numero di cifre nell'output formattato.</span><span class="sxs-lookup"><span data-stu-id="936f3-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="936f3-145">Il valore dell'identificatore della precisione è compreso tra 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="936f3-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="936f3-146">Gli identificatori di formato decimale ("D" o "d") ed esadecimale ("X" o "x") sono supportati solo per i tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="936f3-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="936f3-147">L'identificatore di formato round trip ("R" o "r") è supportato solo per i tipi <xref:System.Single>, <xref:System.Double> e <xref:System.Numerics.BigInteger>.</span><span class="sxs-lookup"><span data-stu-id="936f3-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="936f3-148">Le stringhe di formato numerico standard sono supportate:</span><span class="sxs-lookup"><span data-stu-id="936f3-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="936f3-149">Da alcuni overload del metodo `ToString` di tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="936f3-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="936f3-150">È ad esempio possibile fornire una stringa di formato numerico ai metodi <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> e <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="936f3-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="936f3-151">Dalla [funzionalità di formattazione composita](../../../standard/base-types/composite-formatting.md) di .NET, che è ad esempio supportata dal metodo <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="936f3-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="936f3-152">[Stringhe interpolate](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="936f3-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="936f3-153">Per altre informazioni, vedere [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="936f3-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="936f3-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="936f3-154">See also</span></span>

- [<span data-ttu-id="936f3-155">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="936f3-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="936f3-156">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="936f3-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="936f3-157">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="936f3-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="936f3-158">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="936f3-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="936f3-159">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="936f3-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="936f3-160">string</span><span class="sxs-lookup"><span data-stu-id="936f3-160">string</span></span>](../builtin-types/reference-types.md)
