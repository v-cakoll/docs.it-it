---
title: Caratteri speciali nel codice (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
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
ms.openlocfilehash: cd7fbce5c382c3acd88a12277a3d7899b823d049
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="81a01-102">Caratteri speciali nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81a01-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="81a01-103">Talvolta è necessario utilizzare caratteri speciali nel codice, vale a dire caratteri non alfabetici o numerici.</span><span class="sxs-lookup"><span data-stu-id="81a01-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="81a01-104">La punteggiatura e caratteri speciali di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] set di caratteri sono diversi utilizzi, dall'organizzazione del testo di programma alla definizione di attività eseguite dal compilatore o dal programma compilato.</span><span class="sxs-lookup"><span data-stu-id="81a01-104">The punctuation and special characters in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="81a01-105">Questi caratteri non specificano l'esecuzione di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="81a01-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="81a01-106">Tra parentesi</span><span class="sxs-lookup"><span data-stu-id="81a01-106">Parentheses</span></span>  
 <span data-ttu-id="81a01-107">Utilizzare le parentesi quando si definisce una routine, ad esempio un `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="81a01-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="81a01-108">Tutti gli elenchi di argomenti di routine è necessario racchiudere tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="81a01-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="81a01-109">È inoltre utilizzare parentesi per raggruppare variabili o argomenti in gruppi logici, in particolare per ignorare l'ordine di precedenza tra operatori in un'espressione complessa predefinito.</span><span class="sxs-lookup"><span data-stu-id="81a01-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="81a01-110">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="81a01-110">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="81a01-111">[!code-vb[VbVbcnConventions&#11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="81a01-111">[!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="81a01-112">Dopo l'esecuzione del codice precedente, il valore di `d` è 8,225 e il valore di `e` è 3.</span><span class="sxs-lookup"><span data-stu-id="81a01-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="81a01-113">Il calcolo per `d` utilizza la precedenza predefinita di `/` su `+` ed equivale a `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="81a01-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="81a01-114">Le parentesi nel calcolo del `e` ignorare l'ordine predefinito.</span><span class="sxs-lookup"><span data-stu-id="81a01-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="81a01-115">Separatori</span><span class="sxs-lookup"><span data-stu-id="81a01-115">Separators</span></span>  
 <span data-ttu-id="81a01-116">Separatori si cosa suggerisce il nome stesso: consentono di separare le sezioni di codice.</span><span class="sxs-lookup"><span data-stu-id="81a01-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="81a01-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], il carattere separatore sia i due punti (`:`).</span><span class="sxs-lookup"><span data-stu-id="81a01-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="81a01-118">Utilizzare i separatori quando si desidera includere più istruzioni in una singola riga anziché righe separate.</span><span class="sxs-lookup"><span data-stu-id="81a01-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="81a01-119">Questo consente di risparmiare spazio e migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="81a01-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="81a01-120">Nell'esempio seguente mostra tre istruzioni separate da virgola.</span><span class="sxs-lookup"><span data-stu-id="81a01-120">The following example shows three statements separated by colons.</span></span>  
  
 <span data-ttu-id="81a01-121">[!code-vb[VbVbcnConventions&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="81a01-121">[!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span></span>  
  
 <span data-ttu-id="81a01-122">Per ulteriori informazioni, vedere [How to: Break e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="81a01-122">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="81a01-123">I due punti (`:`) carattere viene utilizzato anche per identificare un'etichetta dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="81a01-123">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="81a01-124">Per ulteriori informazioni, vedere [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="81a01-124">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="81a01-125">Concatenazione</span><span class="sxs-lookup"><span data-stu-id="81a01-125">Concatenation</span></span>  
 <span data-ttu-id="81a01-126">Utilizzare il `&` operatore per *concatenazione*, o il collegamento di più stringhe.</span><span class="sxs-lookup"><span data-stu-id="81a01-126">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="81a01-127">Non confondere con il `+` operatore, che vengono sommati i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="81a01-127">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="81a01-128">Se si utilizza il `+` per concatenare quando si opera su valori numerici, è possibile ottenere risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="81a01-128">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="81a01-129">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="81a01-129">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="81a01-130">[!code-vb[13 VbVbcnConventions](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="81a01-130">[!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span></span>  
  
 <span data-ttu-id="81a01-131">Dopo l'esecuzione del codice precedente, il valore di `resultA` è 21,01 e il valore di `resultB` è "10,0111".</span><span class="sxs-lookup"><span data-stu-id="81a01-131">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="81a01-132">Operatori di accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="81a01-132">Member Access Operators</span></span>  
 <span data-ttu-id="81a01-133">Per accedere a un membro di un tipo, utilizzare il punto (`.`) o punto esclamativo (`!`) (operatore) tra il nome del tipo e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="81a01-133">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="81a01-134">Punto (.) Operatore</span><span class="sxs-lookup"><span data-stu-id="81a01-134">Dot (.) Operator</span></span>  
 <span data-ttu-id="81a01-135">Utilizzare il `.` operatore su una classe, struttura, interfaccia o enumerazione come un operatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="81a01-135">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="81a01-136">Il membro può essere un campo, proprietà, evento o metodo.</span><span class="sxs-lookup"><span data-stu-id="81a01-136">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="81a01-137">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="81a01-137">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="81a01-138">[!code-vb[VbVbcnConventions&#14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="81a01-138">[!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span></span>  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="81a01-139">Punto esclamativo (!) Operatore</span><span class="sxs-lookup"><span data-stu-id="81a01-139">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="81a01-140">Utilizzare il `!` operatore solo in una classe o interfaccia come operatore di accesso al dizionario.</span><span class="sxs-lookup"><span data-stu-id="81a01-140">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="81a01-141">La classe o interfaccia deve avere una proprietà predefinita che accetta un singolo `String` argomento.</span><span class="sxs-lookup"><span data-stu-id="81a01-141">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="81a01-142">Identificatore che segue immediatamente il `!` diventa il valore dell'argomento passato alla proprietà predefinito come stringa.</span><span class="sxs-lookup"><span data-stu-id="81a01-142">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="81a01-143">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="81a01-143">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="81a01-144">[!code-vb[VbVbcnConventions&#15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="81a01-144">[!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span></span>  
  
 <span data-ttu-id="81a01-145">Le tre righe di output `MsgBox` tutte visualizzate con il valore `32856`.</span><span class="sxs-lookup"><span data-stu-id="81a01-145">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="81a01-146">La prima riga utilizza l'accesso tradizionale alla proprietà `index`, il secondo si avvale del fatto che `index` la proprietà predefinita della classe `hasDefault`, e la terza utilizza l'accesso al dizionario alla classe.</span><span class="sxs-lookup"><span data-stu-id="81a01-146">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="81a01-147">Si noti che il secondo operando il `!` operatore deve essere un identificatore valido di Visual Basic non è racchiuso tra virgolette doppie (`" "`).</span><span class="sxs-lookup"><span data-stu-id="81a01-147">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="81a01-148">In altre parole, è possibile utilizzare un valore letterale stringa o una variabile di stringa.</span><span class="sxs-lookup"><span data-stu-id="81a01-148">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="81a01-149">La modifica seguente all'ultima riga del `MsgBox` chiamata genera un errore perché `"X"` è una stringa letterale racchiusa.</span><span class="sxs-lookup"><span data-stu-id="81a01-149">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="81a01-150">I riferimenti alle raccolte predefinite devono essere espliciti.</span><span class="sxs-lookup"><span data-stu-id="81a01-150">References to default collections must be explicit.</span></span> <span data-ttu-id="81a01-151">In particolare, non è possibile utilizzare il `!` operatore su una variabile ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="81a01-151">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="81a01-152">Il `!` carattere viene utilizzato anche come il `Single` tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="81a01-152">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a01-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81a01-153">See Also</span></span>  
 <span data-ttu-id="81a01-154">[Struttura del programma e convenzioni del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="81a01-154">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="81a01-155"> [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="81a01-155"> [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
