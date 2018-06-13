---
title: Tipo per la variabile &#39; &lt;variablename&gt; &#39; non riuscita perché è associato a un campo in un ambito contenitore
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: cb423e8dcced6956eb86d484607915030c91412b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594283"
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="63905-102">Tipo per la variabile &#39; &lt;variablename&gt; &#39; non riuscita perché è associato a un campo in un ambito contenitore</span><span class="sxs-lookup"><span data-stu-id="63905-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="63905-103">Il tipo di variabile '\<variablename >' non verrà dedotto perché associato a un campo in un ambito contenitore.</span><span class="sxs-lookup"><span data-stu-id="63905-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="63905-104">Modificare il nome di '\<variablename >', oppure utilizzare il nome completo (ad esempio, 'Variablename' o 'MyBase').</span><span class="sxs-lookup"><span data-stu-id="63905-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="63905-105">Una variabile di controllo del ciclo nel codice ha lo stesso nome di un campo della classe o altro ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="63905-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="63905-106">Poiché la variabile di controllo viene utilizzata senza un `As` clausola, è associato al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile per tale né dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="63905-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="63905-107">Nell'esempio seguente, `Index`, la variabile di controllo nel `For` istruzione, è associato al `Index` campo la `Customer` classe.</span><span class="sxs-lookup"><span data-stu-id="63905-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="63905-108">Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="63905-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
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
  
 <span data-ttu-id="63905-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="63905-109">By default, this message is a warning.</span></span> <span data-ttu-id="63905-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="63905-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="63905-111">**ID errore:** BC42110</span><span class="sxs-lookup"><span data-stu-id="63905-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="63905-112">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="63905-112">To address this warning</span></span>  
  
-   <span data-ttu-id="63905-113">Rendere la variabile di controllo locale modificando il nome a un identificatore che non sia anche il nome di un campo della classe.</span><span class="sxs-lookup"><span data-stu-id="63905-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="63905-114">Chiarire che la variabile di controllo è associata al campo della classe anteponendo `Me.` al nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="63905-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="63905-115">Anziché basarsi sull'inferenza del tipo locale, utilizzare un `As` clausola per specificare un tipo per la variabile di controllo.</span><span class="sxs-lookup"><span data-stu-id="63905-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="63905-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="63905-116">Example</span></span>  
 <span data-ttu-id="63905-117">Il codice seguente viene illustrato l'esempio precedente con la correzione prima sul posto.</span><span class="sxs-lookup"><span data-stu-id="63905-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63905-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63905-118">See Also</span></span>  
 [<span data-ttu-id="63905-119">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="63905-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="63905-120">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="63905-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="63905-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="63905-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="63905-122">Procedura: fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="63905-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [<span data-ttu-id="63905-123">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="63905-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="63905-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="63905-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
