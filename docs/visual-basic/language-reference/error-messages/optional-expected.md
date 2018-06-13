---
title: '&#39;Parametro facoltativo&#39; previsto'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 52e4288255a246f78730b33beb55f6d2d83ff214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593954"
---
# <a name="39optional39-expected"></a><span data-ttu-id="4b91a-102">&#39;Parametro facoltativo&#39; previsto</span><span class="sxs-lookup"><span data-stu-id="4b91a-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="4b91a-103">Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4b91a-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="4b91a-104">Ogni argomento dopo un argomento facoltativo deve inoltre essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4b91a-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="4b91a-105">**ID errore:** BC30202</span><span class="sxs-lookup"><span data-stu-id="4b91a-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b91a-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4b91a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4b91a-107">Se l'argomento è obbligatorio, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4b91a-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="4b91a-108">Se l'argomento è facoltativo, utilizzare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="4b91a-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b91a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b91a-109">See Also</span></span>  
 [<span data-ttu-id="4b91a-110">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="4b91a-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
