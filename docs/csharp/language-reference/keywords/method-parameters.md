---
title: Parametri di metodo (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 924e261cc876d2428e28ed0f490beb46b95f96e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="4070f-102">Parametri di metodo (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4070f-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="4070f-103">Un parametro dichiarato per un metodo senza [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md) può essere associato a un valore,</span><span class="sxs-lookup"><span data-stu-id="4070f-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="4070f-104">che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="4070f-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="4070f-105">Usando una parola chiave del parametro, è possibile modificare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="4070f-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="4070f-106">Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:</span><span class="sxs-lookup"><span data-stu-id="4070f-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="4070f-107">params</span><span class="sxs-lookup"><span data-stu-id="4070f-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="4070f-108">ref</span><span class="sxs-lookup"><span data-stu-id="4070f-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="4070f-109">out</span><span class="sxs-lookup"><span data-stu-id="4070f-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="4070f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4070f-110">See Also</span></span>  
 [<span data-ttu-id="4070f-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4070f-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4070f-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4070f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4070f-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4070f-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
