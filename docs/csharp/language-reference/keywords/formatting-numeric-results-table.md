---
title: Tabella di formattazione dei risultati numerici (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16976f5a59bd4eb0eca29553aff87d4fe0b1d247
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="e5e10-102">Tabella di formattazione dei risultati numerici (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e5e10-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="e5e10-103">È possibile formattare i risultati numerici usando il metodo <xref:System.String.Format%2A?displayProperty=fullName> o con il metodo <xref:System.Console.Write%2A?displayProperty=fullName> o <xref:System.Console.WriteLine%2A?displayProperty=fullName> che chiama `String.Format`.</span><span class="sxs-lookup"><span data-stu-id="e5e10-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=fullName> method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> or <xref:System.Console.WriteLine%2A?displayProperty=fullName> method, which calls `String.Format`.</span></span> <span data-ttu-id="e5e10-104">Il formato è specificato dalle stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="e5e10-104">The format is specified by using format strings.</span></span> <span data-ttu-id="e5e10-105">La tabella seguente contiene le stringhe di formato standard supportate.</span><span class="sxs-lookup"><span data-stu-id="e5e10-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="e5e10-106">La stringa di formato ha questo aspetto: `Axx`, dove `A` è l'identificatore del formato e `xx` è l'identificatore della precisione.</span><span class="sxs-lookup"><span data-stu-id="e5e10-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="e5e10-107">L'identificatore del formato controlla il tipo di formattazione applicato al valore numerico e l'identificatore della precisione controlla il numero di cifre significative o di decimali dell'output formattato.</span><span class="sxs-lookup"><span data-stu-id="e5e10-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="e5e10-108">Il valore dell'identificatore della precisione è compreso tra 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="e5e10-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="e5e10-109">Per altre informazioni sulle stringhe di formato numerico standard, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="e5e10-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="e5e10-110">Per ulteriori informazioni sul metodo `String.Format`, vedere <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e5e10-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
|<span data-ttu-id="e5e10-111">Identificatore di formato</span><span class="sxs-lookup"><span data-stu-id="e5e10-111">Format Specifier</span></span>|<span data-ttu-id="e5e10-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5e10-112">Description</span></span>|<span data-ttu-id="e5e10-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="e5e10-113">Examples</span></span>|<span data-ttu-id="e5e10-114">Output</span><span class="sxs-lookup"><span data-stu-id="e5e10-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="e5e10-115">C o c</span><span class="sxs-lookup"><span data-stu-id="e5e10-115">C or c</span></span>|<span data-ttu-id="e5e10-116">Valuta</span><span class="sxs-lookup"><span data-stu-id="e5e10-116">Currency</span></span>|<span data-ttu-id="e5e10-117">Console.Write("{0:C}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="e5e10-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="e5e10-118">Console.Write("{0:C}", -2.5);</span><span class="sxs-lookup"><span data-stu-id="e5e10-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="e5e10-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="e5e10-119">$2.50</span></span><br /><br /> <span data-ttu-id="e5e10-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="e5e10-120">($2.50)</span></span>|  
|<span data-ttu-id="e5e10-121">D o d</span><span class="sxs-lookup"><span data-stu-id="e5e10-121">D or d</span></span>|<span data-ttu-id="e5e10-122">Decimal</span><span class="sxs-lookup"><span data-stu-id="e5e10-122">Decimal</span></span>|<span data-ttu-id="e5e10-123">Console.Write("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="e5e10-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="e5e10-124">00025</span><span class="sxs-lookup"><span data-stu-id="e5e10-124">00025</span></span>|  
|<span data-ttu-id="e5e10-125">E o e</span><span class="sxs-lookup"><span data-stu-id="e5e10-125">E or e</span></span>|<span data-ttu-id="e5e10-126">Scientifico</span><span class="sxs-lookup"><span data-stu-id="e5e10-126">Scientific</span></span>|<span data-ttu-id="e5e10-127">Console.Write("{0:E}", 250000);</span><span class="sxs-lookup"><span data-stu-id="e5e10-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="e5e10-128">2.500000E+005</span><span class="sxs-lookup"><span data-stu-id="e5e10-128">2.500000E+005</span></span>|  
|<span data-ttu-id="e5e10-129">F o f</span><span class="sxs-lookup"><span data-stu-id="e5e10-129">F or f</span></span>|<span data-ttu-id="e5e10-130">A virgola fissa</span><span class="sxs-lookup"><span data-stu-id="e5e10-130">Fixed-point</span></span>|<span data-ttu-id="e5e10-131">Console.Write("{0:F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="e5e10-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="e5e10-132">Console.Write("{0:F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="e5e10-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="e5e10-133">25.00</span><span class="sxs-lookup"><span data-stu-id="e5e10-133">25.00</span></span><br /><br /> <span data-ttu-id="e5e10-134">25</span><span class="sxs-lookup"><span data-stu-id="e5e10-134">25</span></span>|  
|<span data-ttu-id="e5e10-135">G o g</span><span class="sxs-lookup"><span data-stu-id="e5e10-135">G or g</span></span>|<span data-ttu-id="e5e10-136">Generale</span><span class="sxs-lookup"><span data-stu-id="e5e10-136">General</span></span>|<span data-ttu-id="e5e10-137">Console.Write("{0:G}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="e5e10-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="e5e10-138">2.5</span><span class="sxs-lookup"><span data-stu-id="e5e10-138">2.5</span></span>|  
|<span data-ttu-id="e5e10-139">N o n</span><span class="sxs-lookup"><span data-stu-id="e5e10-139">N or n</span></span>|<span data-ttu-id="e5e10-140">Number</span><span class="sxs-lookup"><span data-stu-id="e5e10-140">Number</span></span>|<span data-ttu-id="e5e10-141">Console.Write("{0:N}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="e5e10-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="e5e10-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="e5e10-142">2,500,000.00</span></span>|  
|<span data-ttu-id="e5e10-143">X o x</span><span class="sxs-lookup"><span data-stu-id="e5e10-143">X or x</span></span>|<span data-ttu-id="e5e10-144">Esadecimale</span><span class="sxs-lookup"><span data-stu-id="e5e10-144">Hexadecimal</span></span>|<span data-ttu-id="e5e10-145">Console.Write("{0:X}", 250);</span><span class="sxs-lookup"><span data-stu-id="e5e10-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="e5e10-146">Console.Write("{0:X}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="e5e10-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="e5e10-147">FA</span><span class="sxs-lookup"><span data-stu-id="e5e10-147">FA</span></span><br /><br /> <span data-ttu-id="e5e10-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="e5e10-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5e10-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5e10-149">See Also</span></span>  
 <span data-ttu-id="e5e10-150">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5e10-150">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e5e10-151">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5e10-151">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e5e10-152">[Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="e5e10-152">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="e5e10-153">[Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="e5e10-153">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="e5e10-154">string</span><span class="sxs-lookup"><span data-stu-id="e5e10-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)

