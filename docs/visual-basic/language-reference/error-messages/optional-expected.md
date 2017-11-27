---
title: '&#39; facoltativo &#39; previsto'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords: BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e84371935fdd2d558e6828c05fa952b9cc4cf4f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39optional39-expected"></a><span data-ttu-id="33e31-102">&#39; facoltativo &#39; previsto</span><span class="sxs-lookup"><span data-stu-id="33e31-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="33e31-103">Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="33e31-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="33e31-104">Ogni argomento dopo un argomento facoltativo deve inoltre essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="33e31-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="33e31-105">**ID errore:** BC30202</span><span class="sxs-lookup"><span data-stu-id="33e31-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33e31-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="33e31-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="33e31-107">Se l'argomento è obbligatorio, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="33e31-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="33e31-108">Se l'argomento è facoltativo, utilizzare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="33e31-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e31-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33e31-109">See Also</span></span>  
 [<span data-ttu-id="33e31-110">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="33e31-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
