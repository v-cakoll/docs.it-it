---
title: 'Procedura: nascondere una variabile ereditata'
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
ms.openlocfilehash: f49bba0497f9f4f2774b01284c815bba9aaed119
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357270"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="aa12b-102">Procedura: nascondere una variabile ereditata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa12b-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>

<span data-ttu-id="aa12b-103">Una classe derivata eredita tutte le definizioni della relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="aa12b-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="aa12b-104">Se si vuole definire una variabile con lo stesso nome di un elemento della classe di base, è possibile nascondere, o *ombreggiare*, tale elemento della classe base quando si definisce la variabile nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="aa12b-105">In tal caso, il codice della classe derivata accede alla variabile a meno che non venga ignorato in modo esplicito il meccanismo di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="aa12b-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>

<span data-ttu-id="aa12b-106">Un altro motivo per cui potrebbe essere necessario nascondere una variabile ereditata consiste nel proteggersi dalla revisione della classe base.</span><span class="sxs-lookup"><span data-stu-id="aa12b-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="aa12b-107">La classe base può subire una modifica che modifica l'elemento che si sta ereditando.</span><span class="sxs-lookup"><span data-stu-id="aa12b-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="aa12b-108">In tal caso, il `Shadows` modificatore impone la risoluzione dei riferimenti dalla classe derivata alla variabile, anziché all'elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="aa12b-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>

## <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="aa12b-109">Per nascondere una variabile ereditata</span><span class="sxs-lookup"><span data-stu-id="aa12b-109">To hide an inherited variable</span></span>

1. <span data-ttu-id="aa12b-110">Assicurarsi che la variabile che si desidera nascondere sia dichiarata a livello di classe (all'esterno di qualsiasi routine).</span><span class="sxs-lookup"><span data-stu-id="aa12b-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="aa12b-111">In caso contrario, non è necessario nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="aa12b-111">Otherwise, you do not need to hide it.</span></span>
  
2. <span data-ttu-id="aa12b-112">All'interno della classe derivata scrivere un' [istruzione Dim](../../../language-reference/statements/dim-statement.md) che dichiara la variabile.</span><span class="sxs-lookup"><span data-stu-id="aa12b-112">Inside your derived class, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="aa12b-113">Usare lo stesso nome della variabile ereditata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-113">Use the same name as that of the inherited variable.</span></span>

3. <span data-ttu-id="aa12b-114">Includere la parola chiave [Shadows](../../../language-reference/modifiers/shadows.md) nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="aa12b-114">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

     <span data-ttu-id="aa12b-115">Quando il codice nella classe derivata fa riferimento al nome della variabile, il compilatore risolve il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="aa12b-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

     <span data-ttu-id="aa12b-116">Nell'esempio seguente viene illustrata l'ombreggiatura di una variabile ereditata:</span><span class="sxs-lookup"><span data-stu-id="aa12b-116">The following example illustrates shadowing of an inherited variable:</span></span>
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="aa12b-117">Nell'esempio precedente la variabile viene dichiarata `shadowString` nella classe base e viene ombreggiata nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="aa12b-118">La routine `ShowStrings` della classe derivata Visualizza la versione di shadowing della stringa quando il nome `shadowString` non è qualificato.</span><span class="sxs-lookup"><span data-stu-id="aa12b-118">The procedure `ShowStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="aa12b-119">Viene quindi visualizzata la versione ombreggiata quando `shadowString` viene qualificato con la `MyBase` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="aa12b-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="aa12b-120">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="aa12b-120">Robust programming</span></span>

<span data-ttu-id="aa12b-121">Lo shadowing introduce più di una versione di una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="aa12b-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="aa12b-122">Quando un'istruzione del codice fa riferimento al nome della variabile, la versione a cui il compilatore risolve il riferimento dipende da fattori quali il percorso dell'istruzione del codice e la presenza di una stringa qualificata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="aa12b-123">Questo può aumentare il rischio di riferimento a una versione non intenzionale di una variabile ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="aa12b-124">È possibile ridurre il rischio selezionando completamente tutti i riferimenti a una variabile ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="aa12b-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa12b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa12b-125">See also</span></span>

- [<span data-ttu-id="aa12b-126">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="aa12b-126">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="aa12b-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa12b-127">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="aa12b-128">Differenze tra shadowing e override</span><span class="sxs-lookup"><span data-stu-id="aa12b-128">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="aa12b-129">Procedura: nascondere una variabile con lo stesso nome di un'altra variabile</span><span class="sxs-lookup"><span data-stu-id="aa12b-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="aa12b-130">Procedura: accedere a una variabile nascosta da una classe derivata</span><span class="sxs-lookup"><span data-stu-id="aa12b-130">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="aa12b-131">Override</span><span class="sxs-lookup"><span data-stu-id="aa12b-131">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="aa12b-132">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="aa12b-132">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="aa12b-133">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="aa12b-133">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
