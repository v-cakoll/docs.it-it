---
title: Tipi di riferimento (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.referencetypes
dev_langs:
- CSharp
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed7b9c8ed4aa1136c09049c8ffd6c68beeeb2a48
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="reference-types-c-reference"></a><span data-ttu-id="aae4f-102">Tipi di riferimento (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="aae4f-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="aae4f-103">Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="aae4f-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="aae4f-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="aae4f-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="aae4f-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="aae4f-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="aae4f-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri out e ref, vedere [ref](../../../csharp/language-reference/keywords/ref.md) e [Modificatore del parametro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="aae4f-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="aae4f-107">Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="aae4f-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="aae4f-108">class</span><span class="sxs-lookup"><span data-stu-id="aae4f-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="aae4f-109">interface</span><span class="sxs-lookup"><span data-stu-id="aae4f-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="aae4f-110">delegate</span><span class="sxs-lookup"><span data-stu-id="aae4f-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="aae4f-111">In c# sono disponibili i seguenti tipi di riferimento predefiniti:</span><span class="sxs-lookup"><span data-stu-id="aae4f-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="aae4f-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="aae4f-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="aae4f-113">object</span><span class="sxs-lookup"><span data-stu-id="aae4f-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="aae4f-114">string</span><span class="sxs-lookup"><span data-stu-id="aae4f-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="aae4f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aae4f-115">See Also</span></span>  
 <span data-ttu-id="aae4f-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="aae4f-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="aae4f-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="aae4f-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="aae4f-118">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="aae4f-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="aae4f-119">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="aae4f-119">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 [<span data-ttu-id="aae4f-120">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="aae4f-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

