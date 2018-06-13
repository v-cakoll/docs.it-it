---
title: 'Procedura: nascondere una variabile ereditata (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: c59fdd8c6c6d2444b8d687c78c61f4e0d4bf9a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649139"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="6b331-102">Procedura: nascondere una variabile ereditata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b331-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="6b331-103">Una classe derivata eredita tutte le definizioni della relativa classe base.</span><span class="sxs-lookup"><span data-stu-id="6b331-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="6b331-104">Se si desidera definire una variabile utilizzando lo stesso nome di un elemento della classe di base, è possibile nascondere o *shadow*, tale elemento quando si definisce la variabile nella classe derivata della classe base.</span><span class="sxs-lookup"><span data-stu-id="6b331-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="6b331-105">In questo caso, il codice nella classe derivata accede alla variabile a meno che non venga esplicitamente ignorato il meccanismo di shadowing.</span><span class="sxs-lookup"><span data-stu-id="6b331-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="6b331-106">Un altro motivo, che è possibile nascondere una variabile ereditata è evitare revisione della classe base.</span><span class="sxs-lookup"><span data-stu-id="6b331-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="6b331-107">La classe di base può essere sottoposto a una modifica che consente di modificare l'elemento che sta ereditando.</span><span class="sxs-lookup"><span data-stu-id="6b331-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="6b331-108">In questo caso, il `Shadows` modificatore impone riferimenti dalla classe derivata vengano risolti alla variabile, anziché l'elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="6b331-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="6b331-109">Per nascondere una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="6b331-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="6b331-110">Assicurarsi che la variabile che si desidera nascondere è dichiarata a livello di classe (all'esterno di qualsiasi routine).</span><span class="sxs-lookup"><span data-stu-id="6b331-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="6b331-111">In caso contrario non è necessario per nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="6b331-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="6b331-112">All'interno della classe derivata, scrivere un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) dichiarare la variabile.</span><span class="sxs-lookup"><span data-stu-id="6b331-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="6b331-113">Utilizzare lo stesso nome della variabile ereditata.</span><span class="sxs-lookup"><span data-stu-id="6b331-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="6b331-114">Includere il [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="6b331-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="6b331-115">Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="6b331-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="6b331-116">Nell'esempio seguente viene illustrato lo shadowing di una variabile ereditata.</span><span class="sxs-lookup"><span data-stu-id="6b331-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
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
  
     <span data-ttu-id="6b331-117">Nell'esempio precedente viene dichiarata la variabile `shadowString` nella classe base e lo nasconde nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="6b331-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="6b331-118">La procedura `showStrings` nella classe derivata, Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="6b331-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="6b331-119">Verrà quindi visualizzata la versione nascosta quando `shadowString` completo con il `MyBase` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6b331-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6b331-120">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="6b331-120">Robust Programming</span></span>  
 <span data-ttu-id="6b331-121">Shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6b331-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="6b331-122">Quando un'istruzione di codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali la posizione dell'istruzione del codice e la presenza di una stringa di qualifica.</span><span class="sxs-lookup"><span data-stu-id="6b331-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="6b331-123">Ciò può aumentare il rischio di fare riferimento a una versione di una variabile nascosta non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="6b331-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="6b331-124">È possibile ridurre tale rischio in modo completo tutti i riferimenti a una variabile nascosta.</span><span class="sxs-lookup"><span data-stu-id="6b331-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b331-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b331-125">See Also</span></span>  
 [<span data-ttu-id="6b331-126">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="6b331-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="6b331-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b331-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="6b331-128">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="6b331-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="6b331-129">Procedura: nascondere una variabile con lo stesso nome di un'altra variabile</span><span class="sxs-lookup"><span data-stu-id="6b331-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="6b331-130">Procedura: accedere a una variabile nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="6b331-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="6b331-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="6b331-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="6b331-132">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="6b331-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="6b331-133">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="6b331-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
