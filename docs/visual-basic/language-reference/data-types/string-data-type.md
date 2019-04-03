---
title: Tipo di dati String (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 3e87dc6527b4351467b1155439ee8266157c16ff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842291"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="e0c8a-102">Tipo di dati String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0c8a-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="e0c8a-103">Contiene sequenze di punti di codice (a 2 byte) a 16 bit senza segno quell'intervallo compreso tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="e0c8a-104">Ciascuna *punto di codice*, o il codice carattere rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="e0c8a-105">Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) i caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c8a-106">Note</span><span class="sxs-lookup"><span data-stu-id="e0c8a-106">Remarks</span></span>  
 <span data-ttu-id="e0c8a-107">Usare la `String` tipo di dati per contenere più caratteri senza l'overhead di gestione di matrice dei `Char()`, una matrice di `Char` elementi.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="e0c8a-108">Il valore predefinito `String` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="e0c8a-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="e0c8a-109">Si noti che ciò non corrisponde alla stringa vuota (valore `""`).</span><span class="sxs-lookup"><span data-stu-id="e0c8a-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="e0c8a-110">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="e0c8a-110">Unicode Characters</span></span>  
 <span data-ttu-id="e0c8a-111">I punti di 128 codice (0-127) prima di Unicode corrispondono alle lettere e simboli di una tastiera US standard.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="e0c8a-112">Questi primi punti di 128 codice sono identici a quelli definisce il set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="e0c8a-113">I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, ad esempio lettere dell'alfabeto basati sull'alfabeto latino, accenti, i simboli di valuta e le frazioni.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="e0c8a-114">Unicode utilizza i punti di codice rimanenti (256 e 65535) per un'ampia gamma di simboli.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="e0c8a-115">Questo include il carattere di testo in tutto il mondo, i segni diacritici e simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="e0c8a-116">È possibile usare i metodi, ad esempio <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un singolo carattere in un `String` variabile per determinarne la classificazione di Unicode.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="e0c8a-117">Requisiti di formato</span><span class="sxs-lookup"><span data-stu-id="e0c8a-117">Format Requirements</span></span>  
 <span data-ttu-id="e0c8a-118">È necessario racchiudere una `String` letterale racchiusa tra virgolette (`" "`).</span><span class="sxs-lookup"><span data-stu-id="e0c8a-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="e0c8a-119">Se è necessario includere una virgoletta come uno dei caratteri nella stringa, è utilizzare due virgolette contigue (`""`).</span><span class="sxs-lookup"><span data-stu-id="e0c8a-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="e0c8a-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="e0c8a-121">Si noti che le virgolette contigue che rappresentano un segno di virgolette nella stringa di sono indipendenti dalle virgolette che avviano e terminano le `String` letterale.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="e0c8a-122">Manipolazioni di stringa</span><span class="sxs-lookup"><span data-stu-id="e0c8a-122">String Manipulations</span></span>  
 <span data-ttu-id="e0c8a-123">Una volta che si assegna una stringa in un `String` variabile, tale stringa viene *immutabile*, che significa che è possibile modificare la lunghezza o il contenuto.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="e0c8a-124">Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e Ignora quella precedente.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="e0c8a-125">Il `String` variabile fa quindi riferimento alla nuova stringa.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="e0c8a-126">È possibile modificare il contenuto di un `String` variabile tramite un'ampia gamma di funzioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="e0c8a-127">Nell'esempio seguente viene illustrato il <xref:Microsoft.VisualBasic.Strings.Left%2A> (funzione)</span><span class="sxs-lookup"><span data-stu-id="e0c8a-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="e0c8a-128">Una stringa creata da un altro componente può essere completata con spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="e0c8a-129">Se si riceve una stringa di questo tipo, è possibile usare la <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> funzioni rimuovere gli spazi.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="e0c8a-130">Per altre informazioni sulle stringhe, vedere [stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="e0c8a-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="e0c8a-131">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="e0c8a-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="e0c8a-132">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="e0c8a-132">**Negative Numbers.**</span></span> <span data-ttu-id="e0c8a-133">Tenere presente che i caratteri inclusi in `String` non firmati e non può rappresentare i valori negativi.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="e0c8a-134">In ogni caso, è consigliabile non usare `String` per contenere valori numerici.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="e0c8a-135">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="e0c8a-135">**Interop Considerations.**</span></span> <span data-ttu-id="e0c8a-136">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che caratteri della stringa hanno una larghezza di dati diversi (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="e0c8a-137">Se si passa un argomento di stringa di caratteri a 8 bit a un componente, dichiararlo come `Byte()`, una matrice di `Byte` gli elementi, invece di `String` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="e0c8a-138">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="e0c8a-138">**Type Characters.**</span></span> <span data-ttu-id="e0c8a-139">Aggiungendo il carattere di tipo identificatore `$` a qualsiasi identificatore, se ne determina la `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="e0c8a-140">`String` non include alcun carattere di tipo di valore letterale.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-140">`String` has no literal type character.</span></span> <span data-ttu-id="e0c8a-141">Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette (`" "`) come `String`.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="e0c8a-142">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="e0c8a-142">**Framework Type.**</span></span> <span data-ttu-id="e0c8a-143">Il tipo corrispondente in .NET Framework è la <xref:System.String?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="e0c8a-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c8a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c8a-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="e0c8a-145">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e0c8a-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e0c8a-146">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="e0c8a-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="e0c8a-147">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="e0c8a-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e0c8a-148">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="e0c8a-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e0c8a-149">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="e0c8a-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="e0c8a-150">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e0c8a-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
