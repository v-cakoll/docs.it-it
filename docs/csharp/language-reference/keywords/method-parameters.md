---
title: Parametri di metodo - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713380"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="f2608-102">Parametri di metodo (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f2608-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="f2608-103">I parametri dichiarati per un metodo senza [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md), vengono passati al metodo chiamato per valore.</span><span class="sxs-lookup"><span data-stu-id="f2608-103">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="f2608-104">che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2608-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="f2608-105">Usando una parola chiave del parametro, è possibile modificare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="f2608-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="f2608-106">Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:</span><span class="sxs-lookup"><span data-stu-id="f2608-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="f2608-107">[params](./params.md) specifica che questo parametro può accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="f2608-107">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="f2608-108">[in](./in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="f2608-108">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="f2608-109">[ref](./ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="f2608-109">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="f2608-110">[out](./out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="f2608-110">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2608-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2608-111">See also</span></span>

- [<span data-ttu-id="f2608-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f2608-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f2608-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f2608-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f2608-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f2608-114">C# Keywords</span></span>](./index.md)
