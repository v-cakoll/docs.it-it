---
title: Tipo di dati String
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
ms.openlocfilehash: cd4b64c101ae56928e84a04649e49c17b6f4023c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415505"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="9210f-102">Tipo di dati String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9210f-102">String Data Type (Visual Basic)</span></span>

<span data-ttu-id="9210f-103">Include sequenze di punti di codice senza segno a 16 bit (2 byte) che variano da 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="9210f-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="9210f-104">Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="9210f-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="9210f-105">Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="9210f-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9210f-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="9210f-106">Remarks</span></span>  

 <span data-ttu-id="9210f-107">Usare il `String` tipo di dati per mantenere più caratteri senza l'overhead di gestione della matrice di `Char()` , una matrice di `Char` elementi.</span><span class="sxs-lookup"><span data-stu-id="9210f-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="9210f-108">Il valore predefinito di `String` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="9210f-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="9210f-109">Si noti che questa operazione non corrisponde alla stringa vuota (valore `""` ).</span><span class="sxs-lookup"><span data-stu-id="9210f-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="9210f-110">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="9210f-110">Unicode Characters</span></span>  

 <span data-ttu-id="9210f-111">I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9210f-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="9210f-112">Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="9210f-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="9210f-113">I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni.</span><span class="sxs-lookup"><span data-stu-id="9210f-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="9210f-114">Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli.</span><span class="sxs-lookup"><span data-stu-id="9210f-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="9210f-115">Sono inclusi i caratteri testuali, i segni diacritici e i simboli matematici e tecnici in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="9210f-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="9210f-116">È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un singolo carattere in una `String` variabile per determinare la relativa classificazione Unicode.</span><span class="sxs-lookup"><span data-stu-id="9210f-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="9210f-117">Requisiti di formato</span><span class="sxs-lookup"><span data-stu-id="9210f-117">Format Requirements</span></span>  

 <span data-ttu-id="9210f-118">È necessario racchiudere un `String` valore letterale racchiuso tra virgolette ( `" "` ).</span><span class="sxs-lookup"><span data-stu-id="9210f-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="9210f-119">Se è necessario includere una virgoletta come uno dei caratteri nella stringa, è possibile utilizzare due virgolette contigue ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="9210f-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="9210f-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9210f-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="9210f-121">Si noti che le virgolette contigue che rappresentano le virgolette nella stringa sono indipendenti dalle virgolette che iniziano e terminano il `String` valore letterale.</span><span class="sxs-lookup"><span data-stu-id="9210f-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="9210f-122">Modifiche delle stringhe</span><span class="sxs-lookup"><span data-stu-id="9210f-122">String Manipulations</span></span>  

 <span data-ttu-id="9210f-123">Una volta assegnata una stringa a una `String` variabile, tale stringa non è *modificabile*, quindi non è possibile modificarne la lunghezza o il contenuto.</span><span class="sxs-lookup"><span data-stu-id="9210f-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="9210f-124">Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e abbandona quella precedente.</span><span class="sxs-lookup"><span data-stu-id="9210f-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="9210f-125">La `String` variabile fa quindi riferimento alla nuova stringa.</span><span class="sxs-lookup"><span data-stu-id="9210f-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="9210f-126">È possibile modificare il contenuto di una `String` variabile usando un'ampia gamma di funzioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="9210f-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="9210f-127">Nell'esempio seguente viene illustrata la <xref:Microsoft.VisualBasic.Strings.Left%2A> funzione</span><span class="sxs-lookup"><span data-stu-id="9210f-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="9210f-128">Una stringa creata da un altro componente potrebbe essere riempita con spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="9210f-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="9210f-129">Se si riceve una stringa di questo tipo, è possibile usare le <xref:Microsoft.VisualBasic.Strings.Trim%2A> <xref:Microsoft.VisualBasic.Strings.LTrim%2A> funzioni, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> per rimuovere questi spazi.</span><span class="sxs-lookup"><span data-stu-id="9210f-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="9210f-130">Per ulteriori informazioni sulle modifiche delle stringhe, vedere [stringhe](../../programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="9210f-130">For more information about string manipulations, see [Strings](../../programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="9210f-131">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="9210f-131">Programming Tips</span></span>  
  
- <span data-ttu-id="9210f-132">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="9210f-132">**Negative Numbers.**</span></span> <span data-ttu-id="9210f-133">Tenere presente che i caratteri conservati da `String` non sono firmati e non possono rappresentare valori negativi.</span><span class="sxs-lookup"><span data-stu-id="9210f-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="9210f-134">In ogni caso, è consigliabile non usare `String` per mantenere i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="9210f-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="9210f-135">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="9210f-135">**Interop Considerations.**</span></span> <span data-ttu-id="9210f-136">Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i caratteri stringa hanno una larghezza dati diversa (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="9210f-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="9210f-137">Se si passa un argomento stringa di caratteri a 8 bit a tale componente, dichiararlo come `Byte()` una matrice di `Byte` elementi, anziché `String` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9210f-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="9210f-138">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="9210f-138">**Type Characters.**</span></span> <span data-ttu-id="9210f-139">L'aggiunta del carattere di tipo identificatore `$` a qualsiasi identificatore forza il `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="9210f-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="9210f-140">`String`non ha un carattere di tipo letterale.</span><span class="sxs-lookup"><span data-stu-id="9210f-140">`String` has no literal type character.</span></span> <span data-ttu-id="9210f-141">Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette ( `" "` ) come `String` .</span><span class="sxs-lookup"><span data-stu-id="9210f-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="9210f-142">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="9210f-142">**Framework Type.**</span></span> <span data-ttu-id="9210f-143">Il tipo corrispondente nella .NET Framework è la <xref:System.String?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="9210f-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9210f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9210f-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="9210f-145">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9210f-145">Data Types</span></span>](index.md)
- [<span data-ttu-id="9210f-146">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="9210f-146">Char Data Type</span></span>](char-data-type.md)
- [<span data-ttu-id="9210f-147">CString</span><span class="sxs-lookup"><span data-stu-id="9210f-147">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="9210f-148">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="9210f-148">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="9210f-149">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="9210f-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="9210f-150">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9210f-150">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
