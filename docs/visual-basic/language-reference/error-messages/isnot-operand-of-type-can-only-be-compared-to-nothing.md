---
title: È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 1660971e2a1a11d7a2d14f222cd149edf4aa4c7b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249513"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="f5cec-102">È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="f5cec-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="f5cec-103">Una variabile dichiarata come tipo di valore nullable `Nothing` è `IsNot` stata confrontata con un'espressione diversa dall'utilizzo dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="f5cec-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="f5cec-104">**ID errore:** BC32128</span><span class="sxs-lookup"><span data-stu-id="f5cec-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f5cec-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f5cec-105">To correct this error</span></span>

<span data-ttu-id="f5cec-106">Per confrontare un tipo nullable con un'espressione diversa da `Nothing` usando l'operatore `IsNot` , chiamare il metodo `GetType` sul tipo nullable e confrontare il risultato con l'espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f5cec-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="f5cec-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5cec-107">See also</span></span>

- [<span data-ttu-id="f5cec-108">Tipi di valore nullableNullable Value Types</span><span class="sxs-lookup"><span data-stu-id="f5cec-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="f5cec-109">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="f5cec-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
