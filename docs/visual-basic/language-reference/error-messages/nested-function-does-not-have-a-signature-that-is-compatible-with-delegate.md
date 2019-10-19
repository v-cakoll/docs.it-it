---
title: La funzione annidata non dispone di una firma compatibile con il delegato '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580642"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="a6969-102">La funzione annidata non dispone di una firma compatibile con il delegato ' \<delegatename >'</span><span class="sxs-lookup"><span data-stu-id="a6969-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="a6969-103">Un'espressione lambda è stata assegnata a un delegato con una firma incompatibile.</span><span class="sxs-lookup"><span data-stu-id="a6969-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="a6969-104">Nel codice seguente, ad esempio, Delegate `Del` dispone di due parametri Integer.</span><span class="sxs-lookup"><span data-stu-id="a6969-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="a6969-105">L'errore viene generato se un'espressione lambda con un argomento viene dichiarata come tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="a6969-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="a6969-106">**ID errore:** BC36532</span><span class="sxs-lookup"><span data-stu-id="a6969-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a6969-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a6969-107">To correct this error</span></span>

<span data-ttu-id="a6969-108">Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="a6969-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6969-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6969-109">See also</span></span>

- [<span data-ttu-id="a6969-110">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="a6969-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="a6969-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="a6969-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
