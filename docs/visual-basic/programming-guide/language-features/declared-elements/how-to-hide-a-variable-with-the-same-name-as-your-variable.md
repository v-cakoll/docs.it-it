---
title: "Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: a7ebc4eb44592800decd5ef943750f0cd845afb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653118"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="c819d-102">Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c819d-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="c819d-103">È possibile nascondere una variabile da *shadowing* , vale a dire ridefinirla con una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c819d-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="c819d-104">È possibile nascondere la variabile che si desidera nascondere in due modi:</span><span class="sxs-lookup"><span data-stu-id="c819d-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
-   <span data-ttu-id="c819d-105">**Shadowing tramite l'ambito.**</span><span class="sxs-lookup"><span data-stu-id="c819d-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="c819d-106">È possibile nascondere mediante l'ambito da dichiararla all'interno di un'area secondaria dell'area che contiene la variabile che si desidera nascondere.</span><span class="sxs-lookup"><span data-stu-id="c819d-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
-   <span data-ttu-id="c819d-107">**Shadowing tramite eredità.**</span><span class="sxs-lookup"><span data-stu-id="c819d-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="c819d-108">Se la variabile che si desidera nascondere è definita a livello di classe, è possibile nascondere, tramite l'ereditarietà da dichiararla nuovamente con la [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) parola chiave in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c819d-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="c819d-109">Due modi per nascondere una variabile</span><span class="sxs-lookup"><span data-stu-id="c819d-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="c819d-110">Per nascondere una variabile eseguendone lo shadowing mediante ambito</span><span class="sxs-lookup"><span data-stu-id="c819d-110">To hide a variable by shadowing it through scope</span></span>  
  
1.  <span data-ttu-id="c819d-111">Determinare l'area di definizione della variabile a cui che si desidera nascondere e definire un'area secondaria in cui si desidera ridefinirla con la variabile.</span><span class="sxs-lookup"><span data-stu-id="c819d-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="c819d-112">Area della variabile</span><span class="sxs-lookup"><span data-stu-id="c819d-112">Variable's region</span></span>|<span data-ttu-id="c819d-113">Area secondaria consentita per la ridefinizione</span><span class="sxs-lookup"><span data-stu-id="c819d-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="c819d-114">Modulo</span><span class="sxs-lookup"><span data-stu-id="c819d-114">Module</span></span>|<span data-ttu-id="c819d-115">Una classe all'interno del modulo</span><span class="sxs-lookup"><span data-stu-id="c819d-115">A class within the module</span></span>|  
    |<span data-ttu-id="c819d-116">Classe</span><span class="sxs-lookup"><span data-stu-id="c819d-116">Class</span></span>|<span data-ttu-id="c819d-117">Una sottoclasse della classe</span><span class="sxs-lookup"><span data-stu-id="c819d-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="c819d-118">Una routine all'interno della classe</span><span class="sxs-lookup"><span data-stu-id="c819d-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="c819d-119">Non è possibile ridefinire una variabile di routine in un blocco in questa procedura, ad esempio un `If`... `End If` costruzione o `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="c819d-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2.  <span data-ttu-id="c819d-120">Se non esiste già, creare l'area secondaria.</span><span class="sxs-lookup"><span data-stu-id="c819d-120">Create the subregion if it does not already exist.</span></span>  
  
3.  <span data-ttu-id="c819d-121">All'interno della sottoarea scrivere un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiara la variabile ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="c819d-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="c819d-122">Quando il codice all'interno di aree secondarie fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile di shadowing.</span><span class="sxs-lookup"><span data-stu-id="c819d-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="c819d-123">Nell'esempio seguente viene illustrato lo shadowing mediante ambito, nonché un riferimento che consente di ignorare lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="c819d-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="c819d-124">Nell'esempio precedente viene dichiarata la variabile `num` a livello di modulo sia a livello di routine (nella procedura `show`).</span><span class="sxs-lookup"><span data-stu-id="c819d-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="c819d-125">La variabile locale `num` nasconde la variabile a livello di modulo `num` all'interno di `show`, in modo che la variabile locale è impostata su 2.</span><span class="sxs-lookup"><span data-stu-id="c819d-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="c819d-126">Tuttavia, è presente alcuna variabile locale a ombreggiatura `num` nel `useModuleLevelNum` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c819d-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="c819d-127">Pertanto, `useModuleLevelNum` imposta il valore della variabile a livello di modulo su 1.</span><span class="sxs-lookup"><span data-stu-id="c819d-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="c819d-128">Il `MsgBox` chiamare all'interno di `show` ignora il meccanismo di shadowing specificando `num` con il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="c819d-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="c819d-129">Di conseguenza, Visualizza la variabile a livello di modulo anziché la variabile locale.</span><span class="sxs-lookup"><span data-stu-id="c819d-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="c819d-130">Per nascondere una variabile eseguendone lo shadowing tramite eredità</span><span class="sxs-lookup"><span data-stu-id="c819d-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1.  <span data-ttu-id="c819d-131">Assicurarsi che la variabile che si desidera nascondere è dichiarata in una classe e a livello di classe (all'esterno di qualsiasi routine).</span><span class="sxs-lookup"><span data-stu-id="c819d-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="c819d-132">In caso contrario è possibile eseguire lo shadowing tramite l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c819d-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2.  <span data-ttu-id="c819d-133">Definire una classe derivata dalla classe della variabile, se non ne esiste già.</span><span class="sxs-lookup"><span data-stu-id="c819d-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3.  <span data-ttu-id="c819d-134">All'interno della classe derivata, scrivere un `Dim` istruzione di dichiarazione della variabile.</span><span class="sxs-lookup"><span data-stu-id="c819d-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="c819d-135">Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c819d-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="c819d-136">Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c819d-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="c819d-137">Nell'esempio seguente viene illustrato lo shadowing tramite eredità.</span><span class="sxs-lookup"><span data-stu-id="c819d-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="c819d-138">Rende i due riferimenti, uno che accede alla variabile shadowing e uno che consente di ignorare lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="c819d-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="c819d-139">Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe base e lo nasconde nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c819d-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="c819d-140">La procedura `showStrings` nella classe derivata, Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="c819d-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="c819d-141">Verrà quindi visualizzata la versione nascosta quando `shadowString` completo con il `MyBase` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c819d-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c819d-142">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c819d-142">Robust Programming</span></span>  
 <span data-ttu-id="c819d-143">Shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c819d-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="c819d-144">Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione del codice e la presenza di una stringa di qualifica.</span><span class="sxs-lookup"><span data-stu-id="c819d-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="c819d-145">Ciò può aumentare il rischio di fare riferimento a una versione di una variabile nascosta non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="c819d-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="c819d-146">È possibile ridurre tale rischio in modo completo tutti i riferimenti a una variabile nascosta.</span><span class="sxs-lookup"><span data-stu-id="c819d-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c819d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c819d-147">See Also</span></span>  
 [<span data-ttu-id="c819d-148">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="c819d-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="c819d-149">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c819d-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="c819d-150">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="c819d-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="c819d-151">Procedura: nascondere una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="c819d-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="c819d-152">Procedura: accedere a una variabile nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="c819d-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="c819d-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="c819d-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="c819d-154">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="c819d-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="c819d-155">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="c819d-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
