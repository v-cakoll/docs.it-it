---
title: Clausola Of (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="fac39-102">Clausola Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac39-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="fac39-103">Introduce un `Of` clausola che identifica un *parametro di tipo* su un *generico* classe, struttura, interfaccia, delegato o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="fac39-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="fac39-104">Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="fac39-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="fac39-105">Utilizzando la parola chiave</span><span class="sxs-lookup"><span data-stu-id="fac39-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="fac39-106">Nell'esempio di codice viene illustrato come utilizzare il `Of` (parola chiave) per definire la struttura di una classe che accetta due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="fac39-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="fac39-107">Si *vincola* il `keyType` mediante il <xref:System.IComparable> interfaccia, pertanto il codice consumer deve fornire un argomento di tipo che implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="fac39-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="fac39-108">Questa operazione è necessaria in modo che il `add` procedure può chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="fac39-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fac39-109">Per ulteriori informazioni sui vincoli, vedere [elenco tipo](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="fac39-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
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
  
 <span data-ttu-id="fac39-110">Se si completa la precedente definizione di classe, è possibile costruire un'ampia gamma di `dictionary` classi da esso.</span><span class="sxs-lookup"><span data-stu-id="fac39-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="fac39-111">I tipi che si forniscono alla `entryType` e `keyType` determinare il tipo di voce la classe contiene e il tipo di chiave associa ogni voce.</span><span class="sxs-lookup"><span data-stu-id="fac39-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="fac39-112">A causa del vincolo, è necessario fornire al `keyType` un tipo che implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="fac39-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="fac39-113">Esempio di codice seguente crea un oggetto che contiene `String` voci e lo associa un `Integer` chiave con ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="fac39-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="fac39-114">`Integer`implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType`.</span><span class="sxs-lookup"><span data-stu-id="fac39-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="fac39-115">È possibile usare la parola chiave `Of` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fac39-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="fac39-116">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="fac39-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="fac39-117">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="fac39-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="fac39-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="fac39-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fac39-119">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="fac39-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="fac39-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="fac39-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="fac39-121">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="fac39-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fac39-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac39-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="fac39-123">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="fac39-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="fac39-124">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fac39-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="fac39-125">In</span><span class="sxs-lookup"><span data-stu-id="fac39-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="fac39-126">Out</span><span class="sxs-lookup"><span data-stu-id="fac39-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
