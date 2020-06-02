---
title: 'Procedura: Aggiungere zeri iniziali a un numero'
ms.date: 02/25/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: ef18fb1bb7b1592a4e92866028868bf1cf793bbf
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290461"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="9c300-102">Procedura: Aggiungere zeri iniziali a un numero</span><span class="sxs-lookup"><span data-stu-id="9c300-102">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="9c300-103">È possibile aggiungere degli zeri iniziali a un numero intero usando la [stringa di formato numerico standard](standard-numeric-format-strings.md) "D" con un identificatore di precisione.</span><span class="sxs-lookup"><span data-stu-id="9c300-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="9c300-104">È possibile aggiungere zeri iniziali sia ai numeri interi che ai numeri a virgola mobile usando una [stringa di formato numerico personalizzata](custom-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="9c300-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](custom-numeric-format-strings.md).</span></span> <span data-ttu-id="9c300-105">Questo argomento illustra come usare entrambi i metodi per aggiungere gli zeri iniziali a un numero.</span><span class="sxs-lookup"><span data-stu-id="9c300-105">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="9c300-106">Per aggiungere un intero con gli zeri iniziali a una lunghezza specifica</span><span class="sxs-lookup"><span data-stu-id="9c300-106">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="9c300-107">Determinare il numero minimo di cifre da visualizzare nel valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="9c300-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="9c300-108">Includere eventuali cifre iniziali nel numero.</span><span class="sxs-lookup"><span data-stu-id="9c300-108">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="9c300-109">Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9c300-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="9c300-110">Per visualizzare il valore di tipo Integer come valore decimale, chiamare il metodo `ToString(String)` e passare la stringa "D*n*" come valore del parametro `format`, dove *n* rappresenta la lunghezza minima della stringa.</span><span class="sxs-lookup"><span data-stu-id="9c300-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="9c300-111">Per visualizzare il numero intero come valore esadecimale, chiamare il metodo `ToString(String)` e passare la stringa "X*n*" come valore del parametro format, dove *n* rappresenta la lunghezza minima della stringa.</span><span class="sxs-lookup"><span data-stu-id="9c300-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="9c300-112">È anche possibile formattare la stringa come stringa interpolata in [C#](../../csharp/language-reference/tokens/interpolated.md) e in [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) oppure chiamare un metodo, come <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, che usa la [formattazione composita](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9c300-112">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](composite-formatting.md).</span></span>

<span data-ttu-id="9c300-113">Il seguente esempio formatta diversi valori di tipo Integer con gli zeri iniziali in modo che la lunghezza totale del numero formattato sia almeno di otto caratteri.</span><span class="sxs-lookup"><span data-stu-id="9c300-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="9c300-114">Per aggiungere un intero con un determinato numero di zeri iniziali</span><span class="sxs-lookup"><span data-stu-id="9c300-114">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="9c300-115">Determinare il numero di zeri iniziali da visualizzare nel valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="9c300-115">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="9c300-116">Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9c300-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="9c300-117">Per applicare la formattazione come valore decimale, è necessario usare l'identificatore di formato standard "D".</span><span class="sxs-lookup"><span data-stu-id="9c300-117">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="9c300-118">Per applicare la formattazione come valore esadecimale, è necessario usare l'identificatore di formato standard "X".</span><span class="sxs-lookup"><span data-stu-id="9c300-118">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="9c300-119">Determine la lunghezza della stringa numerica non aggiunta chiamando il metodo `ToString("D").Length` o `ToString("X").Length` del valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="9c300-119">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="9c300-120">Aggiungere il numero di zeri iniziali da includere nella stringa formattata nella lunghezza della stringa numerica non aggiunta.</span><span class="sxs-lookup"><span data-stu-id="9c300-120">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="9c300-121">L'aggiunta del numero di zeri iniziali definisce la lunghezza della stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="9c300-121">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="9c300-122">Chiamare il metodo `ToString(String)` del valore integer e passare la stringa "D*n*" per le stringhe decimali e la stringa "X*n*" per quelle esadecimali, dove *n* rappresenta la lunghezza totale della stringa aggiunta.</span><span class="sxs-lookup"><span data-stu-id="9c300-122">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="9c300-123">È anche possibile usare la stringa di formato "D*n*" o "X*n*" in un metodo che supporta la formattazione composta.</span><span class="sxs-lookup"><span data-stu-id="9c300-123">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="9c300-124">Il seguente esempio aggiunge un valore di tipo Integer con cinque zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="9c300-124">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="9c300-125">Per aggiungere un valore numerico con gli zeri iniziali a una lunghezza specifica</span><span class="sxs-lookup"><span data-stu-id="9c300-125">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="9c300-126">Determinare il numero di cifre alla sinistra del decimale che deve avere la rappresentazione della stringa del numero.</span><span class="sxs-lookup"><span data-stu-id="9c300-126">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="9c300-127">Includere gli eventuali zeri iniziali nel numero totale di cifre.</span><span class="sxs-lookup"><span data-stu-id="9c300-127">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="9c300-128">Definire una stringa in formato numerico personalizzato in cui si usa un segnaposto zero "0" per rappresentare il numero minimo di zeri.</span><span class="sxs-lookup"><span data-stu-id="9c300-128">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="9c300-129">Chiamare il metodo `ToString(String)` del numero e passarlo alla stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9c300-129">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="9c300-130">È anche possibile usare la stringa in formato personalizzato con un metodo che supporta la formattazione composita.</span><span class="sxs-lookup"><span data-stu-id="9c300-130">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="9c300-131">L'esempio seguente formatta diversi valori numerici con gli zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="9c300-131">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="9c300-132">Di conseguenza, la lunghezza totale del numero formattato è di almeno otto cifre a sinistra del decimale.</span><span class="sxs-lookup"><span data-stu-id="9c300-132">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="9c300-133">Per aggiungere un valore numerico con un determinato numero di zeri iniziali</span><span class="sxs-lookup"><span data-stu-id="9c300-133">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="9c300-134">Determinare il numero di zeri iniziali che deve avere il valore numerico.</span><span class="sxs-lookup"><span data-stu-id="9c300-134">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="9c300-135">Determinare il numero di cifre a sinistra del decimale nella stringa numerica senza aggiunta di zeri iniziali:</span><span class="sxs-lookup"><span data-stu-id="9c300-135">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="9c300-136">Determinare se la rappresentazione della stringa di un numero include un simbolo di separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="9c300-136">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="9c300-137">In questo caso, determinare il numero di caratteri alla sinistra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="9c300-137">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="9c300-138">-oppure-</span><span class="sxs-lookup"><span data-stu-id="9c300-138">-or-</span></span>

         <span data-ttu-id="9c300-139">In caso contrario, determinare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="9c300-139">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="9c300-140">Creare una stringa in formato personalizzato in cui si usa:</span><span class="sxs-lookup"><span data-stu-id="9c300-140">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="9c300-141">Il segnaposto zero "0" per ogni zero iniziale da visualizzare nella stringa.</span><span class="sxs-lookup"><span data-stu-id="9c300-141">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="9c300-142">Il segnaposto zero o il segnaposto di cifra "#" per rappresentare ogni cifra nella stringa predefinita.</span><span class="sxs-lookup"><span data-stu-id="9c300-142">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="9c300-143">Fornire la stringa di formato personalizzata come parametro nel metodo `ToString(String)` del numero o in un metodo che supporta la formattazione composta.</span><span class="sxs-lookup"><span data-stu-id="9c300-143">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="9c300-144">Il seguente esempio aggiunge due valori <xref:System.Double> con cinque zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="9c300-144">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="9c300-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c300-145">See also</span></span>

- [<span data-ttu-id="9c300-146">Stringhe di formato numerico personalizzato</span><span class="sxs-lookup"><span data-stu-id="9c300-146">Custom Numeric Format Strings</span></span>](custom-numeric-format-strings.md)
- [<span data-ttu-id="9c300-147">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="9c300-147">Standard Numeric Format Strings</span></span>](standard-numeric-format-strings.md)
- [<span data-ttu-id="9c300-148">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="9c300-148">Composite Formatting</span></span>](composite-formatting.md)
