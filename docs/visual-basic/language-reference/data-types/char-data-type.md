---
title: Tipo di dati Char
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 3dbbf9f6a2c4079775e05f5d2dcd8704c1ec4259
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387478"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="092b9-102">Tipo di dati Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="092b9-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="092b9-103">Include punti di codice senza segno a 16 bit (2 byte) compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="092b9-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="092b9-104">Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="092b9-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="092b9-105">Commenti</span><span class="sxs-lookup"><span data-stu-id="092b9-105">Remarks</span></span>

<span data-ttu-id="092b9-106">Utilizzare il `Char` tipo di dati quando è necessario mantenere un solo carattere e non è necessario il sovraccarico di `String` .</span><span class="sxs-lookup"><span data-stu-id="092b9-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="092b9-107">In alcuni casi è possibile usare `Char()` , una matrice di `Char` elementi, per mantenere più caratteri.</span><span class="sxs-lookup"><span data-stu-id="092b9-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="092b9-108">Il valore predefinito di `Char` è il carattere con un punto di codice 0.</span><span class="sxs-lookup"><span data-stu-id="092b9-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="092b9-109">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="092b9-109">Unicode Characters</span></span>

<span data-ttu-id="092b9-110">I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="092b9-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="092b9-111">Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="092b9-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="092b9-112">I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni.</span><span class="sxs-lookup"><span data-stu-id="092b9-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="092b9-113">Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli, inclusi i caratteri testuali in tutto il mondo, i segni diacritici e i simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="092b9-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="092b9-114">È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su una `Char` variabile per determinare la relativa classificazione Unicode.</span><span class="sxs-lookup"><span data-stu-id="092b9-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="092b9-115">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="092b9-115">Type Conversions</span></span>

<span data-ttu-id="092b9-116">Visual Basic non esegue la conversione direttamente tra `Char` e i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="092b9-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="092b9-117">È possibile utilizzare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> <xref:Microsoft.VisualBasic.Strings.AscW%2A> funzione o per convertire un `Char` valore in un oggetto `Integer` che rappresenta il punto di codice.</span><span class="sxs-lookup"><span data-stu-id="092b9-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="092b9-118">È possibile usare la <xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> funzione o per convertire un `Integer` valore in un oggetto con `Char` tale punto di codice.</span><span class="sxs-lookup"><span data-stu-id="092b9-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="092b9-119">Se l'opzione di controllo del tipo (l' [istruzione Option Strict](../statements/option-strict-statement.md)) è impostata su on, è necessario aggiungere il carattere di tipo letterale a un valore letterale stringa a carattere singolo per identificarlo come `Char` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="092b9-119">If the type checking switch (the [Option Strict Statement](../statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="092b9-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="092b9-120">The following example illustrates this.</span></span> <span data-ttu-id="092b9-121">La prima assegnazione alla `charVar` variabile genera l'errore del compilatore [BC30512](../../misc/bc30512.md) perché `Option Strict` è on.</span><span class="sxs-lookup"><span data-stu-id="092b9-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="092b9-122">Il secondo compila correttamente perché il `c` carattere di tipo letterale identifica il valore letterale come `Char` valore.</span><span class="sxs-lookup"><span data-stu-id="092b9-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a><span data-ttu-id="092b9-123">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="092b9-123">Programming Tips</span></span>

- <span data-ttu-id="092b9-124">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="092b9-124">**Negative Numbers.**</span></span> <span data-ttu-id="092b9-125">`Char`è un tipo senza segno e non può rappresentare un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="092b9-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="092b9-126">In ogni caso, è consigliabile non usare `Char` per mantenere i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="092b9-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="092b9-127">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="092b9-127">**Interop Considerations.**</span></span> <span data-ttu-id="092b9-128">Se si interfaccia con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno una larghezza dati diversa (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="092b9-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="092b9-129">Se si passa un argomento a 8 bit a tale componente, dichiararlo come `Byte` anziché `Char` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="092b9-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="092b9-130">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="092b9-130">**Widening.**</span></span> <span data-ttu-id="092b9-131">Il `Char` tipo di dati viene ampliato a `String` .</span><span class="sxs-lookup"><span data-stu-id="092b9-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="092b9-132">Ciò significa che è possibile convertire `Char` in `String` e non si verificherà un oggetto <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="092b9-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="092b9-133">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="092b9-133">**Type Characters.**</span></span> <span data-ttu-id="092b9-134">L'aggiunta del carattere di tipo letterale `C` a un valore letterale stringa a carattere singolo lo impone al `Char` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="092b9-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="092b9-135">`Char`non ha un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="092b9-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="092b9-136">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="092b9-136">**Framework Type.**</span></span> <span data-ttu-id="092b9-137">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="092b9-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="092b9-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="092b9-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="092b9-139">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="092b9-139">Data Types</span></span>](index.md)
- [<span data-ttu-id="092b9-140">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="092b9-140">String Data Type</span></span>](string-data-type.md)
- [<span data-ttu-id="092b9-141">CString</span><span class="sxs-lookup"><span data-stu-id="092b9-141">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="092b9-142">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="092b9-142">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="092b9-143">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="092b9-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="092b9-144">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="092b9-144">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
