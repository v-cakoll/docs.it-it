---
title: Previsto 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: d70a71f8b5f72edbd7f3e50bc099360d02e95389
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840549"
---
# <a name="optional-expected"></a><span data-ttu-id="26e1b-102">Previsto 'Optional'</span><span class="sxs-lookup"><span data-stu-id="26e1b-102">'Optional' expected</span></span>
<span data-ttu-id="26e1b-103">Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="26e1b-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="26e1b-104">Ogni argomento dopo un argomento facoltativo deve anche essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="26e1b-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="26e1b-105">**ID errore:** BC30202</span><span class="sxs-lookup"><span data-stu-id="26e1b-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26e1b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="26e1b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="26e1b-107">Se l'argomento è destinato a essere necessari, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="26e1b-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="26e1b-108">Se l'argomento è destinato a essere facoltativi, usare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="26e1b-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e1b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26e1b-109">See also</span></span>

- [<span data-ttu-id="26e1b-110">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="26e1b-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
