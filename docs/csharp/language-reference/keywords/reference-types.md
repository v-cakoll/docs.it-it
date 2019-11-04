---
title: Tipi di riferimento - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 61b9f8096e1b2093b1ea5589f4336618cd189c34
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422450"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="68548-102">Tipi di riferimento (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="68548-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="68548-103">Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="68548-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="68548-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="68548-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="68548-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="68548-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="68548-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="68548-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="68548-107">Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="68548-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="68548-108">class</span><span class="sxs-lookup"><span data-stu-id="68548-108">class</span></span>](class.md)

- [<span data-ttu-id="68548-109">interface</span><span class="sxs-lookup"><span data-stu-id="68548-109">interface</span></span>](interface.md)

- [<span data-ttu-id="68548-110">delegate</span><span class="sxs-lookup"><span data-stu-id="68548-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="68548-111">In c# sono disponibili i seguenti tipi di riferimento predefiniti:</span><span class="sxs-lookup"><span data-stu-id="68548-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="68548-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="68548-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="68548-113">object</span><span class="sxs-lookup"><span data-stu-id="68548-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="68548-114">string</span><span class="sxs-lookup"><span data-stu-id="68548-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="68548-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68548-115">See also</span></span>

- [<span data-ttu-id="68548-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="68548-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="68548-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="68548-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="68548-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="68548-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="68548-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="68548-119">Types</span></span>](/dotnet/csharp/language-reference/keywords)
- [<span data-ttu-id="68548-120">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="68548-120">Value Types</span></span>](value-types.md)
