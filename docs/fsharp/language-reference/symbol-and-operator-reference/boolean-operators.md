---
title: Operatori booleani (F#)
description: 'Scopri gli operatori booleani sono disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="f665b-104">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="f665b-104">Boolean Operators</span></span>

<span data-ttu-id="f665b-105">In questo argomento viene descritto il supporto per gli operatori booleani nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="f665b-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="f665b-106">Riepilogo degli operatori booleani</span><span class="sxs-lookup"><span data-stu-id="f665b-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="f665b-107">Nella tabella seguente sono riepilogati gli operatori booleani sono disponibili nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="f665b-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="f665b-108">L'unico tipo supportato da questi operatori è il `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="f665b-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="f665b-109">Operatore</span><span class="sxs-lookup"><span data-stu-id="f665b-109">Operator</span></span>|<span data-ttu-id="f665b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f665b-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="f665b-111">Negazione booleana</span><span class="sxs-lookup"><span data-stu-id="f665b-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="f665b-112">Booleano OR</span><span class="sxs-lookup"><span data-stu-id="f665b-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="f665b-113">Booleano AND</span><span class="sxs-lookup"><span data-stu-id="f665b-113">Boolean AND</span></span>|

<span data-ttu-id="f665b-114">Eseguono il booleani AND e OR operatori *valutazione di corto circuito*, vale a dire valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="f665b-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="f665b-115">La seconda espressione del `&&` operatore viene valutato solo se la prima espressione restituisce `true`; la seconda espressione del `||` operatore viene valutato solo se la prima espressione restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="f665b-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f665b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f665b-116">See Also</span></span>
[<span data-ttu-id="f665b-117">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="f665b-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="f665b-118">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="f665b-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="f665b-119">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="f665b-119">Symbol and Operator Reference</span></span>](index.md)
