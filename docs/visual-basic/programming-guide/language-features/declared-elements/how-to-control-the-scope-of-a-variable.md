---
title: "Procedura: controllare l'ambito di una variabile"
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
ms.openlocfilehash: 8b21f22edea84448e3f2969c3e4b07c08a17a338
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357348"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="d54a5-102">Procedura: controllare l'ambito di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d54a5-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="d54a5-103">In genere, una variabile è nell' *ambito*o visibile per riferimento, in tutta l'area in cui viene dichiarata.</span><span class="sxs-lookup"><span data-stu-id="d54a5-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="d54a5-104">In alcuni casi, il livello di *accesso* della variabile può influenzare il proprio ambito.</span><span class="sxs-lookup"><span data-stu-id="d54a5-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="d54a5-105">Per altre informazioni, vedere [Scope in Visual Basic](scope.md).</span><span class="sxs-lookup"><span data-stu-id="d54a5-105">For more information, see [Scope in Visual Basic](scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="d54a5-106">Ambito a livello di blocco o di procedura</span><span class="sxs-lookup"><span data-stu-id="d54a5-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="d54a5-107">Per rendere una variabile visibile solo all'interno di un blocco</span><span class="sxs-lookup"><span data-stu-id="d54a5-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="d54a5-108">Inserire l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) per la variabile tra le istruzioni di inizializzazione e terminazione del blocco, ad esempio tra le `For` istruzioni e `Next` di un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="d54a5-108">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="d54a5-109">È possibile fare riferimento alla variabile solo dall'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="d54a5-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="d54a5-110">Per rendere una variabile visibile solo all'interno di una routine</span><span class="sxs-lookup"><span data-stu-id="d54a5-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="d54a5-111">Inserire l' `Dim` istruzione per la variabile all'interno della routine, ma all'esterno di qualsiasi blocco (ad esempio un `With` blocco... `End With` ).</span><span class="sxs-lookup"><span data-stu-id="d54a5-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="d54a5-112">È possibile fare riferimento alla variabile solo dalla procedura, incluso all'interno di qualsiasi blocco contenuto nella procedura.</span><span class="sxs-lookup"><span data-stu-id="d54a5-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="d54a5-113">Ambito a livello di modulo o di spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d54a5-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="d54a5-114">Per praticità, il *livello del modulo* a singolo termine si applica ugualmente a moduli, classi e strutture.</span><span class="sxs-lookup"><span data-stu-id="d54a5-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="d54a5-115">Il livello di accesso di una variabile a livello di modulo ne determina l'ambito.</span><span class="sxs-lookup"><span data-stu-id="d54a5-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="d54a5-116">Lo spazio dei nomi che contiene il modulo, la classe o la struttura influenza anche l'ambito.</span><span class="sxs-lookup"><span data-stu-id="d54a5-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="d54a5-117">Per rendere visibile una variabile in un modulo, una classe o una struttura</span><span class="sxs-lookup"><span data-stu-id="d54a5-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="d54a5-118">Inserire l' `Dim` istruzione per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="d54a5-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="d54a5-119">Includere la parola chiave [private](../../../language-reference/modifiers/private.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d54a5-119">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="d54a5-120">È possibile fare riferimento alla variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, ma non dall'esterno.</span><span class="sxs-lookup"><span data-stu-id="d54a5-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="d54a5-121">Per rendere visibile una variabile in uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d54a5-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="d54a5-122">Inserire l' `Dim` istruzione per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="d54a5-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="d54a5-123">Includere la parola chiave [Friend](../../../language-reference/modifiers/friend.md) o [public](../../../language-reference/modifiers/public.md) nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d54a5-123">Include the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="d54a5-124">È possibile fare riferimento alla variabile da qualsiasi punto all'interno dello spazio dei nomi che contiene il modulo, la classe o la struttura.</span><span class="sxs-lookup"><span data-stu-id="d54a5-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d54a5-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d54a5-125">Example</span></span>  
 <span data-ttu-id="d54a5-126">Nell'esempio seguente viene dichiarata una variabile a livello di modulo e la relativa visibilità viene limitata al codice all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="d54a5-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="d54a5-127">Nell'esempio precedente, tutte le procedure definite in module `demonstrateScope` possono fare riferimento alla `String` variabile `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="d54a5-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="d54a5-128">Quando `usePrivateVariable` viene chiamata la stored procedure, viene visualizzato il contenuto della variabile stringa `strMsg` in una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d54a5-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="d54a5-129">Con la seguente modifica all'esempio precedente, `strMsg` è possibile fare riferimento alla variabile di stringa dal codice in qualsiasi punto dello spazio dei nomi della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d54a5-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="d54a5-130">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="d54a5-130">Robust Programming</span></span>  
 <span data-ttu-id="d54a5-131">Più ristretto è l'ambito di una variabile, minore è il numero di opportunità disponibili per farvi riferimento accidentalmente al posto di un'altra variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="d54a5-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="d54a5-132">È anche possibile ridurre al minimo i problemi di corrispondenza dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d54a5-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d54a5-133">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d54a5-133">.NET Framework Security</span></span>  
 <span data-ttu-id="d54a5-134">Più ristretto è l'ambito di una variabile, minore è la probabilità che il codice dannoso possa utilizzarlo in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="d54a5-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54a5-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d54a5-135">See also</span></span>

- [<span data-ttu-id="d54a5-136">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d54a5-136">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="d54a5-137">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d54a5-137">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="d54a5-138">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d54a5-138">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="d54a5-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="d54a5-139">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="d54a5-140">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="d54a5-140">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="d54a5-141">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="d54a5-141">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
