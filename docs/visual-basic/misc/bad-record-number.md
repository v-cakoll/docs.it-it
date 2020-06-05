---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 44a11d95d33041de9d637684f41cb003dcc36b97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84367542"
---
# <a name="bad-record-number"></a><span data-ttu-id="83c12-102">Numero di record non valido</span><span class="sxs-lookup"><span data-stu-id="83c12-102">Bad record number</span></span>
<span data-ttu-id="83c12-103">Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="83c12-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83c12-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="83c12-104">To correct this error</span></span>  
  
1. <span data-ttu-id="83c12-105">Controllare i calcoli usati per generare il numero di record.</span><span class="sxs-lookup"><span data-stu-id="83c12-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="83c12-106">Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record.</span><span class="sxs-lookup"><span data-stu-id="83c12-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="83c12-107">Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.</span><span class="sxs-lookup"><span data-stu-id="83c12-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c12-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c12-108">See also</span></span>

- [<span data-ttu-id="83c12-109">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="83c12-109">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
