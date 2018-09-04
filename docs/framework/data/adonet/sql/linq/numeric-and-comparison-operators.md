---
title: Operatori numerici e di confronto
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a7a455730860e2b11a5ceff5a70934502b312e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515066"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="fb072-102">Operatori numerici e di confronto</span><span class="sxs-lookup"><span data-stu-id="fb072-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="fb072-103">Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="fb072-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="fb072-104">In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="fb072-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="fb072-105">In SQL non è supportato l'operatore aritmetico unchecked.</span><span class="sxs-lookup"><span data-stu-id="fb072-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="fb072-106">Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fb072-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="fb072-107">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="fb072-107">Supported Operators</span></span>  
 <span data-ttu-id="fb072-108">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="fb072-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports the following operators.</span></span>  
  
-   <span data-ttu-id="fb072-109">Operatori aritmetici di base:</span><span class="sxs-lookup"><span data-stu-id="fb072-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="fb072-110">`-` (sottrazione)</span><span class="sxs-lookup"><span data-stu-id="fb072-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="fb072-111">Divisione con valori integer di Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="fb072-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="fb072-112">`%` (`Mod` di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb072-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="fb072-113">`-` (negazione unaria)</span><span class="sxs-lookup"><span data-stu-id="fb072-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="fb072-114">Operatori di confronto di base:</span><span class="sxs-lookup"><span data-stu-id="fb072-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="fb072-115">`=` di Visual Basic e `==` di C#</span><span class="sxs-lookup"><span data-stu-id="fb072-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="fb072-116">`<>` di Visual Basic e `!=` di C#</span><span class="sxs-lookup"><span data-stu-id="fb072-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="fb072-117">`Is/IsNot` Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb072-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="fb072-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb072-118">See Also</span></span>  
 [<span data-ttu-id="fb072-119">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="fb072-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="fb072-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="fb072-120">C# Operators</span></span>](https://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="fb072-121">Operatori</span><span class="sxs-lookup"><span data-stu-id="fb072-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
