---
title: Shadowing in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 489e1786b08085f229f66b2dbc434b96b06d86df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="235b9-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="235b9-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="235b9-103">Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, o *shadow*, l'altro.</span><span class="sxs-lookup"><span data-stu-id="235b9-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="235b9-104">In questo caso, l'elemento nascosto non è disponibile per riferimento; al contrario, quando il codice utilizza il nome dell'elemento, il compilatore Visual Basic risolve nell'elemento di shadowing.</span><span class="sxs-lookup"><span data-stu-id="235b9-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="235b9-105">Scopo</span><span class="sxs-lookup"><span data-stu-id="235b9-105">Purpose</span></span>  
 <span data-ttu-id="235b9-106">Lo scopo principale di shadowing sia per proteggere la definizione dei membri della classe.</span><span class="sxs-lookup"><span data-stu-id="235b9-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="235b9-107">La classe di base può essere sottoposto a una modifica che crea un elemento con lo stesso nome già definito.</span><span class="sxs-lookup"><span data-stu-id="235b9-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="235b9-108">In questo caso, il `Shadows` modificatore impone che fa riferimento tramite la classe deve essere risolto per il membro è definito, anziché il nuovo elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="235b9-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="235b9-109">Tipi di Shadowing</span><span class="sxs-lookup"><span data-stu-id="235b9-109">Types of Shadowing</span></span>  
 <span data-ttu-id="235b9-110">Un elemento può nascondere un altro elemento in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="235b9-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="235b9-111">L'elemento di shadowing può essere dichiarato in un'area secondaria dell'area che contiene l'elemento nascosto, in cui viene eseguito lo shadowing *mediante l'ambito*.</span><span class="sxs-lookup"><span data-stu-id="235b9-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="235b9-112">O una classe derivata può ridefinire un membro di una classe base, in cui viene eseguito lo shadowing *tramite ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="235b9-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="235b9-113">Shadowing tramite l'ambito</span><span class="sxs-lookup"><span data-stu-id="235b9-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="235b9-114">È possibile che gli elementi nella stesso modulo, classe o struttura abbiano lo stesso nome ma ambiti diversi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="235b9-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="235b9-115">Quando vengono dichiarati due elementi in questo modo, il codice fa riferimento al nome condividono l'elemento con ambito più ristretto nasconde l'altro elemento (l'ambito del blocco è ristretto).</span><span class="sxs-lookup"><span data-stu-id="235b9-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="235b9-116">Ad esempio, un modulo è possibile definire un `Public` variabile denominata `temp`, e una procedura all'interno del modulo è possibile dichiarare una variabile locale denominata anche `temp`.</span><span class="sxs-lookup"><span data-stu-id="235b9-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="235b9-117">Fa riferimento alle `temp` dall'interno la procedura di accesso alla variabile locale, mentre i riferimenti a `temp` dall'esterno della routine accedono il `Public` variabile.</span><span class="sxs-lookup"><span data-stu-id="235b9-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="235b9-118">In questo caso, la variabile della procedura `temp` nasconde la variabile di modulo `temp`.</span><span class="sxs-lookup"><span data-stu-id="235b9-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="235b9-119">La figura seguente mostra due variabili, entrambi denominati `temp`.</span><span class="sxs-lookup"><span data-stu-id="235b9-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="235b9-120">La variabile locale `temp` nasconde la variabile membro `temp` quando si accede da all'interno della relativa routine `p`.</span><span class="sxs-lookup"><span data-stu-id="235b9-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="235b9-121">Tuttavia, il `MyClass` parola chiave ignora lo shadowing e accedere alla variabile membro.</span><span class="sxs-lookup"><span data-stu-id="235b9-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="235b9-122">![Diagramma grafico dello shadowing tramite ambito](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="235b9-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="235b9-123">Shadowing tramite l'ambito</span><span class="sxs-lookup"><span data-stu-id="235b9-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="235b9-124">Per un esempio di shadowing tramite l'ambito, vedere [procedura: nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="235b9-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="235b9-125">Shadowing tramite eredità</span><span class="sxs-lookup"><span data-stu-id="235b9-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="235b9-126">Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe base, l'elemento ridefinisce nasconde l'elemento originale.</span><span class="sxs-lookup"><span data-stu-id="235b9-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="235b9-127">È possibile nascondere qualsiasi tipo di elemento dichiarato o set di elementi in overload con qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="235b9-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="235b9-128">Ad esempio, un `Integer` variabile può nascondere un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="235b9-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="235b9-129">Se si nasconde una routine con un'altra routine, è possibile utilizzare un elenco di parametri e un tipo restituito differente.</span><span class="sxs-lookup"><span data-stu-id="235b9-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="235b9-130">Nella figura seguente viene illustrata una classe base `b` e una classe derivata `d` che eredita da `b`.</span><span class="sxs-lookup"><span data-stu-id="235b9-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="235b9-131">La classe base definisce una routine denominata `proc`, mentre la classe derivata nasconde con un'altra routine con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="235b9-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="235b9-132">Il primo `Call` istruzione accede lo shadowing `proc` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="235b9-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="235b9-133">Tuttavia, il `MyBase` parola chiave ignora lo shadowing e accedere alla routine nascosta nella classe base.</span><span class="sxs-lookup"><span data-stu-id="235b9-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="235b9-134">![Diagramma grafico dello shadowing tramite eredità](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="235b9-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="235b9-135">Shadowing tramite eredità</span><span class="sxs-lookup"><span data-stu-id="235b9-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="235b9-136">Per un esempio dello shadowing tramite eredità, vedere [procedura: nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e [procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="235b9-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="235b9-137">Shadowing e livello di accesso</span><span class="sxs-lookup"><span data-stu-id="235b9-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="235b9-138">L'elemento di shadowing non è sempre accessibile dal codice utilizzando la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="235b9-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="235b9-139">Ad esempio, può essere dichiarata `Private`.</span><span class="sxs-lookup"><span data-stu-id="235b9-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="235b9-140">In tal caso, lo shadowing viene annullato e il compilatore risolve qualsiasi riferimento allo stesso elemento avrebbe se fosse disponibile alcuna ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="235b9-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="235b9-141">Questo elemento è l'elemento accessibile il minor numero di derivazionali passaggi precedenti dalla classe di shadowing.</span><span class="sxs-lookup"><span data-stu-id="235b9-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="235b9-142">Se l'elemento nascosto non è una stored procedure, la risoluzione è nella versione accessibile più vicina con lo stesso nome, l'elenco dei parametri e tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="235b9-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="235b9-143">Nell'esempio seguente viene illustrata una gerarchia di ereditarietà delle tre classi.</span><span class="sxs-lookup"><span data-stu-id="235b9-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="235b9-144">Ogni classe definisce un `Sub` procedura `display`, e ogni classe derivata nasconde la `display` procedura nella relativa classe base.</span><span class="sxs-lookup"><span data-stu-id="235b9-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="235b9-145">Nell'esempio precedente, la classe derivata `secondClass` shadows `display` con un `Private` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="235b9-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="235b9-146">Quando modulo `callDisplay` chiamate `display` in `secondClass`, il codice chiamante non è compreso `secondClass` e pertanto non può accedere privato `display` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="235b9-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="235b9-147">Lo shadowing viene annullato e il compilatore risolve il riferimento alla classe di base `display` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="235b9-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="235b9-148">Tuttavia, l'altra classe derivata `thirdClass` dichiara `display` come `Public`, pertanto il codice in `callDisplay` possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="235b9-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="235b9-149">Shadowing e override</span><span class="sxs-lookup"><span data-stu-id="235b9-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="235b9-150">Non confondere shadowing e override.</span><span class="sxs-lookup"><span data-stu-id="235b9-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="235b9-151">Entrambi vengono utilizzati quando una classe derivata eredita da una classe base ed entrambi consentono di ridefinire un elemento dichiarato con un altro.</span><span class="sxs-lookup"><span data-stu-id="235b9-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="235b9-152">Ma esistono differenze significative tra i due.</span><span class="sxs-lookup"><span data-stu-id="235b9-152">But there are significant differences between the two.</span></span> <span data-ttu-id="235b9-153">Per un confronto, vedere [le differenze tra Shadowing e verrà ignorato](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="235b9-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="235b9-154">Shadowing e overload</span><span class="sxs-lookup"><span data-stu-id="235b9-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="235b9-155">Se si nasconde lo stesso elemento di classe di base con più di un elemento nella classe derivata, gli elementi di shadowing diventeranno versioni di overload di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="235b9-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="235b9-156">Per ulteriori informazioni, vedere [overload di routine](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="235b9-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="235b9-157">Accesso a un elemento nascosto</span><span class="sxs-lookup"><span data-stu-id="235b9-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="235b9-158">Quando si accede a un elemento da una classe derivata, in genere avviene tramite l'istanza corrente della classe derivata, specificando il nome dell'elemento con la `Me` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="235b9-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="235b9-159">Se la classe derivata nasconde l'elemento nella classe base, è possibile accedere all'elemento della classe base qualificandola con il `MyBase` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="235b9-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="235b9-160">Per un esempio di accesso a un elemento nascosto, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="235b9-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="235b9-161">Dichiarazione della variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="235b9-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="235b9-162">Come si crea la variabile oggetto può influire anche se la classe derivata accede a un elemento di shadowing o l'elemento nascosto.</span><span class="sxs-lookup"><span data-stu-id="235b9-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="235b9-163">Nell'esempio seguente crea due oggetti da una classe derivata, ma è dichiarato un oggetto della classe base e l'altro come classe derivata.</span><span class="sxs-lookup"><span data-stu-id="235b9-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="235b9-164">Nell'esempio precedente, la variabile `basObj` viene dichiarata come classe base.</span><span class="sxs-lookup"><span data-stu-id="235b9-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="235b9-165">L'assegnazione di un `dervCls` oggetto costituisce una conversione di ampliamento e pertanto è valida.</span><span class="sxs-lookup"><span data-stu-id="235b9-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="235b9-166">Tuttavia, la classe di base non può accedere alla versione di shadowing della variabile `z` nella classe derivata, pertanto, il compilatore risolve `basObj.z` il valore di classe di base originale.</span><span class="sxs-lookup"><span data-stu-id="235b9-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235b9-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="235b9-167">See Also</span></span>  
 [<span data-ttu-id="235b9-168">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="235b9-168">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="235b9-169">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="235b9-169">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="235b9-170">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="235b9-170">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="235b9-171">Shadows</span><span class="sxs-lookup"><span data-stu-id="235b9-171">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="235b9-172">Overrides</span><span class="sxs-lookup"><span data-stu-id="235b9-172">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="235b9-173">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="235b9-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="235b9-174">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="235b9-174">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
