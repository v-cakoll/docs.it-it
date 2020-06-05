---
title: Il nome di variabile di intervallo può essere dedotto solo da un nome semplice o completo senza argomenti
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6b155de0bb62f667ca76ec9454dec1466976a9b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400409"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="4850a-102">Il nome di variabile di intervallo può essere dedotto solo da un nome semplice o completo senza argomenti</span><span class="sxs-lookup"><span data-stu-id="4850a-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="4850a-103">Un elemento di programmazione che accetta uno o più argomenti è incluso in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="4850a-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="4850a-104">Il compilatore non è in grado di dedurre una variabile di intervallo da tale elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4850a-104">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="4850a-105">**ID errore:** BC36599</span><span class="sxs-lookup"><span data-stu-id="4850a-105">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4850a-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4850a-106">To correct this error</span></span>

<span data-ttu-id="4850a-107">Specificare un nome di variabile esplicito per l'elemento di programmazione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4850a-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="4850a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4850a-108">See also</span></span>

- [<span data-ttu-id="4850a-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4850a-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4850a-110">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="4850a-110">Select Clause</span></span>](../queries/select-clause.md)
