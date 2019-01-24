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
ms.openlocfilehash: e4c6c5cb8c041f1f0dfb3a9a3f858850d67d1c38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698238"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="0e378-102">Clausola Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e378-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="0e378-103">Introduce un' `Of` clausola che identifica una *il parametro di tipo* su un *generico* classe, struttura, interfaccia, delegato o procedure.</span><span class="sxs-lookup"><span data-stu-id="0e378-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="0e378-104">Per informazioni su tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="0e378-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="0e378-105">Tramite l'utilizzo della parola chiave</span><span class="sxs-lookup"><span data-stu-id="0e378-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="0e378-106">Il codice seguente viene illustrato come utilizzare il `Of` parola chiave per definire la struttura di una classe che accetta due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="0e378-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="0e378-107">Si *vincola* la `keyType` parametro per il <xref:System.IComparable> interfaccia, che significa che il codice consumer deve fornire un argomento di tipo che implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="0e378-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="0e378-108">Questa operazione è necessaria in modo che il `add` procedure può chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="0e378-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0e378-109">Per altre informazioni sui vincoli, vedere [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0e378-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
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
  
 <span data-ttu-id="0e378-110">Dopo aver completato la precedente definizione di classe, è possibile costruire una serie di `dictionary` classi da esso.</span><span class="sxs-lookup"><span data-stu-id="0e378-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="0e378-111">I tipi forniti da `entryType` e `keyType` determinare il tipo di voce contiene la classe e il tipo di chiave associa ogni voce.</span><span class="sxs-lookup"><span data-stu-id="0e378-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="0e378-112">A causa del vincolo, è necessario fornire al `keyType` un tipo che implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="0e378-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="0e378-113">L'esempio di codice seguente crea un oggetto che contiene `String` voci e associa un `Integer` chiave con ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="0e378-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="0e378-114">`Integer` implementa <xref:System.IComparable> e pertanto soddisfa il vincolo su `keyType`.</span><span class="sxs-lookup"><span data-stu-id="0e378-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="0e378-115">È possibile usare la parola chiave `Of` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e378-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0e378-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="0e378-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="0e378-117">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="0e378-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="0e378-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="0e378-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0e378-119">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="0e378-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="0e378-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="0e378-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="0e378-121">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="0e378-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e378-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e378-122">See also</span></span>
- <xref:System.IComparable>
- [<span data-ttu-id="0e378-123">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="0e378-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="0e378-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e378-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0e378-125">In</span><span class="sxs-lookup"><span data-stu-id="0e378-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="0e378-126">Out</span><span class="sxs-lookup"><span data-stu-id="0e378-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
