---
title: Nozioni fondamentali sulle stringhe in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a40435b76b0eee4f4eca15d5ba1a31cc58698ab
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="fedff-102">Nozioni fondamentali sulle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fedff-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="fedff-103">Il tipo di dati `String` rappresenta una serie di caratteri, ognuno dei quali, a sua volta, rappresenta un'istanza del tipo di dati `Char`.</span><span class="sxs-lookup"><span data-stu-id="fedff-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="fedff-104">In questo argomento introduce i concetti di base di stringhe in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fedff-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="fedff-105">Variabili di tipo String</span><span class="sxs-lookup"><span data-stu-id="fedff-105">String Variables</span></span>  
 <span data-ttu-id="fedff-106">È possibile assegnare a un'istanza di una stringa un valore letterale che rappresenta una serie di caratteri.</span><span class="sxs-lookup"><span data-stu-id="fedff-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="fedff-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fedff-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]  
  
 <span data-ttu-id="fedff-108">Una variabile `String` può accettare anche qualsiasi espressione che restituisca una stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="fedff-109">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="fedff-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]  
  
 <span data-ttu-id="fedff-110">Qualsiasi valore letterale assegnato a una variabile `String` deve essere racchiuso tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="fedff-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="fedff-111">Questo implica che all'interno di una stringa le virgolette non possono essere rappresentate dal segno di virgolette.</span><span class="sxs-lookup"><span data-stu-id="fedff-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="fedff-112">Il codice seguente, ad esempio, causa un errore di compilazione:</span><span class="sxs-lookup"><span data-stu-id="fedff-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]  
  
 <span data-ttu-id="fedff-113">L'errore è determinato dal fatto che durante la compilazione la stringa viene considerata terminata dopo il secondo segno di virgolette e il resto della stringa è interpretato come codice.</span><span class="sxs-lookup"><span data-stu-id="fedff-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="fedff-114">Per risolvere questo problema, Visual Basic vengono interpretati da due virgolette in una stringa letterale come un segno di virgolette nella stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="fedff-115">L'esempio seguente illustra il modo corretto per inserire le virgolette in una stringa: </span><span class="sxs-lookup"><span data-stu-id="fedff-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]  
  
 <span data-ttu-id="fedff-116">Nell'esempio precedente, la coppia di virgolette che precede la parola `Look` diventa un segno di virgolette nella stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="fedff-117">Le tre serie di virgolette alla fine della riga rappresentano le virgolette appartenenti alla stringa seguite dal carattere di terminazione della stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="fedff-118">I valori letterali stringa possono contenere più righe:</span><span class="sxs-lookup"><span data-stu-id="fedff-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="fedff-119">La stringa risultante contiene le sequenze di nuove righe usate nel valore letterale stringa (vbcr, vbcrlf e così via).</span><span class="sxs-lookup"><span data-stu-id="fedff-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="fedff-120">Non è più necessario usare la soluzione alternativa precedente:</span><span class="sxs-lookup"><span data-stu-id="fedff-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="fedff-121">Caratteri nelle stringhe</span><span class="sxs-lookup"><span data-stu-id="fedff-121">Characters in Strings</span></span>  
 <span data-ttu-id="fedff-122">Una stringa può essere considerata una serie di valori `Char`. Il tipo `String` è dotato di funzioni predefinite che consentono di eseguire numerose manipolazioni della stringa, simili a quelle consentite dalle matrici.</span><span class="sxs-lookup"><span data-stu-id="fedff-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="fedff-123">Come tutte le matrici in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], queste sono matrici in base zero.</span><span class="sxs-lookup"><span data-stu-id="fedff-123">Like all array in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="fedff-124">Per fare riferimento a un carattere specifico di una stringa è possibile usare la proprietà `Chars`, che consente di accedere a un carattere in base alla sua posizione all'interno della stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="fedff-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fedff-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]  
  
 <span data-ttu-id="fedff-126">Nell'esempio precedente, la proprietà `Chars` della stringa restituisce il quarto carattere della stringa, ovvero `D`, e lo assegna a `myChar`.</span><span class="sxs-lookup"><span data-stu-id="fedff-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="fedff-127">È anche possibile ottenere la lunghezza di una particolare stringa mediante la proprietà `Length`.</span><span class="sxs-lookup"><span data-stu-id="fedff-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="fedff-128">Se è necessario eseguire su una stringa più manipolazioni analoghe a quelle consentite nelle matrici, è possibile convertire la stringa in una matrice di istanze di `Char` usando la funzione `ToCharArray` della stringa.</span><span class="sxs-lookup"><span data-stu-id="fedff-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="fedff-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fedff-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]  
  
 <span data-ttu-id="fedff-130">La variabile `myArray` ora contiene una matrice di istanze di `Char`, ognuna delle quali rappresenta un carattere di `myString`.</span><span class="sxs-lookup"><span data-stu-id="fedff-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="fedff-131">Immutabilità delle stringhe</span><span class="sxs-lookup"><span data-stu-id="fedff-131">The Immutability of Strings</span></span>  
 <span data-ttu-id="fedff-132">È una stringa *non modificabile*, vale a dire che il relativo valore non può essere modificato una volta che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="fedff-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="fedff-133">Questo non impedisce tuttavia di assegnare più valori a una variabile di tipo String.</span><span class="sxs-lookup"><span data-stu-id="fedff-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="fedff-134">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fedff-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]  
  
 <span data-ttu-id="fedff-135">In questo esempio, dopo aver creato una variabile stringa, le viene assegnato un valore che successivamente viene modificato. </span><span class="sxs-lookup"><span data-stu-id="fedff-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="fedff-136">Più precisamente, nella prima riga viene creata un'istanza di tipo `String` cui viene assegnato il valore `This string is immutable`.</span><span class="sxs-lookup"><span data-stu-id="fedff-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="fedff-137">Nella seconda riga dell'esempio viene creata una nuova istanza a cui viene assegnato il valore `Or is it?`. Il riferimento alla prima istanza viene quindi ignorato e con la variabile stringa viene archiviato il riferimento alla nuova istanza. </span><span class="sxs-lookup"><span data-stu-id="fedff-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="fedff-138">A differenza di altri tipi di dati intrinseci, `String` è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="fedff-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="fedff-139">Quando una variabile di tipo riferimento viene passata come argomento di una funzione o di una subroutine, invece del valore effettivo della stringa viene passato un riferimento all'indirizzo di memoria in cui sono archiviati i dati</span><span class="sxs-lookup"><span data-stu-id="fedff-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="fedff-140">Nell'esempio precedente, quindi, il nome della variabile rimane lo stesso, ma punta a un'istanza nuova e diversa della classe `String`, che contiene il nuovo valore. </span><span class="sxs-lookup"><span data-stu-id="fedff-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fedff-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fedff-141">See Also</span></span>  
 [<span data-ttu-id="fedff-142">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fedff-142">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [<span data-ttu-id="fedff-143">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="fedff-143">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="fedff-144">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="fedff-144">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="fedff-145">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="fedff-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
