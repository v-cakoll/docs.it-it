---
title: Il tipo della variabile '<variablename>' non verrà dedotto perché associato a un ambito di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: bcd142785d8ee736c6a1b41950fae80e4d26fa18
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838817"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="76faa-102">Il tipo della variabile '\<nomevariabile >' non riuscita perché è associato a un campo in un ambito contenitore</span><span class="sxs-lookup"><span data-stu-id="76faa-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="76faa-103">Il tipo della variabile '\<nomevariabile >' non riuscita perché è associato a un campo in un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="76faa-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="76faa-104">Modificare il nome del '\<nomevariabile >', oppure usare il nome completo (ad esempio, 'Me. variablename' o 'Variablename').</span><span class="sxs-lookup"><span data-stu-id="76faa-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="76faa-105">Una variabile di controllo ciclo nel codice ha lo stesso nome di un campo della classe o altri ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="76faa-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="76faa-106">Poiché la variabile di controllo viene usata senza un `As` clausola, è associato al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile per tale né dedurne il tipo.</span><span class="sxs-lookup"><span data-stu-id="76faa-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="76faa-107">Nell'esempio seguente `Index`, la variabile di controllo nel `For` istruzione, è associato ai `Index` campo il `Customer` classe.</span><span class="sxs-lookup"><span data-stu-id="76faa-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="76faa-108">Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="76faa-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="76faa-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="76faa-109">By default, this message is a warning.</span></span> <span data-ttu-id="76faa-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="76faa-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="76faa-111">**ID errore:** BC42110</span><span class="sxs-lookup"><span data-stu-id="76faa-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="76faa-112">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="76faa-112">To address this warning</span></span>  
  
-   <span data-ttu-id="76faa-113">Rendere la variabile di controllo locale modificando il relativo nome a un identificatore che non è anche il nome di un campo della classe.</span><span class="sxs-lookup"><span data-stu-id="76faa-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="76faa-114">Chiarire che la variabile di controllo associata al campo della classe, facendolo precedere dalla `Me.` al nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="76faa-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="76faa-115">Anziché basarsi sull'inferenza del tipo locale, usare un `As` clausola per specificare un tipo di variabile di controllo ciclo for.</span><span class="sxs-lookup"><span data-stu-id="76faa-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="76faa-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="76faa-116">Example</span></span>  
 <span data-ttu-id="76faa-117">Il codice seguente illustra l'esempio precedente con la correzione primo posto.</span><span class="sxs-lookup"><span data-stu-id="76faa-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="76faa-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76faa-118">See also</span></span>

- [<span data-ttu-id="76faa-119">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="76faa-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="76faa-120">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="76faa-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="76faa-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="76faa-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="76faa-122">Procedura: Fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="76faa-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="76faa-123">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="76faa-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="76faa-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="76faa-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
