---
title: "Procedura: nascondere una variabile con lo stesso nome di un'altra variabile"
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
ms.openlocfilehash: c1f4c2fbf339358be77e76468b1db94616bf04a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357232"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="ef881-102">Procedura: nascondere una variabile con lo stesso nome di un'altra variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef881-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="ef881-103">Per nascondere una variabile, è possibile *ombreggiarla* , ovvero ridefinerla con una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="ef881-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="ef881-104">È possibile ombreggiare la variabile che si desidera nascondere in due modi:</span><span class="sxs-lookup"><span data-stu-id="ef881-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="ef881-105">**Shadowing tramite ambito.**</span><span class="sxs-lookup"><span data-stu-id="ef881-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="ef881-106">È possibile ombreggiarlo tramite l'ambito ridichiarando il contenuto in una regione secondaria dell'area contenente la variabile che si desidera nascondere.</span><span class="sxs-lookup"><span data-stu-id="ef881-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="ef881-107">**Shadowing tramite ereditarietà.**</span><span class="sxs-lookup"><span data-stu-id="ef881-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="ef881-108">Se la variabile che si desidera nascondere è definita a livello di classe, è possibile ombreggiarla tramite ereditarietà ridichiarando la parola chiave [Shadows](../../../language-reference/modifiers/shadows.md) in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ef881-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="ef881-109">Due modi per nascondere una variabile</span><span class="sxs-lookup"><span data-stu-id="ef881-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="ef881-110">Per nascondere una variabile ombreggiando l'ambito</span><span class="sxs-lookup"><span data-stu-id="ef881-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="ef881-111">Determinare l'area che definisce la variabile che si desidera nascondere e determinare un'area secondaria in cui ridefinirla con la variabile.</span><span class="sxs-lookup"><span data-stu-id="ef881-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="ef881-112">Area della variabile</span><span class="sxs-lookup"><span data-stu-id="ef881-112">Variable's region</span></span>|<span data-ttu-id="ef881-113">Area secondaria consentita per la ridefinizione</span><span class="sxs-lookup"><span data-stu-id="ef881-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="ef881-114">Modulo</span><span class="sxs-lookup"><span data-stu-id="ef881-114">Module</span></span>|<span data-ttu-id="ef881-115">Una classe all'interno del modulo</span><span class="sxs-lookup"><span data-stu-id="ef881-115">A class within the module</span></span>|
    |<span data-ttu-id="ef881-116">Class</span><span class="sxs-lookup"><span data-stu-id="ef881-116">Class</span></span>|<span data-ttu-id="ef881-117">Sottoclasse all'interno della classe</span><span class="sxs-lookup"><span data-stu-id="ef881-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="ef881-118">Una routine all'interno della classe</span><span class="sxs-lookup"><span data-stu-id="ef881-118">A procedure within the class</span></span>|

    <span data-ttu-id="ef881-119">Non è possibile ridefinire una variabile di routine in un blocco all'interno di tale procedura, ad esempio in una `If` costruzione... `End If` o un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="ef881-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="ef881-120">Creare l'area secondaria, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="ef881-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="ef881-121">All'interno dell'area secondaria scrivere un' [istruzione Dim](../../../language-reference/statements/dim-statement.md) che dichiara la variabile di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="ef881-121">Within the subregion, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="ef881-122">Quando il codice all'interno dell'area secondaria fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="ef881-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="ef881-123">Nell'esempio seguente viene illustrata l'ombreggiatura tramite l'ambito, nonché un riferimento che ignora lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="ef881-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="ef881-124">Nell'esempio precedente la variabile viene dichiarata `num` a livello di modulo e a livello di routine (nella procedura `show` ).</span><span class="sxs-lookup"><span data-stu-id="ef881-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="ef881-125">La variabile locale `num` nasconde la variabile `num` a livello di modulo in `show` , quindi la variabile locale è impostata su 2.</span><span class="sxs-lookup"><span data-stu-id="ef881-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="ef881-126">Non esiste tuttavia alcuna variabile locale da nascondere `num` nella `useModuleLevelNum` procedura.</span><span class="sxs-lookup"><span data-stu-id="ef881-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="ef881-127">Pertanto, `useModuleLevelNum` imposta il valore della variabile a livello di modulo su 1.</span><span class="sxs-lookup"><span data-stu-id="ef881-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="ef881-128">La `MsgBox` chiamata all'interno `show` Ignora il meccanismo di shadowing qualificando `num` il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="ef881-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="ef881-129">Quindi, Visualizza la variabile a livello di modulo invece della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="ef881-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="ef881-130">Per nascondere una variabile mediante lo shadowing tramite ereditarietà</span><span class="sxs-lookup"><span data-stu-id="ef881-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="ef881-131">Assicurarsi che la variabile che si desidera nascondere sia dichiarata in una classe e a livello di classe (all'esterno di qualsiasi routine).</span><span class="sxs-lookup"><span data-stu-id="ef881-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="ef881-132">In caso contrario, non sarà possibile nasconderlo tramite l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="ef881-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="ef881-133">Definire una classe derivata dalla classe della variabile se non ne esiste già una.</span><span class="sxs-lookup"><span data-stu-id="ef881-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="ef881-134">All'interno della classe derivata scrivere un' `Dim` istruzione che dichiara la variabile.</span><span class="sxs-lookup"><span data-stu-id="ef881-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="ef881-135">Includere la parola chiave [Shadows](../../../language-reference/modifiers/shadows.md) nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="ef881-135">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="ef881-136">Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="ef881-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="ef881-137">Nell'esempio seguente viene illustrata l'ombreggiatura tramite ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="ef881-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="ef881-138">Crea due riferimenti, uno che accede alla variabile di shadowing e uno che ignora lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="ef881-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="ef881-139">Nell'esempio precedente la variabile viene dichiarata `shadowString` nella classe base e viene ombreggiata nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ef881-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="ef881-140">La routine `showStrings` della classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="ef881-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="ef881-141">Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la `MyBase` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ef881-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="ef881-142">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ef881-142">Robust Programming</span></span>

<span data-ttu-id="ef881-143">Lo shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="ef881-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="ef881-144">Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata.</span><span class="sxs-lookup"><span data-stu-id="ef881-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="ef881-145">Questo può aumentare il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="ef881-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="ef881-146">È possibile ridurre il rischio selezionando completamente tutti i riferimenti a una variabile ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="ef881-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef881-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef881-147">See also</span></span>

- [<span data-ttu-id="ef881-148">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="ef881-148">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="ef881-149">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef881-149">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="ef881-150">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="ef881-150">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="ef881-151">Procedura: nascondere una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="ef881-151">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="ef881-152">Procedura: accedere a una variabile nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="ef881-152">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="ef881-153">Override</span><span class="sxs-lookup"><span data-stu-id="ef881-153">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ef881-154">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="ef881-154">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="ef881-155">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="ef881-155">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
