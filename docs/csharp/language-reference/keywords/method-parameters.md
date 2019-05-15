---
title: Parametri di metodo - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 6746b572719b3233f3b99afde3dd8b5c0b7abcf1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592965"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="78384-102">Parametri di metodo (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="78384-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="78384-103">I parametri dichiarati per un metodo senza [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), vengono passati al metodo chiamato per valore.</span><span class="sxs-lookup"><span data-stu-id="78384-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="78384-104">che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="78384-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="78384-105">Usando una parola chiave del parametro, è possibile modificare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="78384-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="78384-106">Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:</span><span class="sxs-lookup"><span data-stu-id="78384-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="78384-107">[params](../../../csharp/language-reference/keywords/params.md) specifica che questo parametro può accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="78384-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="78384-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="78384-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="78384-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="78384-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="78384-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="78384-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78384-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78384-111">See also</span></span>

- [<span data-ttu-id="78384-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="78384-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="78384-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="78384-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="78384-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="78384-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
