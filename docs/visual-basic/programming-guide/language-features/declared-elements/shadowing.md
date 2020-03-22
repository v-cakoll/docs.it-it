---
title: Shadowing
ms.date: 07/20/2015
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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266885"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="e150f-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e150f-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="e150f-103">Quando due elementi di programmazione condividono lo stesso nome, uno di essi può nascondere, o *ombreggiare*, l'altro.</span><span class="sxs-lookup"><span data-stu-id="e150f-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="e150f-104">In una situazione di questo tipo, l'elemento nascosto non è disponibile come riferimento; al contrario, quando il codice utilizza il nome dell'elemento, il compilatore Visual Basic lo risolve nell'elemento di shadowing.</span><span class="sxs-lookup"><span data-stu-id="e150f-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="e150f-105">Scopo</span><span class="sxs-lookup"><span data-stu-id="e150f-105">Purpose</span></span>  
 <span data-ttu-id="e150f-106">Lo scopo principale dello shadowing è proteggere la definizione dei membri della classe.</span><span class="sxs-lookup"><span data-stu-id="e150f-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="e150f-107">La classe base potrebbe subire una modifica che crea un elemento con lo stesso nome di uno già definito.</span><span class="sxs-lookup"><span data-stu-id="e150f-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="e150f-108">In questo caso, il `Shadows` modificatore forza i riferimenti tramite la classe da risolvere per il membro definito, anziché per il nuovo elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="e150f-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="e150f-109">Tipi di ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="e150f-109">Types of Shadowing</span></span>  
 <span data-ttu-id="e150f-110">Un elemento può nascondere un altro elemento in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e150f-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="e150f-111">L'elemento di shadowing può essere dichiarato all'interno di una sottoarea dell'area contenente l'elemento nascosto, nel qual caso lo shadowing viene eseguito *tramite l'ambito*.</span><span class="sxs-lookup"><span data-stu-id="e150f-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="e150f-112">In alternativa, una classe di derivazione può ridefinire un membro di una classe base, nel qual caso lo shadowing viene eseguito *tramite l'ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="e150f-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="e150f-113">Shadowing attraverso l'ambito</span><span class="sxs-lookup"><span data-stu-id="e150f-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="e150f-114">È possibile che la programmazione di elementi nello stesso modulo, classe o struttura abbia lo stesso nome ma ambito diverso.</span><span class="sxs-lookup"><span data-stu-id="e150f-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="e150f-115">Quando due elementi vengono dichiarati in questo modo e il codice fa riferimento al nome che condividono, l'elemento con l'ambito più stretto nasconde l'altro elemento (l'ambito del blocco è il più stretto).</span><span class="sxs-lookup"><span data-stu-id="e150f-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="e150f-116">Ad esempio, un modulo `Public` può `temp`definire una variabile denominata , e `temp`una routine all'interno del modulo può dichiarare anche una variabile locale denominata .</span><span class="sxs-lookup"><span data-stu-id="e150f-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="e150f-117">I `temp` riferimenti a dall'interno della routine `temp` accedono alla variabile `Public` locale, mentre i riferimenti all'esterno della routine accedono alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e150f-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="e150f-118">In questo caso, `temp` la variabile `temp`di routine nasconde la variabile di modulo .</span><span class="sxs-lookup"><span data-stu-id="e150f-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="e150f-119">Nella figura seguente vengono illustrate `temp`due variabili, entrambe denominate .</span><span class="sxs-lookup"><span data-stu-id="e150f-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="e150f-120">La variabile `temp` locale nasconde `temp` la variabile membro `p`quando si accede dall'interno della propria routine .</span><span class="sxs-lookup"><span data-stu-id="e150f-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="e150f-121">Tuttavia, `MyClass` la parola chiave ignora lo shadowing e accede alla variabile membro.</span><span class="sxs-lookup"><span data-stu-id="e150f-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Immagine che mostra lo shadowing attraverso l'ambito.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="e150f-123">Per un esempio di shadowing nell'ambito, vedere [Procedura: nascondere una variabile con lo stesso nome della variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="e150f-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="e150f-124">Shadowing tramite ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e150f-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="e150f-125">Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe base, l'elemento di ridefinizione nasconde l'elemento originale.</span><span class="sxs-lookup"><span data-stu-id="e150f-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="e150f-126">È possibile nascondere qualsiasi tipo di elemento dichiarato, o set di elementi di overload, con qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="e150f-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="e150f-127">Ad esempio, `Integer` una variabile `Function` può eseguire lo shadowing di una routine.</span><span class="sxs-lookup"><span data-stu-id="e150f-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="e150f-128">Se si nasconde una routine con un'altra routine, è possibile utilizzare un elenco di parametri diverso e un tipo restituito diverso.</span><span class="sxs-lookup"><span data-stu-id="e150f-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="e150f-129">Nella figura seguente vengono `b` illustrate una `d` classe base `b`e una classe derivata che eredita da .</span><span class="sxs-lookup"><span data-stu-id="e150f-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="e150f-130">La classe base definisce `proc`una routine denominata e la classe derivata la nasconde con un'altra routine con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="e150f-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="e150f-131">La `Call` prima istruzione accede allo `proc` shadowing nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e150f-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="e150f-132">Tuttavia, `MyBase` la parola chiave ignora lo shadowing e accede alla routine sottoposta a shadowing nella classe base.</span><span class="sxs-lookup"><span data-stu-id="e150f-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Diagramma grafico dello shadowing tramite eredità](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="e150f-134">Per un esempio di shadowing tramite ereditarietà, vedere [How to: Nascondere una variabile con lo stesso nome della variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e Procedura: nascondere una variabile [ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="e150f-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="e150f-135">Shadowing e livello di accesso</span><span class="sxs-lookup"><span data-stu-id="e150f-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="e150f-136">L'elemento di shadowing non è sempre accessibile dal codice tramite la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e150f-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="e150f-137">Ad esempio, potrebbe `Private`essere dichiarato .</span><span class="sxs-lookup"><span data-stu-id="e150f-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="e150f-138">In tal caso, lo shadowing viene annullato e il compilatore risolve qualsiasi riferimento allo stesso elemento che avrebbe se non ci fosse stato lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="e150f-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="e150f-139">Questo elemento è l'elemento accessibile il minor numero di passaggi derivati-indietro dalla classe di shadowing.</span><span class="sxs-lookup"><span data-stu-id="e150f-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="e150f-140">Se l'elemento nascosto è una routine, la risoluzione è alla versione accessibile più vicina con lo stesso nome, elenco di parametri e tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="e150f-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="e150f-141">Nell'esempio seguente viene illustrata una gerarchia di ereditarietà di tre classi.</span><span class="sxs-lookup"><span data-stu-id="e150f-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="e150f-142">Ogni classe definisce una `Sub` routine `display`, `display` mentre ogni classe derivata nasconde la routine nella relativa classe base.</span><span class="sxs-lookup"><span data-stu-id="e150f-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="e150f-143">Nell'esempio precedente, le `secondClass` ombre `display` della `Private` classe derivata con una routine.</span><span class="sxs-lookup"><span data-stu-id="e150f-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="e150f-144">Quando `callDisplay` il `display` `secondClass`modulo chiama in `secondClass` , il codice `display` chiamante è esterno e pertanto non può accedere alla routine privata.</span><span class="sxs-lookup"><span data-stu-id="e150f-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="e150f-145">Lo shadowing viene sconfitto e il compilatore `display` risolve il riferimento alla routine della classe base.</span><span class="sxs-lookup"><span data-stu-id="e150f-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="e150f-146">Tuttavia, l'altra `thirdClass` classe derivata dichiara `display` come `Public`, in modo che il codice in `callDisplay` possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="e150f-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="e150f-147">Shadowing e override</span><span class="sxs-lookup"><span data-stu-id="e150f-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="e150f-148">Non confondere lo shadowing con l'override.</span><span class="sxs-lookup"><span data-stu-id="e150f-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="e150f-149">Entrambi vengono utilizzati quando una classe derivata eredita da una classe base ed entrambi ridefiniscono un elemento dichiarato con un altro.</span><span class="sxs-lookup"><span data-stu-id="e150f-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="e150f-150">Ma ci sono differenze significative tra i due.</span><span class="sxs-lookup"><span data-stu-id="e150f-150">But there are significant differences between the two.</span></span> <span data-ttu-id="e150f-151">Per un confronto, vedere [Differenze tra shadowing e override](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="e150f-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="e150f-152">Shadowing e Sovraccarico</span><span class="sxs-lookup"><span data-stu-id="e150f-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="e150f-153">Se si nasconde lo stesso elemento della classe base con più di un elemento nella classe derivata, gli elementi di shadowing diventano versioni di overload di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="e150f-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="e150f-154">Per altre informazioni, vedere [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="e150f-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="e150f-155">Accesso a un elemento ombreggiatoAccessing a Shadowed Element</span><span class="sxs-lookup"><span data-stu-id="e150f-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="e150f-156">Quando si accede a un elemento da una classe derivata, in genere si esegue questa `Me` operazione tramite l'istanza corrente di tale classe derivata, qualificando il nome dell'elemento con la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="e150f-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="e150f-157">Se la classe derivata nasconde l'elemento nella classe base, è possibile `MyBase` accedere all'elemento della classe base qualificandolo con la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="e150f-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="e150f-158">Per un esempio di accesso a un elemento nascosto, vedere [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="e150f-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="e150f-159">Dichiarazione della variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="e150f-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="e150f-160">La modalità di creazione della variabile oggetto può anche influire sulla possibilità che la classe derivata acceda a un elemento di shadowing o all'elemento ombreggiato.</span><span class="sxs-lookup"><span data-stu-id="e150f-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="e150f-161">Nell'esempio seguente vengono creati due oggetti da una classe derivata, ma un oggetto viene dichiarato come classe base e l'altro come classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e150f-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="e150f-162">Nell'esempio precedente, la `basObj` variabile viene dichiarata come classe base.</span><span class="sxs-lookup"><span data-stu-id="e150f-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="e150f-163">L'assegnazione di un `dervCls` oggetto ad esso costituisce una conversione di ampliamento ed è quindi valido.</span><span class="sxs-lookup"><span data-stu-id="e150f-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="e150f-164">Tuttavia, la classe base non può `z` accedere alla versione di shadowing `basObj.z` della variabile nella classe derivata, pertanto il compilatore viene risolto nel valore della classe base originale.</span><span class="sxs-lookup"><span data-stu-id="e150f-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e150f-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e150f-165">See also</span></span>

- [<span data-ttu-id="e150f-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="e150f-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="e150f-167">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e150f-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="e150f-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="e150f-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="e150f-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="e150f-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="e150f-170">Esegue l' override</span><span class="sxs-lookup"><span data-stu-id="e150f-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="e150f-171">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="e150f-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="e150f-172">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e150f-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
