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
ms.openlocfilehash: b2d6cc94c11ca6305a75e9ee489af53ad957201e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744525"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="77577-102">Tipi di riferimento (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="77577-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="77577-103">Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="77577-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="77577-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="77577-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="77577-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="77577-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="77577-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="77577-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="77577-107">Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="77577-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="77577-108">Classe</span><span class="sxs-lookup"><span data-stu-id="77577-108">class</span></span>](class.md)

- [<span data-ttu-id="77577-109">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="77577-109">interface</span></span>](interface.md)

- [<span data-ttu-id="77577-110">Delegato</span><span class="sxs-lookup"><span data-stu-id="77577-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="77577-111">In c# sono disponibili i seguenti tipi di riferimento predefiniti:</span><span class="sxs-lookup"><span data-stu-id="77577-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="77577-112">dinamico</span><span class="sxs-lookup"><span data-stu-id="77577-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="77577-113">Oggetto</span><span class="sxs-lookup"><span data-stu-id="77577-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="77577-114">Stringa</span><span class="sxs-lookup"><span data-stu-id="77577-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="77577-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77577-115">See also</span></span>

- [<span data-ttu-id="77577-116">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="77577-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="77577-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="77577-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="77577-118">Tipi di puntatore</span><span class="sxs-lookup"><span data-stu-id="77577-118">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="77577-119">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="77577-119">Value types</span></span>](../builtin-types/value-types.md)
