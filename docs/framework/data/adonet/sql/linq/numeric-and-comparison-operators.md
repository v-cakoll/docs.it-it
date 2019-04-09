---
title: Operatori numerici e di confronto
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 9b31fd2d819afbb1e589ad74f23ec139830c68b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212167"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="82c65-102">Operatori numerici e di confronto</span><span class="sxs-lookup"><span data-stu-id="82c65-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="82c65-103">Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="82c65-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="82c65-104">In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="82c65-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="82c65-105">In SQL non è supportato l'operatore aritmetico unchecked.</span><span class="sxs-lookup"><span data-stu-id="82c65-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="82c65-106">Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="82c65-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="82c65-107">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="82c65-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="82c65-108">supporta gli operatori seguenti.</span><span class="sxs-lookup"><span data-stu-id="82c65-108">supports the following operators.</span></span>  
  
-   <span data-ttu-id="82c65-109">Operatori aritmetici di base:</span><span class="sxs-lookup"><span data-stu-id="82c65-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   `-` <span data-ttu-id="82c65-110">(sottrazione)</span><span class="sxs-lookup"><span data-stu-id="82c65-110">(subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="82c65-111">Divisione con valori integer di Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="82c65-111">Visual Basic integer division (`\`)</span></span>  
  
    -   `%` <span data-ttu-id="82c65-112">(Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="82c65-112">(Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` <span data-ttu-id="82c65-113">(negazione unaria)</span><span class="sxs-lookup"><span data-stu-id="82c65-113">(unary negation)</span></span>  
  
-   <span data-ttu-id="82c65-114">Operatori di confronto di base:</span><span class="sxs-lookup"><span data-stu-id="82c65-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="82c65-115">Visual Basic `=` e c#</span><span class="sxs-lookup"><span data-stu-id="82c65-115">Visual Basic `=` and C#</span></span> `==`  
  
    -   <span data-ttu-id="82c65-116">Visual Basic `<>` e c#</span><span class="sxs-lookup"><span data-stu-id="82c65-116">Visual Basic `<>` and C#</span></span> `!=`  
  
    -   <span data-ttu-id="82c65-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82c65-117">Visual Basic</span></span> `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="82c65-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c65-118">See also</span></span>

- [<span data-ttu-id="82c65-119">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="82c65-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="82c65-120">Operatori [C#]</span><span class="sxs-lookup"><span data-stu-id="82c65-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)
- [<span data-ttu-id="82c65-121">Operatori</span><span class="sxs-lookup"><span data-stu-id="82c65-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
