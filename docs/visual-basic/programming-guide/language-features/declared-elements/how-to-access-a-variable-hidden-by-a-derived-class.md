---
title: 'Procedura: accedere a una variabile nascosta da una classe derivata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648047"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="50476-102">Procedura: accedere a una variabile nascosta da una classe derivata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50476-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="50476-103">Quando il codice in una classe derivata accede a una variabile, il compilatore risolve in genere il riferimento alla versione accessibile più vicino, vale a dire la versione accessibile i minor numero di passaggi di derivazione con le versioni precedenti dalla classe.</span><span class="sxs-lookup"><span data-stu-id="50476-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="50476-104">Se la variabile è definita nella classe derivata, il codice accede normalmente tale definizione.</span><span class="sxs-lookup"><span data-stu-id="50476-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="50476-105">Se la variabile di classe derivata nasconde una variabile nella classe base, in quanto viene nascosta la versione della classe base.</span><span class="sxs-lookup"><span data-stu-id="50476-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="50476-106">Tuttavia, è possibile accedere alla variabile della classe base qualificandola con il `MyBase` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="50476-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="50476-107">Per accedere a una variabile di classe base nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="50476-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="50476-108">In un'espressione o istruzione di assegnazione, far precedere il nome della variabile con il `MyBase` (parola chiave) e un periodo (`.`).</span><span class="sxs-lookup"><span data-stu-id="50476-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="50476-109">Il compilatore risolve il riferimento alla versione della classe base della variabile.</span><span class="sxs-lookup"><span data-stu-id="50476-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="50476-110">Nell'esempio seguente viene illustrato lo shadowing tramite eredità.</span><span class="sxs-lookup"><span data-stu-id="50476-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="50476-111">Rende i due riferimenti, uno che accede alla variabile shadowing e uno che consente di ignorare lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="50476-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="50476-112">Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe base e lo nasconde nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="50476-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="50476-113">La procedura `showStrings` nella classe derivata, Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="50476-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="50476-114">Verrà quindi visualizzata la versione nascosta quando `shadowString` completo con il `MyBase` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="50476-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="50476-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="50476-115">Robust Programming</span></span>  
 <span data-ttu-id="50476-116">Per ridurre il rischio di fare riferimento a una versione di una variabile nascosta indesiderata, è possibile qualificare completamente tutti i riferimenti a una variabile nascosta.</span><span class="sxs-lookup"><span data-stu-id="50476-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="50476-117">Shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="50476-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="50476-118">Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione del codice e la presenza di una stringa di qualifica.</span><span class="sxs-lookup"><span data-stu-id="50476-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="50476-119">Ciò può aumentare il rischio di fare riferimento alla versione errata della variabile.</span><span class="sxs-lookup"><span data-stu-id="50476-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50476-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50476-120">See Also</span></span>  
 [<span data-ttu-id="50476-121">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="50476-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="50476-122">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50476-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="50476-123">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="50476-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="50476-124">Procedura: nascondere una variabile con lo stesso nome di un'altra variabile</span><span class="sxs-lookup"><span data-stu-id="50476-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="50476-125">Procedura: nascondere una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="50476-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="50476-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="50476-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="50476-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="50476-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="50476-128">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="50476-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="50476-129">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="50476-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
