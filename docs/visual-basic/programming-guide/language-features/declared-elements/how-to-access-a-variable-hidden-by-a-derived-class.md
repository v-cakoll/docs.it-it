---
title: 'Procedura: Accedere a una variabile nascosta da una classe derivata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 68f92142cdc435ebd82101eea83035e1d09dcf25
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630010"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="96866-102">Procedura: Accedere a una variabile nascosta da una classe derivata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96866-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="96866-103">Quando il codice in una classe derivata accede a una variabile, il compilatore normalmente risolve il riferimento alla versione accessibile più vicina, ovvero la versione accessibile, il minor numero di passaggi derivazionali dalla classe di accesso.</span><span class="sxs-lookup"><span data-stu-id="96866-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="96866-104">Se la variabile è definita nella classe derivata, il codice accede normalmente a tale definizione.</span><span class="sxs-lookup"><span data-stu-id="96866-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="96866-105">Se la variabile della classe derivata ombreggia una variabile nella classe di base, nasconde la versione della classe base.</span><span class="sxs-lookup"><span data-stu-id="96866-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="96866-106">Tuttavia, è possibile accedere alla variabile della classe base qualificando la `MyBase` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="96866-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="96866-107">Per accedere a una variabile della classe di base nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="96866-107">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="96866-108">In un'espressione o in un'istruzione di assegnazione precedere il nome della `MyBase` variabile con la parola chiave`.`e un punto ().</span><span class="sxs-lookup"><span data-stu-id="96866-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="96866-109">Il compilatore risolve il riferimento alla versione della classe di base della variabile.</span><span class="sxs-lookup"><span data-stu-id="96866-109">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="96866-110">Nell'esempio seguente viene illustrata l'ombreggiatura tramite ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="96866-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="96866-111">Crea due riferimenti, uno che accede alla variabile di shadowing e uno che ignora lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="96866-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="96866-112">Nell'esempio precedente la variabile `shadowString` viene dichiarata nella classe base e viene ombreggiata nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="96866-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="96866-113">La routine `showStrings` della classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="96866-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="96866-114">Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la `MyBase` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="96866-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="96866-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="96866-115">Robust Programming</span></span>

<span data-ttu-id="96866-116">Per ridurre il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata, è possibile qualificare completamente tutti i riferimenti a una variabile ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="96866-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="96866-117">Lo shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="96866-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="96866-118">Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata.</span><span class="sxs-lookup"><span data-stu-id="96866-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="96866-119">Questo può aumentare il rischio di fare riferimento alla versione errata della variabile.</span><span class="sxs-lookup"><span data-stu-id="96866-119">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="96866-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96866-120">See also</span></span>

- [<span data-ttu-id="96866-121">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="96866-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="96866-122">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96866-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="96866-123">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="96866-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="96866-124">Procedura: Nascondere una variabile con lo stesso nome della variabile</span><span class="sxs-lookup"><span data-stu-id="96866-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="96866-125">Procedura: Nascondi una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="96866-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="96866-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="96866-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="96866-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="96866-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="96866-128">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="96866-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="96866-129">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="96866-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
