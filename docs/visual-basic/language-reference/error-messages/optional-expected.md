---
title: '&#39;Facoltativo&#39; previsto'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 46bd84e2bcf5c5bea11a5c9d8b6e9254c49e3021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642477"
---
# <a name="39optional39-expected"></a><span data-ttu-id="01cf4-102">&#39;Facoltativo&#39; previsto</span><span class="sxs-lookup"><span data-stu-id="01cf4-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="01cf4-103">Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="01cf4-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="01cf4-104">Ogni argomento dopo un argomento facoltativo deve anche essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="01cf4-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="01cf4-105">**ID errore:** BC30202</span><span class="sxs-lookup"><span data-stu-id="01cf4-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01cf4-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="01cf4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="01cf4-107">Se l'argomento è destinato a essere necessari, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="01cf4-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="01cf4-108">Se l'argomento è destinato a essere facoltativi, usare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="01cf4-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cf4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01cf4-109">See also</span></span>
- [<span data-ttu-id="01cf4-110">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="01cf4-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
