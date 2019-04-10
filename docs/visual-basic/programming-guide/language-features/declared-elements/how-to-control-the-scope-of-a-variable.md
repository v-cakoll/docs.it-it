---
title: "Procedura: Controllare l'ambito di una variabile (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324318"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="17abd-102">Procedura: Controllare l'ambito di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17abd-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="17abd-103">In genere, una variabile si trova nel *ambito*, o visibile per riferimento, l'area in cui è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="17abd-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="17abd-104">In dell'alcuni casi, la variabile *livello di accesso* possono influenzare il relativo ambito.</span><span class="sxs-lookup"><span data-stu-id="17abd-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="17abd-105">Per altre informazioni, vedere [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="17abd-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="17abd-106">Ambito a livello di routine o di blocco</span><span class="sxs-lookup"><span data-stu-id="17abd-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="17abd-107">Per rendere visibili solo all'interno di un blocco di una variabile</span><span class="sxs-lookup"><span data-stu-id="17abd-107">To make a variable visible only within a block</span></span>  
  
-   <span data-ttu-id="17abd-108">Sul posto il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile tra l'avvio e terminazione istruzioni di dichiarazione di tale blocco, ad esempio tra il `For` e `Next` istruzioni di un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="17abd-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="17abd-109">È possibile fare riferimento alla variabile solo dall'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="17abd-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="17abd-110">Per rendere visibili solo all'interno di una routine di una variabile</span><span class="sxs-lookup"><span data-stu-id="17abd-110">To make a variable visible only within a procedure</span></span>  
  
-   <span data-ttu-id="17abd-111">Sul posto di `Dim` istruzione per la variabile all'interno della routine, ma all'esterno di qualsiasi blocco (ad esempio un `With`... `End With` blocco).</span><span class="sxs-lookup"><span data-stu-id="17abd-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="17abd-112">È possibile fare riferimento alla variabile solo dall'interno della routine, inclusi gli eventuali blocchi contenute nella procedura.</span><span class="sxs-lookup"><span data-stu-id="17abd-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="17abd-113">Ambito livello di modulo o Namespace</span><span class="sxs-lookup"><span data-stu-id="17abd-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="17abd-114">Per praticità, il termine singolo *a livello di modulo* si applica equamente a moduli, le classi e strutture.</span><span class="sxs-lookup"><span data-stu-id="17abd-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="17abd-115">Il livello di accesso di una variabile a livello di modulo determina il relativo ambito.</span><span class="sxs-lookup"><span data-stu-id="17abd-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="17abd-116">Lo spazio dei nomi che contiene il modulo, classe o struttura influisce anche sull'ambito.</span><span class="sxs-lookup"><span data-stu-id="17abd-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="17abd-117">Per rendere visibile in un modulo, classe o struttura di una variabile</span><span class="sxs-lookup"><span data-stu-id="17abd-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="17abd-118">Posizione di `Dim` istruzione per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17abd-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="17abd-119">Includere il [privati](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17abd-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="17abd-120">È possibile fare riferimento alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non da al suo esterno.</span><span class="sxs-lookup"><span data-stu-id="17abd-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="17abd-121">Per rendere visibile in uno spazio dei nomi una variabile</span><span class="sxs-lookup"><span data-stu-id="17abd-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="17abd-122">Posizione di `Dim` istruzione per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="17abd-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="17abd-123">Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [pubblici](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="17abd-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="17abd-124">È possibile fare riferimento alla variabile da qualsiasi posizione all'interno dello spazio dei nomi che contiene il modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="17abd-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17abd-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="17abd-125">Example</span></span>  
 <span data-ttu-id="17abd-126">Nell'esempio seguente viene dichiarata una variabile a livello di modulo e consente di limitare la visibilità al codice all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="17abd-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="17abd-127">Nell'esempio precedente, tutte le procedure definite nel modulo `demonstrateScope` può fare riferimento al `String` variabile `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="17abd-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="17abd-128">Quando la `usePrivateVariable` routine viene chiamata, viene visualizzato il contenuto della variabile di stringa `strMsg` in una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="17abd-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="17abd-129">Con la modifica seguente all'esempio precedente, la variabile stringa `strMsg` può essere indicato dal codice in qualsiasi punto nello spazio dei nomi della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="17abd-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="17abd-130">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="17abd-130">Robust Programming</span></span>  
 <span data-ttu-id="17abd-131">Più ristretto ambito di una variabile, i meno le possibilità di fare riferimento a esso accidentalmente al posto di un'altra variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="17abd-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="17abd-132">È anche possibile ridurre al minimo i problemi di riferimento corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="17abd-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="17abd-133">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17abd-133">.NET Framework Security</span></span>  
 <span data-ttu-id="17abd-134">Più ristretto ambito di una variabile, utilizzare minori saranno le probabilità che codice dannoso può rendere non corretta di esso.</span><span class="sxs-lookup"><span data-stu-id="17abd-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17abd-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17abd-135">See also</span></span>

- [<span data-ttu-id="17abd-136">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17abd-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="17abd-137">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17abd-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="17abd-138">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17abd-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="17abd-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="17abd-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="17abd-140">Dichiarazione di variabili</span><span class="sxs-lookup"><span data-stu-id="17abd-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="17abd-141">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="17abd-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
