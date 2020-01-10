---
title: Tipi di riferimento - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 16e7cdc624979f9a35e287ea5274bd9398c83132
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715170"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="994fa-102">Tipi di riferimento (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="994fa-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="994fa-103">Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="994fa-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="994fa-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="994fa-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="994fa-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="994fa-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="994fa-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="994fa-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="994fa-107">Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="994fa-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="994fa-108">classe</span><span class="sxs-lookup"><span data-stu-id="994fa-108">class</span></span>](class.md)

- [<span data-ttu-id="994fa-109">interface</span><span class="sxs-lookup"><span data-stu-id="994fa-109">interface</span></span>](interface.md)

- [<span data-ttu-id="994fa-110">delegate</span><span class="sxs-lookup"><span data-stu-id="994fa-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="994fa-111">In c# sono disponibili i seguenti tipi di riferimento predefiniti:</span><span class="sxs-lookup"><span data-stu-id="994fa-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="994fa-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="994fa-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="994fa-113">object</span><span class="sxs-lookup"><span data-stu-id="994fa-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="994fa-114">string</span><span class="sxs-lookup"><span data-stu-id="994fa-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="994fa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="994fa-115">See also</span></span>

- [<span data-ttu-id="994fa-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="994fa-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="994fa-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="994fa-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="994fa-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="994fa-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="994fa-119">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="994fa-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="994fa-120">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="994fa-120">Value types</span></span>](value-types.md)
