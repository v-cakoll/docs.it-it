---
title: Operatori booleani (F#)
description: 'Scopri gli operatori booleani sono disponibili in F # linguaggio di programmazione.'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563428"
---
# <a name="boolean-operators"></a><span data-ttu-id="c251b-103">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="c251b-103">Boolean Operators</span></span>

<span data-ttu-id="c251b-104">In questo argomento viene descritto il supporto per gli operatori booleani nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="c251b-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="c251b-105">Riepilogo degli operatori booleani</span><span class="sxs-lookup"><span data-stu-id="c251b-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="c251b-106">Nella tabella seguente sono riepilogati gli operatori booleani sono disponibili nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="c251b-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="c251b-107">L'unico tipo supportato da questi operatori è il `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="c251b-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="c251b-108">Operatore</span><span class="sxs-lookup"><span data-stu-id="c251b-108">Operator</span></span>|<span data-ttu-id="c251b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c251b-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="c251b-110">Negazione booleana</span><span class="sxs-lookup"><span data-stu-id="c251b-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="c251b-111">Booleano OR</span><span class="sxs-lookup"><span data-stu-id="c251b-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="c251b-112">Booleano AND</span><span class="sxs-lookup"><span data-stu-id="c251b-112">Boolean AND</span></span>|

<span data-ttu-id="c251b-113">Eseguono il booleani AND e OR operatori *valutazione di corto circuito*, vale a dire valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="c251b-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="c251b-114">La seconda espressione del `&&` operatore viene valutato solo se la prima espressione restituisce `true`; la seconda espressione del `||` operatore viene valutato solo se la prima espressione restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="c251b-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c251b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c251b-115">See Also</span></span>
[<span data-ttu-id="c251b-116">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="c251b-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="c251b-117">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="c251b-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="c251b-118">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="c251b-118">Symbol and Operator Reference</span></span>](index.md)
