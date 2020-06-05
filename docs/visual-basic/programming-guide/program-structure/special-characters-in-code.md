---
title: Caratteri speciali nel codice
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
ms.openlocfilehash: c9b170ed812474cdeee100f1dc388d5c7e85f2cc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400591"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="e92a0-102">Caratteri speciali nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e92a0-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="e92a0-103">In alcuni casi è necessario usare caratteri speciali nel codice, ovvero caratteri non alfabetici o numerici.</span><span class="sxs-lookup"><span data-stu-id="e92a0-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="e92a0-104">La punteggiatura e i caratteri speciali del set di caratteri Visual Basic hanno diversi usi, dall'organizzazione del testo del programma alla definizione delle attività eseguite dal compilatore o dal programma compilato.</span><span class="sxs-lookup"><span data-stu-id="e92a0-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="e92a0-105">Questi caratteri non specificano l'esecuzione di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="e92a0-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="e92a0-106">Parentesi</span><span class="sxs-lookup"><span data-stu-id="e92a0-106">Parentheses</span></span>  
 <span data-ttu-id="e92a0-107">Usare le parentesi quando si definisce una routine, ad esempio `Sub` o `Function` .</span><span class="sxs-lookup"><span data-stu-id="e92a0-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="e92a0-108">È necessario racchiudere tra parentesi tutti gli elenchi di argomenti di routine.</span><span class="sxs-lookup"><span data-stu-id="e92a0-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="e92a0-109">È inoltre possibile utilizzare le parentesi per inserire variabili o argomenti in gruppi logici, in particolare per eseguire l'override dell'ordine predefinito di precedenza degli operatori in un'espressione complessa.</span><span class="sxs-lookup"><span data-stu-id="e92a0-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="e92a0-110">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e92a0-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="e92a0-111">Dopo l'esecuzione del codice precedente, il valore di `d` è 8,225 e il valore di `e` è 3.</span><span class="sxs-lookup"><span data-stu-id="e92a0-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="e92a0-112">Il calcolo per `d` utilizza la precedenza predefinita di `/` over `+` ed è equivalente a `d = b + (c / a)` .</span><span class="sxs-lookup"><span data-stu-id="e92a0-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="e92a0-113">Le parentesi nel calcolo per eseguono l' `e` override della precedenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="e92a0-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="e92a0-114">Separatori</span><span class="sxs-lookup"><span data-stu-id="e92a0-114">Separators</span></span>  
 <span data-ttu-id="e92a0-115">I separatori eseguono le operazioni che il nome suggerisce: separano sezioni di codice.</span><span class="sxs-lookup"><span data-stu-id="e92a0-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="e92a0-116">In Visual Basic il carattere separatore è costituito dai due punti ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="e92a0-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="e92a0-117">Usare i separatori quando si desidera includere più istruzioni su una sola riga anziché su righe separate.</span><span class="sxs-lookup"><span data-stu-id="e92a0-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="e92a0-118">Questo consente di risparmiare spazio e di migliorare la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="e92a0-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="e92a0-119">Nell'esempio seguente vengono illustrate tre istruzioni separate da due punti.</span><span class="sxs-lookup"><span data-stu-id="e92a0-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="e92a0-120">Per altre informazioni, vedere [procedura: interrompere e combinare istruzioni nel codice](how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="e92a0-120">For more information, see [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="e92a0-121">Il carattere due punti ( `:` ) viene utilizzato anche per identificare un'etichetta di istruzione.</span><span class="sxs-lookup"><span data-stu-id="e92a0-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="e92a0-122">Per altre informazioni, vedere [How to: Label statements](how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="e92a0-122">For more information, see [How to: Label Statements](how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="e92a0-123">Concatenazione</span><span class="sxs-lookup"><span data-stu-id="e92a0-123">Concatenation</span></span>  
 <span data-ttu-id="e92a0-124">Utilizzare l' `&` operatore per la *concatenazione*o collegare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="e92a0-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="e92a0-125">Non confonderla con l' `+` operatore, che somma i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="e92a0-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="e92a0-126">Se si utilizza l' `+` operatore per concatenare quando si opera su valori numerici, è possibile ottenere risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="e92a0-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="e92a0-127">L'esempio seguente illustra questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e92a0-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="e92a0-128">Dopo l'esecuzione del codice precedente, il valore di `resultA` è 21,01 e il valore di `resultB` è "10,0111".</span><span class="sxs-lookup"><span data-stu-id="e92a0-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="e92a0-129">Operatori di accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="e92a0-129">Member Access Operators</span></span>  
 <span data-ttu-id="e92a0-130">Per accedere a un membro di un tipo, usare l'operatore punto ( `.` ) o punto esclamativo ( `!` ) tra il nome del tipo e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="e92a0-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="e92a0-131">Punto (.) Operatore</span><span class="sxs-lookup"><span data-stu-id="e92a0-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="e92a0-132">Usare l' `.` operatore in una classe, una struttura, un'interfaccia o un'enumerazione come operatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="e92a0-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="e92a0-133">Il membro può essere un campo, una proprietà, un evento o un metodo.</span><span class="sxs-lookup"><span data-stu-id="e92a0-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="e92a0-134">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e92a0-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="e92a0-135">Punto esclamativo (!) Operatore</span><span class="sxs-lookup"><span data-stu-id="e92a0-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="e92a0-136">Usare l' `!` operatore solo in una classe o in un'interfaccia come operatore di accesso del dizionario.</span><span class="sxs-lookup"><span data-stu-id="e92a0-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="e92a0-137">La classe o l'interfaccia deve avere una proprietà predefinita che accetta un singolo `String` argomento.</span><span class="sxs-lookup"><span data-stu-id="e92a0-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="e92a0-138">L'identificatore immediatamente successivo all' `!` operatore diventa il valore dell'argomento passato alla proprietà predefinita sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="e92a0-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="e92a0-139">L'esempio seguente illustra questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e92a0-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="e92a0-140">Le tre righe di output di `MsgBox` tutti visualizzano il valore `32856` .</span><span class="sxs-lookup"><span data-stu-id="e92a0-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="e92a0-141">La prima riga usa l'accesso tradizionale alla proprietà `index` , il secondo usa il fatto che `index` è la proprietà predefinita della classe `hasDefault` e la terza usa l'accesso tramite dizionario alla classe.</span><span class="sxs-lookup"><span data-stu-id="e92a0-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="e92a0-142">Si noti che il secondo operando dell' `!` operatore deve essere un identificatore di Visual Basic valido non racchiuso tra virgolette doppie ( `" "` ).</span><span class="sxs-lookup"><span data-stu-id="e92a0-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="e92a0-143">In altre parole, non è possibile usare un valore letterale stringa o una variabile di stringa.</span><span class="sxs-lookup"><span data-stu-id="e92a0-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="e92a0-144">La seguente modifica all'ultima riga della `MsgBox` chiamata genera un errore perché `"X"` è un valore letterale stringa racchiuso.</span><span class="sxs-lookup"><span data-stu-id="e92a0-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="e92a0-145">I riferimenti alle raccolte predefinite devono essere espliciti.</span><span class="sxs-lookup"><span data-stu-id="e92a0-145">References to default collections must be explicit.</span></span> <span data-ttu-id="e92a0-146">In particolare, non è possibile usare l' `!` operatore su una variabile ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="e92a0-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="e92a0-147">Il `!` carattere viene utilizzato anche come `Single` carattere di tipo.</span><span class="sxs-lookup"><span data-stu-id="e92a0-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92a0-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e92a0-148">See also</span></span>

- [<span data-ttu-id="e92a0-149">Struttura del programma e convenzioni del codice</span><span class="sxs-lookup"><span data-stu-id="e92a0-149">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="e92a0-150">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="e92a0-150">Type Characters</span></span>](../language-features/data-types/type-characters.md)
