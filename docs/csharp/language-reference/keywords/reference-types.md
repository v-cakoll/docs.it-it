---
title: Tipi di riferimento (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: cca9826c658581be38866410d5f966b1c7c35772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267339"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="a3f60-102">Tipi di riferimento (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a3f60-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="a3f60-103">Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="a3f60-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="a3f60-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="a3f60-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="a3f60-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="a3f60-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="a3f60-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) e [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="a3f60-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="a3f60-107">Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="a3f60-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="a3f60-108">class</span><span class="sxs-lookup"><span data-stu-id="a3f60-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="a3f60-109">interface</span><span class="sxs-lookup"><span data-stu-id="a3f60-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="a3f60-110">delegate</span><span class="sxs-lookup"><span data-stu-id="a3f60-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="a3f60-111">In c# sono disponibili i seguenti tipi di riferimento predefiniti:</span><span class="sxs-lookup"><span data-stu-id="a3f60-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="a3f60-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="a3f60-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="a3f60-113">object</span><span class="sxs-lookup"><span data-stu-id="a3f60-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="a3f60-114">string</span><span class="sxs-lookup"><span data-stu-id="a3f60-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3f60-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f60-115">See Also</span></span>  
 [<span data-ttu-id="a3f60-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a3f60-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a3f60-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a3f60-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a3f60-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a3f60-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a3f60-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="a3f60-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="a3f60-120">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="a3f60-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
