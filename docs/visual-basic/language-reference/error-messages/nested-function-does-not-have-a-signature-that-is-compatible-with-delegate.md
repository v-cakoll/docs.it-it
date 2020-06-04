---
title: La funzione annidata non dispone di una firma compatibile con il delegato '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 28d07f01c0fd467cb68d73749988273eee95edf4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409426"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="f3ae7-102">La funzione annidata non dispone di una firma compatibile con il delegato '\<delegatename>'</span><span class="sxs-lookup"><span data-stu-id="f3ae7-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="f3ae7-103">Un'espressione lambda è stata assegnata a un delegato con una firma incompatibile.</span><span class="sxs-lookup"><span data-stu-id="f3ae7-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="f3ae7-104">Nel codice seguente, ad esempio, il delegato `Del` ha due parametri Integer.</span><span class="sxs-lookup"><span data-stu-id="f3ae7-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="f3ae7-105">L'errore viene generato se un'espressione lambda con un argomento viene dichiarata come tipo `Del` :</span><span class="sxs-lookup"><span data-stu-id="f3ae7-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="f3ae7-106">**ID errore:** BC36532</span><span class="sxs-lookup"><span data-stu-id="f3ae7-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f3ae7-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f3ae7-107">To correct this error</span></span>

<span data-ttu-id="f3ae7-108">Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="f3ae7-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3ae7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3ae7-109">See also</span></span>

- [<span data-ttu-id="f3ae7-110">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="f3ae7-110">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="f3ae7-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="f3ae7-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
