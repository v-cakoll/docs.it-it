---
title: Il tipo della variabile '<variablename>' non verrà dedotto perché associato a un ambito di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: e56529919945558df178e18a83a895a79bfe4919
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512719"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="7fffa-102">Il tipo per la variabile\<' variablename >' non verrà dedotto perché è associato a un campo in un ambito di inclusione</span><span class="sxs-lookup"><span data-stu-id="7fffa-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="7fffa-103">Il tipo per la variabile\<' variablename >' non verrà dedotto perché è associato a un campo in un ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="7fffa-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="7fffa-104">Modificare il nome di '\<VariableName >' o usare il nome completo (ad esempio,' me. VariableName ' o ' MyBase. VariableName ').</span><span class="sxs-lookup"><span data-stu-id="7fffa-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="7fffa-105">Una variabile di controllo loop nel codice ha lo stesso nome di un campo della classe o di un altro ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="7fffa-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="7fffa-106">Poiché la variabile di controllo viene utilizzata senza `As` una clausola, viene associata al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile o ne deduce il tipo.</span><span class="sxs-lookup"><span data-stu-id="7fffa-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="7fffa-107">Nell'esempio `Index`seguente, la variabile di controllo `For` nell'istruzione è associata `Customer` al `Index` campo nella classe.</span><span class="sxs-lookup"><span data-stu-id="7fffa-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="7fffa-108">Il compilatore non crea una nuova variabile per la variabile `Index` di controllo o ne deduce il tipo.</span><span class="sxs-lookup"><span data-stu-id="7fffa-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
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

<span data-ttu-id="7fffa-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="7fffa-109">By default, this message is a warning.</span></span> <span data-ttu-id="7fffa-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7fffa-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="7fffa-111">**ID errore:** BC42110</span><span class="sxs-lookup"><span data-stu-id="7fffa-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="7fffa-112">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="7fffa-112">To address this warning</span></span>

- <span data-ttu-id="7fffa-113">Impostare la variabile di controllo del ciclo come variabile locale cambiando il nome in un identificatore che non sia anche il nome di un campo della classe.</span><span class="sxs-lookup"><span data-stu-id="7fffa-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="7fffa-114">Chiarire che la variabile di controllo del ciclo viene associata al campo della classe `Me.` anteponendo il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="7fffa-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="7fffa-115">Anziché basarsi sull'inferenza del tipo locale, usare `As` una clausola per specificare un tipo per la variabile di controllo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="7fffa-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="7fffa-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fffa-116">Example</span></span>
 <span data-ttu-id="7fffa-117">Il codice seguente illustra l'esempio precedente con la prima correzione sul posto.</span><span class="sxs-lookup"><span data-stu-id="7fffa-117">The following code shows the earlier example with the first correction in place.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="7fffa-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fffa-118">See also</span></span>

- [<span data-ttu-id="7fffa-119">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="7fffa-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="7fffa-120">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="7fffa-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="7fffa-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="7fffa-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="7fffa-122">Procedura: Fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="7fffa-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="7fffa-123">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="7fffa-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7fffa-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="7fffa-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
