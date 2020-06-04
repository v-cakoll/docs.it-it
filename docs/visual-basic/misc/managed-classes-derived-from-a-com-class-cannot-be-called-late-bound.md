---
title: Le classi gestite derivate da una classe COM non possono essere chiamate ad associazione tardiva.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402122"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="e1e0c-102">Le classi gestite derivate da una classe COM non possono essere chiamate ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="e1e0c-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="e1e0c-103">Si è provato a eseguire una chiamata ad associazione tardiva a una classe gestita derivata da una classe COM, ma questo tipo di chiamata non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e1e0c-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="e1e0c-104">Per risolvere il problema</span><span class="sxs-lookup"><span data-stu-id="e1e0c-104">To correct the problem</span></span>

<span data-ttu-id="e1e0c-105">Eseguire una chiamata con associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="e1e0c-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1e0c-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1e0c-106">See also</span></span>

- [<span data-ttu-id="e1e0c-107">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="e1e0c-107">Error Types</span></span>](../programming-guide/language-features/error-types.md)
