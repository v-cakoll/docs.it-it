---
title: Previsto 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 411e3248409ab0184666f4efefb4ec4becf7cab1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409348"
---
# <a name="optional-expected"></a><span data-ttu-id="a75a1-102">Previsto 'Optional'</span><span class="sxs-lookup"><span data-stu-id="a75a1-102">'Optional' expected</span></span>
<span data-ttu-id="a75a1-103">Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a75a1-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="a75a1-104">Ogni argomento che segue un argomento facoltativo deve anche essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a75a1-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="a75a1-105">**ID errore:** BC30202</span><span class="sxs-lookup"><span data-stu-id="a75a1-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a75a1-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a75a1-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a75a1-107">Se l'argomento deve essere necessario, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="a75a1-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="a75a1-108">Se l'argomento è destinato a essere facoltativo, usare la `Optional` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="a75a1-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75a1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a75a1-109">See also</span></span>

- [<span data-ttu-id="a75a1-110">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="a75a1-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
