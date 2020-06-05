---
title: Clausola Of
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
ms.openlocfilehash: 8497f46453d586fb94e1f7c82c81c6b923dd6f60
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404421"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="1ce3c-102">Clausola Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ce3c-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="1ce3c-103">Introduce una `Of` clausola che identifica un *parametro di tipo* in una classe, una struttura, un'interfaccia, un delegato o una routine *generica* .</span><span class="sxs-lookup"><span data-stu-id="1ce3c-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="1ce3c-104">Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ce3c-104">For information on generic types, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="1ce3c-105">Utilizzo della parola chiave of</span><span class="sxs-lookup"><span data-stu-id="1ce3c-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="1ce3c-106">Nell'esempio di codice seguente viene usata la `Of` parola chiave per definire il contorno di una classe che accetta due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="1ce3c-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="1ce3c-107">*Vincola* il `keyType` parametro dall' <xref:System.IComparable> interfaccia, il che significa che il codice consumer deve fornire un argomento di tipo che implementi <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="1ce3c-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="1ce3c-108">Questa operazione è necessaria in modo che la `add` procedura possa chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="1ce3c-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1ce3c-109">Per altre informazioni sui vincoli, vedere [Type List](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="1ce3c-109">For more information on constraints, see [Type List](type-list.md).</span></span>  
  
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
  
 <span data-ttu-id="1ce3c-110">Se si completa la definizione di classe precedente, è possibile creare una varietà di `dictionary` classi.</span><span class="sxs-lookup"><span data-stu-id="1ce3c-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="1ce3c-111">I tipi forniti `entryType` e `keyType` determinano il tipo di voce che la classe include e il tipo di chiave che associa a ogni voce.</span><span class="sxs-lookup"><span data-stu-id="1ce3c-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="1ce3c-112">A causa del vincolo, è necessario fornire a `keyType` un tipo che implementa <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="1ce3c-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="1ce3c-113">Nell'esempio di codice seguente viene creato un oggetto contenente le `String` voci e viene associata una `Integer` chiave a ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="1ce3c-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="1ce3c-114">`Integer`implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType` .</span><span class="sxs-lookup"><span data-stu-id="1ce3c-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="1ce3c-115">È possibile usare la parola chiave `Of` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ce3c-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1ce3c-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="1ce3c-116">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="1ce3c-117">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="1ce3c-117">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="1ce3c-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1ce3c-118">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="1ce3c-119">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="1ce3c-119">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="1ce3c-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="1ce3c-120">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="1ce3c-121">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="1ce3c-121">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ce3c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ce3c-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="1ce3c-123">Type List</span><span class="sxs-lookup"><span data-stu-id="1ce3c-123">Type List</span></span>](type-list.md)
- [<span data-ttu-id="1ce3c-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ce3c-124">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="1ce3c-125">In</span><span class="sxs-lookup"><span data-stu-id="1ce3c-125">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="1ce3c-126">Out</span><span class="sxs-lookup"><span data-stu-id="1ce3c-126">Out</span></span>](../modifiers/out-generic-modifier.md)
