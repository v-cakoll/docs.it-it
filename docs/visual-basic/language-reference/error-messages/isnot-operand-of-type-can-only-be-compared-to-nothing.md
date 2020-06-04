---
title: È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: fb61b04021bd844fade94413b4f3b28b82f6411b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402798"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="ab156-102">È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="ab156-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="ab156-103">Una variabile dichiarata come tipo di valore Nullable è stata confrontata con un'espressione diversa da quella `Nothing` usata dall' `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="ab156-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="ab156-104">**ID errore:** BC32128</span><span class="sxs-lookup"><span data-stu-id="ab156-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ab156-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ab156-105">To correct this error</span></span>

<span data-ttu-id="ab156-106">Per confrontare un tipo nullable con un'espressione diversa da `Nothing` usando l'operatore `IsNot` , chiamare il metodo `GetType` sul tipo nullable e confrontare il risultato con l'espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ab156-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="ab156-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab156-107">See also</span></span>

- [<span data-ttu-id="ab156-108">Tipi di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="ab156-108">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ab156-109">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="ab156-109">IsNot Operator</span></span>](../operators/isnot-operator.md)
