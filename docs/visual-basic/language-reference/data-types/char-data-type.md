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
ms.openlocfilehash: 09b0162068bc068bd77612816626897ec4a151d9
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42911967"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="af904-102">Tipo di dati Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af904-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="af904-103">Contiene punti di codice (a 2 byte) a 16 bit senza segno compresi nell'intervallo compreso tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="af904-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="af904-104">Ciascuna *punto di codice*, o il codice carattere rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="af904-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af904-105">Note</span><span class="sxs-lookup"><span data-stu-id="af904-105">Remarks</span></span>  
 <span data-ttu-id="af904-106">Usare la `Char` quando è necessario contenere un solo tipo di dati carattere e non è necessario l'overhead di `String`.</span><span class="sxs-lookup"><span data-stu-id="af904-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="af904-107">In alcuni casi è possibile usare `Char()`, una matrice di `Char` elementi, per contenere più caratteri.</span><span class="sxs-lookup"><span data-stu-id="af904-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="af904-108">Il valore predefinito di `Char` è il carattere con un punto di codice pari a 0.</span><span class="sxs-lookup"><span data-stu-id="af904-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="af904-109">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="af904-109">Unicode Characters</span></span>  
 <span data-ttu-id="af904-110">I punti di 128 codice (0-127) prima di Unicode corrispondono alle lettere e simboli di una tastiera US standard.</span><span class="sxs-lookup"><span data-stu-id="af904-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="af904-111">Questi primi punti di 128 codice sono identici a quelli definisce il set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="af904-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="af904-112">I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, ad esempio lettere dell'alfabeto basati sull'alfabeto latino, accenti, i simboli di valuta e le frazioni.</span><span class="sxs-lookup"><span data-stu-id="af904-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="af904-113">Unicode utilizza i punti di codice rimanenti (256 e 65535) per un'ampia gamma di simboli, inclusi i caratteri di testo in tutto il mondo, i segni diacritici e simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="af904-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="af904-114">È possibile usare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un `Char` variabile per determinarne la classificazione di Unicode.</span><span class="sxs-lookup"><span data-stu-id="af904-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="af904-115">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="af904-115">Type Conversions</span></span>  
 <span data-ttu-id="af904-116">Visual Basic non converte direttamente tra `Char` e i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="af904-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="af904-117">È possibile usare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> oppure <xref:Microsoft.VisualBasic.Strings.AscW%2A> funzione per convertire un `Char` valore un `Integer` che rappresenta il punto di codice.</span><span class="sxs-lookup"><span data-stu-id="af904-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="af904-118">È possibile usare il <xref:Microsoft.VisualBasic.Strings.Chr%2A> oppure <xref:Microsoft.VisualBasic.Strings.ChrW%2A> funzione per convertire un `Integer` valore un `Char` che dispone di tale punto di codice.</span><span class="sxs-lookup"><span data-stu-id="af904-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="af904-119">Se il controllo del tipo passa ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) è attivo, è necessario aggiungere il carattere di tipo di valore letterale in una stringa di caratteri a un valore letterale per identificarlo come il `Char` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="af904-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="af904-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="af904-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="af904-121">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="af904-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="af904-122">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="af904-122">**Negative Numbers.**</span></span> <span data-ttu-id="af904-123">`Char` è un tipo senza segno e non può rappresentare un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="af904-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="af904-124">In ogni caso, è consigliabile non usare `Char` per contenere valori numerici.</span><span class="sxs-lookup"><span data-stu-id="af904-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="af904-125">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="af904-125">**Interop Considerations.**</span></span> <span data-ttu-id="af904-126">Se si deve interfacciare con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno un'ampiezza dei dati diverse (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="af904-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="af904-127">Se si passa un argomento a 8 bit da tale componente, dichiararlo come `Byte` invece di `Char` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="af904-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="af904-128">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="af904-128">**Widening.**</span></span> <span data-ttu-id="af904-129">Il `Char` può ampliarsi nel tipo di dati `String`.</span><span class="sxs-lookup"><span data-stu-id="af904-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="af904-130">Ciò significa che è possibile convertire `Char` al `String` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="af904-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="af904-131">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="af904-131">**Type Characters.**</span></span> <span data-ttu-id="af904-132">Aggiungendo il carattere di tipo di valore letterale `C` a una stringa di caratteri a un valore letterale, se ne determina la `Char` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="af904-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="af904-133">`Char` possiede alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="af904-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="af904-134">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="af904-134">**Framework Type.**</span></span> <span data-ttu-id="af904-135">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af904-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af904-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af904-136">See Also</span></span>  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="af904-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="af904-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="af904-138">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="af904-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="af904-139">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="af904-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="af904-140">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="af904-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="af904-141">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="af904-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="af904-142">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="af904-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
