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
ms.openlocfilehash: 7d76e2e7398c2f954ff4274f77ffa350efbd3617
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410747"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="3d3ad-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d3ad-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="3d3ad-103">Quando due elementi di programmazione condividono lo stesso nome, uno di essi può nascondere, o *ombreggiare*, l'altro.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="3d3ad-104">In una situazione di questo tipo, l'elemento ombreggiato non è disponibile per riferimento. al contrario, quando il codice usa il nome dell'elemento, il compilatore Visual Basic lo risolve nell'elemento ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="3d3ad-105">Scopo</span><span class="sxs-lookup"><span data-stu-id="3d3ad-105">Purpose</span></span>  
 <span data-ttu-id="3d3ad-106">Lo scopo principale dello shadowing consiste nel proteggere la definizione dei membri della classe.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="3d3ad-107">La classe base può subire una modifica che crea un elemento con lo stesso nome di uno già definito.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="3d3ad-108">In tal caso, il `Shadows` modificatore impone la risoluzione dei riferimenti attraverso la classe al membro definito, anziché al nuovo elemento della classe di base.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="3d3ad-109">Tipi di ombreggiatura</span><span class="sxs-lookup"><span data-stu-id="3d3ad-109">Types of Shadowing</span></span>  
 <span data-ttu-id="3d3ad-110">Un elemento può nascondere un altro elemento in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="3d3ad-111">L'elemento shadowing può essere dichiarato all'interno di un'area secondaria dell'area contenente l'elemento ombreggiato, nel qual caso l'ombreggiatura viene eseguita *tramite l'ambito*.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="3d3ad-112">O una classe di derivazione può ridefinire un membro di una classe di base, nel qual caso l'ombreggiatura viene eseguita *tramite ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="3d3ad-113">Shadowing tramite ambito</span><span class="sxs-lookup"><span data-stu-id="3d3ad-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="3d3ad-114">È possibile che gli elementi di programmazione dello stesso modulo, classe o struttura abbiano lo stesso nome ma un ambito diverso.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="3d3ad-115">Quando due elementi sono dichiarati in questo modo e il codice fa riferimento al nome che condividono, l'elemento con l'ambito più piccolo ombreggia l'altro elemento (l'ambito del blocco è il più piccolo).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="3d3ad-116">Un modulo, ad esempio, può definire una `Public` variabile denominata `temp` e una routine all'interno del modulo può dichiarare una variabile locale denominata `temp` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="3d3ad-117">I riferimenti a `temp` dall'interno della procedura accedono alla variabile locale, mentre i riferimenti a `temp` dall'esterno della routine accedono alla `Public` variabile.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="3d3ad-118">In questo caso, la variabile di procedura `temp` nasconde la variabile del modulo `temp` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="3d3ad-119">Nella figura seguente sono illustrate due variabili, entrambe denominate `temp` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="3d3ad-120">La variabile locale `temp` nasconde la variabile membro `temp` quando vi si accede dall'interno di una routine `p` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="3d3ad-121">Tuttavia, la `MyClass` parola chiave ignora lo shadowing e accede alla variabile membro.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Immagine che mostra lo shadowing attraverso l'ambito.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="3d3ad-123">Per un esempio di shadowing tramite l'ambito, vedere [procedura: nascondere una variabile con lo stesso nome della variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="3d3ad-124">Shadowing tramite ereditarietà</span><span class="sxs-lookup"><span data-stu-id="3d3ad-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="3d3ad-125">Se una classe derivata ridefinisce un elemento di programmazione ereditato da una classe base, l'elemento di ridefinizione nasconde l'elemento originale.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="3d3ad-126">È possibile nascondere qualsiasi tipo di elemento dichiarato o set di elementi di overload con qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="3d3ad-127">Una variabile, ad esempio, `Integer` può nascondere una `Function` routine.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="3d3ad-128">Se si nasconde una routine con un'altra procedura, è possibile usare un elenco di parametri diverso e un tipo restituito diverso.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="3d3ad-129">Nella figura seguente viene illustrata una classe di base `b` e una classe derivata `d` che eredita da `b` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="3d3ad-130">La classe base definisce una routine denominata `proc` e la classe derivata la nasconde con un'altra routine con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="3d3ad-131">La prima `Call` istruzione accede allo shadowing `proc` nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="3d3ad-132">Tuttavia, la `MyBase` parola chiave ignora lo shadowing e accede alla procedura ombreggiata nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Diagramma grafico dello shadowing tramite eredità](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="3d3ad-134">Per un esempio di shadowing tramite ereditarietà, vedere [procedura: nascondere una variabile con lo stesso nome della variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) e [procedura: nascondere una variabile ereditata](how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="3d3ad-135">Ombreggiatura e livello di accesso</span><span class="sxs-lookup"><span data-stu-id="3d3ad-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="3d3ad-136">L'elemento shadowing non è sempre accessibile dal codice usando la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="3d3ad-137">Ad esempio, potrebbe essere dichiarata `Private` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="3d3ad-138">In tal caso, lo shadowing viene sconfitto e il compilatore risolve tutti i riferimenti allo stesso elemento che avrebbe se non fosse presente alcuna ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="3d3ad-139">Questo elemento è l'elemento accessibile, il minor numero di passaggi derivazionali dalla classe shadowing.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="3d3ad-140">Se l'elemento ombreggiato è una routine, la risoluzione è la versione accessibile più vicina con lo stesso nome, l'elenco di parametri e il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="3d3ad-141">Nell'esempio seguente viene illustrata una gerarchia di ereditarietà di tre classi.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="3d3ad-142">Ogni classe definisce una `Sub` routine `display` e ogni classe derivata nasconde la `display` routine nella relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="3d3ad-143">Nell'esempio precedente, la classe derivata viene `secondClass` ombreggiata `display` con una `Private` routine.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="3d3ad-144">Quando `callDisplay` il modulo chiama `display` in `secondClass` , il codice chiamante è esterno `secondClass` e pertanto non può accedere alla procedura privata `display` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="3d3ad-145">Lo shadowing viene sconfitto e il compilatore risolve il riferimento alla routine della classe base `display` .</span><span class="sxs-lookup"><span data-stu-id="3d3ad-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="3d3ad-146">Tuttavia, l'altra classe derivata `thirdClass` dichiara `display` come `Public` , quindi il codice in `callDisplay` può accedervi.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="3d3ad-147">Shadowing e override</span><span class="sxs-lookup"><span data-stu-id="3d3ad-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="3d3ad-148">Non confondere lo shadowing con l'override di.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="3d3ad-149">Entrambi vengono usati quando una classe derivata eredita da una classe di base ed entrambi ridefiniscono un elemento dichiarato con un altro.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="3d3ad-150">Tuttavia, esistono differenze significative tra i due.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-150">But there are significant differences between the two.</span></span> <span data-ttu-id="3d3ad-151">Per un confronto, vedere [differenze tra shadowing e override](differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-151">For a comparison, see [Differences Between Shadowing and Overriding](differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="3d3ad-152">Shadowing e overload</span><span class="sxs-lookup"><span data-stu-id="3d3ad-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="3d3ad-153">Se si nasconde lo stesso elemento della classe di base con più di un elemento della classe derivata, gli elementi di shadowing diventano versioni di overload di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="3d3ad-154">Per altre informazioni, vedere [Procedure Overloading](../procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-154">For more information, see [Procedure Overloading](../procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="3d3ad-155">Accesso a un elemento ombreggiato</span><span class="sxs-lookup"><span data-stu-id="3d3ad-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="3d3ad-156">Quando si accede a un elemento da una classe derivata, in genere si esegue questa operazione attraverso l'istanza corrente della classe derivata, qualificando il nome dell'elemento con la `Me` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="3d3ad-157">Se la classe derivata nasconde l'elemento nella classe di base, è possibile accedere all'elemento della classe base qualificando la `MyBase` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="3d3ad-158">Per un esempio di accesso a un elemento ombreggiato, vedere [procedura: accedere a una variabile nascosta da una classe derivata](how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="3d3ad-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="3d3ad-159">Dichiarazione della variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="3d3ad-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="3d3ad-160">La modalità di creazione della variabile oggetto può influire anche sul fatto che la classe derivata acceda a un elemento ombreggiato o all'elemento ombreggiato.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="3d3ad-161">Nell'esempio seguente vengono creati due oggetti da una classe derivata, ma un oggetto viene dichiarato come la classe base e l'altro come classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="3d3ad-162">Nell'esempio precedente la variabile `basObj` viene dichiarata come classe base.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="3d3ad-163">L'assegnazione `dervCls` di un oggetto a essa costituisce una conversione più ampia ed è quindi valida.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="3d3ad-164">Tuttavia, la classe base non può accedere alla versione Shadow della variabile `z` nella classe derivata, quindi il compilatore si risolve nel `basObj.z` valore della classe base originale.</span><span class="sxs-lookup"><span data-stu-id="3d3ad-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d3ad-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d3ad-165">See also</span></span>

- [<span data-ttu-id="3d3ad-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="3d3ad-166">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="3d3ad-167">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d3ad-167">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="3d3ad-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="3d3ad-168">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3d3ad-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="3d3ad-169">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="3d3ad-170">Override</span><span class="sxs-lookup"><span data-stu-id="3d3ad-170">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="3d3ad-171">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="3d3ad-171">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="3d3ad-172">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="3d3ad-172">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
