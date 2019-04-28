---
title: Operatori booleani
description: Scopri gli operatori booleani che sono disponibili in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925814"
---
# <a name="boolean-operators"></a><span data-ttu-id="f27f1-103">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="f27f1-103">Boolean Operators</span></span>

<span data-ttu-id="f27f1-104">In questo argomento viene descritto il supporto per gli operatori booleani in di F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="f27f1-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="f27f1-105">Riepilogo degli operatori booleani</span><span class="sxs-lookup"><span data-stu-id="f27f1-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="f27f1-106">Nella tabella seguente sono riepilogati gli operatori booleani che sono disponibili in di F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="f27f1-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="f27f1-107">L'unico tipo supportato da questi operatori è il `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="f27f1-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="f27f1-108">Operatore</span><span class="sxs-lookup"><span data-stu-id="f27f1-108">Operator</span></span>|<span data-ttu-id="f27f1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f27f1-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="f27f1-110">Negazione booleana</span><span class="sxs-lookup"><span data-stu-id="f27f1-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="f27f1-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="f27f1-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="f27f1-112">AND booleano</span><span class="sxs-lookup"><span data-stu-id="f27f1-112">Boolean AND</span></span>|

<span data-ttu-id="f27f1-113">Il booleani AND e OR operatori seguire *valutazione di corto circuito*, vale a dire, tali operatori valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="f27f1-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="f27f1-114">La seconda espressione del `&&` operatore viene valutato solo se la prima espressione viene valutata `true`; la seconda espressione delle `||` operatore viene valutato solo se la prima espressione viene valutata `false`.</span><span class="sxs-lookup"><span data-stu-id="f27f1-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f27f1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f27f1-115">See also</span></span>

- [<span data-ttu-id="f27f1-116">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="f27f1-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="f27f1-117">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="f27f1-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="f27f1-118">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="f27f1-118">Symbol and Operator Reference</span></span>](index.md)