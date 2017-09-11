---
title: Tipo di dati (Visual Basic) stringa | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5d7a4272169ae7b2749d038e1116818d2cfbad95
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="59ba9-102">Tipo di dati String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59ba9-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="59ba9-103">Contiene le sequenze di punti di codice di (2 byte) senza segno a 16 bit quell'intervallo compreso tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="59ba9-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="59ba9-104">Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="59ba9-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="59ba9-105">Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) i caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="59ba9-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59ba9-106">Note</span><span class="sxs-lookup"><span data-stu-id="59ba9-106">Remarks</span></span>  
 <span data-ttu-id="59ba9-107">Utilizzare il `String` tipo di dati per contenere più caratteri senza overhead nella gestione di `Char()`, una matrice di `Char` elementi.</span><span class="sxs-lookup"><span data-stu-id="59ba9-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="59ba9-108">Il valore predefinito di `String` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="59ba9-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="59ba9-109">Si noti che questo non corrisponde alla stringa vuota (valore `""`).</span><span class="sxs-lookup"><span data-stu-id="59ba9-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="59ba9-110">Caratteri Unicode</span><span class="sxs-lookup"><span data-stu-id="59ba9-110">Unicode Characters</span></span>  
 <span data-ttu-id="59ba9-111">I primo 128 punti di codice (da 0 a 127) di Unicode corrispondono alle lettere e simboli di tastiera standard.</span><span class="sxs-lookup"><span data-stu-id="59ba9-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="59ba9-112">Questi primi punti di 128 codice sono gli stessi di quelli definisce il set di caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="59ba9-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="59ba9-113">I secondo 128 punti di codice (128-255) rappresentano caratteri speciali, ad esempio lettere dell'alfabeto latino, accenti, simboli di valuta e le frazioni di secondo.</span><span class="sxs-lookup"><span data-stu-id="59ba9-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="59ba9-114">Unicode utilizza i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli.</span><span class="sxs-lookup"><span data-stu-id="59ba9-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="59ba9-115">Sono inclusi caratteri testuali in tutto il mondo, i segni diacritici e simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="59ba9-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="59ba9-116">È possibile utilizzare i metodi, ad esempio <xref:System.Char.IsDigit%2A>e <xref:System.Char.IsPunctuation%2A>su un singolo carattere in un `String` variabile per determinarne la classificazione Unicode.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A></span><span class="sxs-lookup"><span data-stu-id="59ba9-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="59ba9-117">Requisiti di formato</span><span class="sxs-lookup"><span data-stu-id="59ba9-117">Format Requirements</span></span>  
 <span data-ttu-id="59ba9-118">È necessario racchiudere un `String` letterale racchiusa tra virgolette (`" "`).</span><span class="sxs-lookup"><span data-stu-id="59ba9-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="59ba9-119">Se è necessario includere una virgoletta come uno dei caratteri nella stringa, utilizzare due virgolette contigue (`""`).</span><span class="sxs-lookup"><span data-stu-id="59ba9-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="59ba9-120">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="59ba9-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="59ba9-121">Si noti che le virgolette contigue che rappresentano le virgolette nella stringa sono indipendenti dalle virgolette che iniziano e terminano le `String` letterale.</span><span class="sxs-lookup"><span data-stu-id="59ba9-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="59ba9-122">Manipolazioni di stringhe</span><span class="sxs-lookup"><span data-stu-id="59ba9-122">String Manipulations</span></span>  
 <span data-ttu-id="59ba9-123">Dopo aver assegnato una stringa a un `String` è variabile, tale stringa *non modificabile*, ovvero è possibile modificare la lunghezza o il contenuto.</span><span class="sxs-lookup"><span data-stu-id="59ba9-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="59ba9-124">Quando si modifica una stringa in alcun modo, Visual Basic crea una nuova stringa e la precedente viene abbandonata.</span><span class="sxs-lookup"><span data-stu-id="59ba9-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="59ba9-125">Il `String` variabile fa quindi riferimento alla nuova stringa.</span><span class="sxs-lookup"><span data-stu-id="59ba9-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="59ba9-126">È possibile modificare il contenuto di un `String` variabile utilizzando un'ampia gamma di funzioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="59ba9-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="59ba9-127">Nell'esempio seguente viene illustrata la <xref:Microsoft.VisualBasic.Strings.Left%2A>funzione</xref:Microsoft.VisualBasic.Strings.Left%2A></span><span class="sxs-lookup"><span data-stu-id="59ba9-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="59ba9-128">Una stringa creata da un altro componente può essere completata con spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="59ba9-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="59ba9-129">Se si riceve una stringa di questo tipo, è possibile utilizzare il <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A>funzioni per rimuovere gli spazi.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A></span><span class="sxs-lookup"><span data-stu-id="59ba9-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="59ba9-130">Per ulteriori informazioni sulle stringhe, vedere [stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="59ba9-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="59ba9-131">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="59ba9-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="59ba9-132">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="59ba9-132">**Negative Numbers.**</span></span> <span data-ttu-id="59ba9-133">Tenere presente che i caratteri inclusi in `String` non sono firmati e non può rappresentare valori negativi.</span><span class="sxs-lookup"><span data-stu-id="59ba9-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="59ba9-134">In ogni caso, è consigliabile non utilizzare `String` per includere valori numerici.</span><span class="sxs-lookup"><span data-stu-id="59ba9-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="59ba9-135">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="59ba9-135">**Interop Considerations.**</span></span> <span data-ttu-id="59ba9-136">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i caratteri di stringa hanno un'ampiezza dei dati diversa (8 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="59ba9-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="59ba9-137">Se si passa un argomento di stringa di caratteri a 8 bit a tale componente, dichiararla come `Byte()`, una matrice di `Byte` elementi, anziché `String` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="59ba9-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="59ba9-138">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="59ba9-138">**Type Characters.**</span></span> <span data-ttu-id="59ba9-139">Aggiungendo il carattere di tipo identificatore `$` a qualsiasi identificatore e ne impone il `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="59ba9-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="59ba9-140">`String`non include alcun carattere tipo effettivo.</span><span class="sxs-lookup"><span data-stu-id="59ba9-140">`String` has no literal type character.</span></span> <span data-ttu-id="59ba9-141">Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette (`" "`) come `String`.</span><span class="sxs-lookup"><span data-stu-id="59ba9-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="59ba9-142">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="59ba9-142">**Framework Type.**</span></span> <span data-ttu-id="59ba9-143">Il tipo corrispondente in .NET Framework è la <xref:System.String?displayProperty=fullName>classe.</xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="59ba9-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=fullName> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ba9-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59ba9-144">See Also</span></span>  
 <span data-ttu-id="59ba9-145"><xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="59ba9-145"><xref:System.String?displayProperty=fullName></span></span>   
<span data-ttu-id="59ba9-146"> [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="59ba9-146"> [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="59ba9-147"> [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="59ba9-147"> [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="59ba9-148"> [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="59ba9-148"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="59ba9-149"> [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="59ba9-149"> [Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
<span data-ttu-id="59ba9-150"> [Procedura: chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span><span class="sxs-lookup"><span data-stu-id="59ba9-150"> [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span></span>  
<span data-ttu-id="59ba9-151"> [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="59ba9-151"> [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span></span>

