---
title: Operatori numerici e di confronto
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 733c1e494c29f04aa06a4159c3b1dae219f01b44
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180336"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="b2862-102">Operatori numerici e di confronto</span><span class="sxs-lookup"><span data-stu-id="b2862-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="b2862-103">Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="b2862-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="b2862-104">In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="b2862-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="b2862-105">In SQL non è supportato l'operatore aritmetico unchecked.</span><span class="sxs-lookup"><span data-stu-id="b2862-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="b2862-106">Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b2862-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="b2862-107">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="b2862-107">Supported Operators</span></span>  
 <span data-ttu-id="b2862-108">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b2862-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports the following operators.</span></span>  
  
-   <span data-ttu-id="b2862-109">Operatori aritmetici di base:</span><span class="sxs-lookup"><span data-stu-id="b2862-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="b2862-110">`-` (sottrazione)</span><span class="sxs-lookup"><span data-stu-id="b2862-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="b2862-111">Divisione con valori integer di Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="b2862-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="b2862-112">`%` (`Mod` di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2862-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="b2862-113">`-` (negazione unaria)</span><span class="sxs-lookup"><span data-stu-id="b2862-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="b2862-114">Operatori di confronto di base:</span><span class="sxs-lookup"><span data-stu-id="b2862-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="b2862-115">`=` di Visual Basic e `==` di C#</span><span class="sxs-lookup"><span data-stu-id="b2862-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="b2862-116">`<>` di Visual Basic e `!=` di C#</span><span class="sxs-lookup"><span data-stu-id="b2862-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="b2862-117">`Is/IsNot` Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2862-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="b2862-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2862-118">See Also</span></span>  
 [<span data-ttu-id="b2862-119">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="b2862-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="b2862-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b2862-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="b2862-121">Operatori</span><span class="sxs-lookup"><span data-stu-id="b2862-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
