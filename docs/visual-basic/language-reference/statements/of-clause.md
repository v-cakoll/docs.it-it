---
title: Clausola Of (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: c0cfbb5109d5b49f995028944e735c96440c9ab2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583502"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="11460-102">Clausola Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11460-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="11460-103">Introduce una clausola `Of`, che identifica un *parametro di tipo* in una classe, una struttura, un'interfaccia, un delegato o una routine *generica* .</span><span class="sxs-lookup"><span data-stu-id="11460-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="11460-104">Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="11460-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="11460-105">Utilizzo della parola chiave of</span><span class="sxs-lookup"><span data-stu-id="11460-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="11460-106">Nell'esempio di codice seguente viene usata la parola chiave `Of` per definire il contorno di una classe che accetta due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="11460-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="11460-107">*Vincola* il parametro `keyType` dall'interfaccia <xref:System.IComparable>, il che significa che il codice consumer deve fornire un argomento di tipo che implementi <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="11460-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="11460-108">Questa operazione è necessaria in modo che la procedura `add` possa chiamare il metodo <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11460-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="11460-109">Per altre informazioni sui vincoli, vedere [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="11460-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="11460-110">Se si completa la definizione di classe precedente, è possibile creare una varietà di `dictionary` classi.</span><span class="sxs-lookup"><span data-stu-id="11460-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="11460-111">I tipi forniti per `entryType` e `keyType` determinare il tipo di voce che la classe include e il tipo di chiave che associa a ogni voce.</span><span class="sxs-lookup"><span data-stu-id="11460-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="11460-112">A causa del vincolo, è necessario fornire a `keyType` un tipo che implementi <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="11460-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="11460-113">Nell'esempio di codice seguente viene creato un oggetto che include `String` voci e associa una chiave di `Integer` a ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="11460-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="11460-114">`Integer` implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType`.</span><span class="sxs-lookup"><span data-stu-id="11460-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="11460-115">È possibile usare la parola chiave `Of` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="11460-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="11460-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="11460-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="11460-117">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="11460-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="11460-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="11460-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="11460-119">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="11460-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="11460-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="11460-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="11460-121">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="11460-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="11460-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11460-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="11460-123">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="11460-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="11460-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11460-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="11460-125">In</span><span class="sxs-lookup"><span data-stu-id="11460-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="11460-126">Out</span><span class="sxs-lookup"><span data-stu-id="11460-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
