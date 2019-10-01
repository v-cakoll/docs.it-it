---
title: Impossibile convertire il tipo anonimo in una struttura ad albero dell'espressione. Il tipo anonimo contiene un campo utilizzato nell'inizializzazione di un altro campo.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701184"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="2be0e-102">Impossibile convertire il tipo anonimo in una struttura ad albero dell'espressione. Il tipo anonimo contiene un campo utilizzato nell'inizializzazione di un altro campo.</span><span class="sxs-lookup"><span data-stu-id="2be0e-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="2be0e-103">Il compilatore non accetta la conversione di un oggetto anonimo in un albero delle espressioni quando una proprietà del tipo anonimo viene utilizzata per inizializzare un'altra proprietà del tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="2be0e-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="2be0e-104">Nel codice seguente, ad esempio, `Prop1` viene dichiarata nell'elenco di inizializzazione e quindi utilizzata come valore iniziale per `Prop2`.</span><span class="sxs-lookup"><span data-stu-id="2be0e-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="2be0e-105">**ID errore:** BC36548</span><span class="sxs-lookup"><span data-stu-id="2be0e-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2be0e-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2be0e-106">To correct this error</span></span>  
  
- <span data-ttu-id="2be0e-107">Assegnare il valore iniziale per `Prop1` a una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="2be0e-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="2be0e-108">Assegnare la variabile a `Prop1` e `Prop2`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2be0e-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2be0e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2be0e-109">See also</span></span>

- [<span data-ttu-id="2be0e-110">Tipi anonimi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2be0e-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="2be0e-111">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2be0e-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="2be0e-112">Procedura: Usare gli alberi delle espressioni per la compilazione di query dinamiche (Visual Basic) </span><span class="sxs-lookup"><span data-stu-id="2be0e-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
