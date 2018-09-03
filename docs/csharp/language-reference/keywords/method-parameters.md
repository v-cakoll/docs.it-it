---
title: Parametri di metodo (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 446a5239fa1de8559dea50f7e8b8869aed0297c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390000"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="3a88a-102">Parametri di metodo (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3a88a-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="3a88a-103">I parametri dichiarati per un metodo senza [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), vengono passati al metodo chiamato per valore.</span><span class="sxs-lookup"><span data-stu-id="3a88a-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="3a88a-104">che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="3a88a-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="3a88a-105">Usando una parola chiave del parametro, è possibile modificare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="3a88a-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="3a88a-106">Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:</span><span class="sxs-lookup"><span data-stu-id="3a88a-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="3a88a-107">[params](../../../csharp/language-reference/keywords/params.md) specifica che questo parametro può accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="3a88a-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="3a88a-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="3a88a-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="3a88a-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="3a88a-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="3a88a-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="3a88a-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a88a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a88a-111">See Also</span></span>

- [<span data-ttu-id="3a88a-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3a88a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3a88a-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a88a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3a88a-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="3a88a-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
