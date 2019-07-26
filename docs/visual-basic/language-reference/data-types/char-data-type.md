---
title: Tipo di dati Char (Visual Basic)
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
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512782"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="c9e47-102">Tipo di dati Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e47-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="c9e47-103">Include punti di codice senza segno a 16 bit (2 byte) compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="c9e47-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="c9e47-104">Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9e47-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9e47-105">Note</span><span class="sxs-lookup"><span data-stu-id="c9e47-105">Remarks</span></span>

<span data-ttu-id="c9e47-106">Utilizzare il `Char` tipo di dati quando è necessario mantenere un solo carattere e non è necessario il sovraccarico di `String`.</span><span class="sxs-lookup"><span data-stu-id="c9e47-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="c9e47-107">In alcuni casi è possibile usare `Char()`, una matrice di `Char` elementi, per mantenere più caratteri.</span><span class="sxs-lookup"><span data-stu-id="c9e47-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="c9e47-108">Il valore predefinito di `Char` è il carattere con un punto di codice 0.</span><span class="sxs-lookup"><span data-stu-id="c9e47-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="c9e47-109">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="c9e47-109">Unicode Characters</span></span>

<span data-ttu-id="c9e47-110">I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c9e47-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="c9e47-111">Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="c9e47-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="c9e47-112">I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni.</span><span class="sxs-lookup"><span data-stu-id="c9e47-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="c9e47-113">Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli, inclusi i caratteri testuali in tutto il mondo, i segni diacritici e i simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="c9e47-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="c9e47-114">È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su una `Char` variabile per determinare la relativa classificazione Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9e47-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="c9e47-115">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="c9e47-115">Type Conversions</span></span>

<span data-ttu-id="c9e47-116">Visual Basic non esegue la conversione direttamente `Char` tra e i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="c9e47-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="c9e47-117">È possibile utilizzare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> funzione <xref:Microsoft.VisualBasic.Strings.AscW%2A> o per convertire un `Char` valore in un `Integer` oggetto che rappresenta il punto di codice.</span><span class="sxs-lookup"><span data-stu-id="c9e47-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="c9e47-118">È possibile usare la <xref:Microsoft.VisualBasic.Strings.Chr%2A> funzione <xref:Microsoft.VisualBasic.Strings.ChrW%2A> o per convertire un `Integer` valore in un `Char` oggetto con tale punto di codice.</span><span class="sxs-lookup"><span data-stu-id="c9e47-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="c9e47-119">Se l'opzione di controllo del tipo ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) è impostata su on, è necessario aggiungere il carattere di tipo letterale a un valore letterale stringa `Char` a carattere singolo per identificarlo come tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c9e47-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="c9e47-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c9e47-120">The following example illustrates this.</span></span>

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a><span data-ttu-id="c9e47-121">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="c9e47-121">Programming Tips</span></span>

- <span data-ttu-id="c9e47-122">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="c9e47-122">**Negative Numbers.**</span></span> <span data-ttu-id="c9e47-123">`Char`è un tipo senza segno e non può rappresentare un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="c9e47-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="c9e47-124">In ogni caso, è consigliabile non usare `Char` per mantenere i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="c9e47-124">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="c9e47-125">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="c9e47-125">**Interop Considerations.**</span></span> <span data-ttu-id="c9e47-126">Se si interfaccia con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno una larghezza dati diversa (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="c9e47-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="c9e47-127">Se si passa un argomento a 8 bit a tale componente, dichiararlo come `Byte` `Char` anziché nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9e47-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="c9e47-128">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="c9e47-128">**Widening.**</span></span> <span data-ttu-id="c9e47-129">Il `Char` tipo di dati viene ampliato a `String`.</span><span class="sxs-lookup"><span data-stu-id="c9e47-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="c9e47-130">Ciò significa che è possibile `Char` eseguire `String` la conversione in e non <xref:System.OverflowException?displayProperty=nameWithType> si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="c9e47-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="c9e47-131">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="c9e47-131">**Type Characters.**</span></span> <span data-ttu-id="c9e47-132">L'aggiunta del carattere `C` di tipo letterale a un valore letterale stringa a carattere singolo lo impone `Char` al tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c9e47-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="c9e47-133">`Char`non ha un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="c9e47-133">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="c9e47-134">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="c9e47-134">**Framework Type.**</span></span> <span data-ttu-id="c9e47-135">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9e47-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9e47-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e47-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="c9e47-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c9e47-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="c9e47-138">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="c9e47-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="c9e47-139">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="c9e47-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c9e47-140">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="c9e47-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="c9e47-141">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="c9e47-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="c9e47-142">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c9e47-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
