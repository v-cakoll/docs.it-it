---
title: Parametri di metodo (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b20d2d233350cfb9de55cbd07e722082ec311597
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="5ab6b-102">Parametri di metodo (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5ab6b-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="5ab6b-103">I parametri dichiarati per un metodo senza [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), vengono passati al metodo chiamato per valore.</span><span class="sxs-lookup"><span data-stu-id="5ab6b-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="5ab6b-104">che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="5ab6b-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="5ab6b-105">Usando una parola chiave del parametro, è possibile modificare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="5ab6b-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="5ab6b-106">Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:</span><span class="sxs-lookup"><span data-stu-id="5ab6b-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="5ab6b-107">params</span><span class="sxs-lookup"><span data-stu-id="5ab6b-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="5ab6b-108">in</span><span class="sxs-lookup"><span data-stu-id="5ab6b-108">in</span></span>](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
  
-   [<span data-ttu-id="5ab6b-109">ref</span><span class="sxs-lookup"><span data-stu-id="5ab6b-109">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="5ab6b-110">out</span><span class="sxs-lookup"><span data-stu-id="5ab6b-110">out</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ab6b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ab6b-111">See Also</span></span>  
 [<span data-ttu-id="5ab6b-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5ab6b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5ab6b-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5ab6b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5ab6b-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="5ab6b-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
