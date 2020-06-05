---
title: Il tipo della variabile '<variablename>' non verrà dedotto perché associato a un ambito di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 98aeb5699fdd5e5e538a205acd37436019c3fc03
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363046"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="b43de-102">Il tipo della variabile '\<variablename>' non verrà dedotto perché associato a un ambito di inclusione</span><span class="sxs-lookup"><span data-stu-id="b43de-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="b43de-103">Il tipo per la variabile ' \<variablename> ' non verrà dedotto perché è associato a un campo in un ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="b43de-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="b43de-104">Modificare il nome di ' \<variablename> ' o usare il nome completo (ad esempio,' me. VariableName ' o ' MyBase. VariableName ').</span><span class="sxs-lookup"><span data-stu-id="b43de-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="b43de-105">Una variabile di controllo loop nel codice ha lo stesso nome di un campo della classe o di un altro ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="b43de-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="b43de-106">Poiché la variabile di controllo viene utilizzata senza una `As` clausola, viene associata al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile o ne deduce il tipo.</span><span class="sxs-lookup"><span data-stu-id="b43de-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="b43de-107">Nell'esempio seguente, `Index` la variabile di controllo nell' `For` istruzione è associata al `Index` campo nella `Customer` classe.</span><span class="sxs-lookup"><span data-stu-id="b43de-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="b43de-108">Il compilatore non crea una nuova variabile per la variabile di controllo `Index` o ne deduce il tipo.</span><span class="sxs-lookup"><span data-stu-id="b43de-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

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

<span data-ttu-id="b43de-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="b43de-109">By default, this message is a warning.</span></span> <span data-ttu-id="b43de-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b43de-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="b43de-111">**ID errore:** BC42110</span><span class="sxs-lookup"><span data-stu-id="b43de-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="b43de-112">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="b43de-112">To address this warning</span></span>

- <span data-ttu-id="b43de-113">Impostare la variabile di controllo del ciclo come variabile locale cambiando il nome in un identificatore che non sia anche il nome di un campo della classe.</span><span class="sxs-lookup"><span data-stu-id="b43de-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="b43de-114">Chiarire che la variabile di controllo del ciclo viene associata al campo della classe anteponendo `Me.` il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="b43de-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="b43de-115">Anziché basarsi sull'inferenza del tipo locale, usare una `As` clausola per specificare un tipo per la variabile di controllo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="b43de-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="b43de-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b43de-116">Example</span></span>
 <span data-ttu-id="b43de-117">Il codice seguente illustra l'esempio precedente con la prima correzione sul posto.</span><span class="sxs-lookup"><span data-stu-id="b43de-117">The following code shows the earlier example with the first correction in place.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b43de-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b43de-118">See also</span></span>

- [<span data-ttu-id="b43de-119">Option Infer (istruzione)</span><span class="sxs-lookup"><span data-stu-id="b43de-119">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="b43de-120">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="b43de-120">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="b43de-121">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="b43de-121">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="b43de-122">Procedura: fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="b43de-122">How to: Refer to the Current Instance of an Object</span></span>](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="b43de-123">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="b43de-123">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="b43de-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="b43de-124">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
