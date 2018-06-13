---
title: Caratteri speciali nel codice (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 932b38d97b36292e66bfad91a9a3799459d3b73c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654356"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="d8fc6-102">Caratteri speciali nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8fc6-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="d8fc6-103">In alcuni casi è necessario usare caratteri speciali nel codice, ovvero i caratteri non alfabetici o numerici.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="d8fc6-104">La punteggiatura e caratteri speciali nel set di caratteri Visual Basic presenti diversi utilizzi, dall'organizzazione del testo di programma alla definizione di attività che esegue il compilatore o dal programma compilato.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="d8fc6-105">Questi caratteri non specificano l'esecuzione di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="d8fc6-106">Tra parentesi</span><span class="sxs-lookup"><span data-stu-id="d8fc6-106">Parentheses</span></span>  
 <span data-ttu-id="d8fc6-107">Utilizzare le parentesi quando si definisce una routine, ad esempio un `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="d8fc6-108">Tutti gli elenchi di argomenti di stored procedure è necessario racchiudere tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="d8fc6-109">È inoltre utilizzare parentesi per raggruppare variabili o argomenti in gruppi logici, soprattutto per ignorare l'ordine predefinito di precedenza degli operatori in un'espressione complessa.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="d8fc6-110">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 <span data-ttu-id="d8fc6-111">Dopo l'esecuzione del codice precedente, il valore di `d` è 8,225 e il valore di `e` è 3.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="d8fc6-112">Il calcolo di `d` utilizza la precedenza predefinita di `/` su `+` ed equivale a `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="d8fc6-113">Le parentesi nel calcolo del `e` ignorare l'ordine predefinito.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="d8fc6-114">Separatori</span><span class="sxs-lookup"><span data-stu-id="d8fc6-114">Separators</span></span>  
 <span data-ttu-id="d8fc6-115">Separatori si cosa suggerisce il nome stesso: consentono di separare le sezioni di codice.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="d8fc6-116">In Visual Basic, il carattere di separazione è i due punti (`:`).</span><span class="sxs-lookup"><span data-stu-id="d8fc6-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="d8fc6-117">Utilizzare i separatori quando si desidera includere più istruzioni in una singola riga anziché righe separate.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="d8fc6-118">Questo consente di risparmiare spazio e migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="d8fc6-119">Nell'esempio seguente mostra tre istruzioni separate da virgola.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 <span data-ttu-id="d8fc6-120">Per ulteriori informazioni, vedere [come: Break e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="d8fc6-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="d8fc6-121">I due punti (`:`) carattere viene utilizzato anche per identificare un'etichetta di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="d8fc6-122">Per ulteriori informazioni, vedere [come: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="d8fc6-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="d8fc6-123">Concatenazione</span><span class="sxs-lookup"><span data-stu-id="d8fc6-123">Concatenation</span></span>  
 <span data-ttu-id="d8fc6-124">Utilizzare il `&` operatore per *concatenazione*, o il collegamento di più stringhe.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="d8fc6-125">Non confondere con il `+` operatore, che vengono sommati i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="d8fc6-126">Se si utilizza il `+` per concatenare quando si opera su valori numerici, è possibile ottenere risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="d8fc6-127">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 <span data-ttu-id="d8fc6-128">Dopo l'esecuzione del codice precedente, il valore di `resultA` è 21,01 e il valore di `resultB` è "10,0111".</span><span class="sxs-lookup"><span data-stu-id="d8fc6-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="d8fc6-129">Operatori di accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="d8fc6-129">Member Access Operators</span></span>  
 <span data-ttu-id="d8fc6-130">Per accedere a un membro di un tipo, utilizzare il punto (`.`) o punto esclamativo (`!`) (operatore) tra il nome del tipo e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="d8fc6-131">Punto (.) Operatore</span><span class="sxs-lookup"><span data-stu-id="d8fc6-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="d8fc6-132">Utilizzare il `.` operatore su una classe, struttura, interfaccia o enumerazione come un operatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="d8fc6-133">Il membro può essere un campo, proprietà, eventi o metodo.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="d8fc6-134">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="d8fc6-135">Punto esclamativo (!) Operatore</span><span class="sxs-lookup"><span data-stu-id="d8fc6-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="d8fc6-136">Utilizzare il `!` operatore solo in una classe o interfaccia come operatore di accesso al dizionario.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="d8fc6-137">La classe o interfaccia deve avere una proprietà predefinita che accetta un unico `String` argomento.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="d8fc6-138">Identificatore che segue immediatamente il `!` diventa il valore dell'argomento passato alla proprietà predefinita sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="d8fc6-139">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 <span data-ttu-id="d8fc6-140">Le tre righe di output `MsgBox` tutti di visualizzare il valore `32856`.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="d8fc6-141">La prima riga utilizza l'accesso alla proprietà tradizionale `index`, il secondo si avvalgono del fatto che `index` la proprietà predefinita della classe `hasDefault`, e la terza utilizza la classe di accesso del dizionario.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="d8fc6-142">Si noti che il secondo operando del `!` operatore deve essere un valido identificatore Visual Basic non è racchiuso tra virgolette doppie (`" "`).</span><span class="sxs-lookup"><span data-stu-id="d8fc6-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="d8fc6-143">In altre parole, è possibile utilizzare un valore letterale stringa o una variabile di stringa.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="d8fc6-144">La modifica seguente all'ultima riga del `MsgBox` chiamata genera un errore perché `"X"` è una stringa letterale racchiusa.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="d8fc6-145">I riferimenti alle raccolte predefinite devono essere espliciti.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-145">References to default collections must be explicit.</span></span> <span data-ttu-id="d8fc6-146">In particolare, non è possibile utilizzare il `!` operatore su una variabile di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="d8fc6-147">Il `!` carattere viene utilizzato anche come il `Single` carattere tipo.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fc6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8fc6-148">See Also</span></span>  
 [<span data-ttu-id="d8fc6-149">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="d8fc6-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="d8fc6-150">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="d8fc6-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
