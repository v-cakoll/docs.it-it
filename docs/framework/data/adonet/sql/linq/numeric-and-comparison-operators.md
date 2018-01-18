---
title: Operatori numerici e di confronto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 56558e790b8aee300da0a75ade7c0ac451a0eca1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="b2cb0-102">Operatori numerici e di confronto</span><span class="sxs-lookup"><span data-stu-id="b2cb0-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="b2cb0-103">Gli operatori aritmetici e di confronto funzionano correttamente in Common Language Runtime (CLR), ad eccezione di quanto descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="b2cb0-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="b2cb0-104">In SQL non è supportato l'operatore modulo per i numeri a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="b2cb0-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="b2cb0-105">In SQL non è supportato l'operatore aritmetico unchecked.</span><span class="sxs-lookup"><span data-stu-id="b2cb0-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="b2cb0-106">Gli operatori di incremento e decremento provocano effetti collaterali quando vengono usati in espressioni che non possono essere replicate in SQL e, di conseguenza, non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b2cb0-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="b2cb0-107">Operatori supportati</span><span class="sxs-lookup"><span data-stu-id="b2cb0-107">Supported Operators</span></span>  
 <span data-ttu-id="b2cb0-108">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b2cb0-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports the following operators.</span></span>  
  
-   <span data-ttu-id="b2cb0-109">Operatori aritmetici di base:</span><span class="sxs-lookup"><span data-stu-id="b2cb0-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="b2cb0-110">`-` (sottrazione)</span><span class="sxs-lookup"><span data-stu-id="b2cb0-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="b2cb0-111">Divisione con valori integer di Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="b2cb0-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="b2cb0-112">`%` (`Mod` di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2cb0-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="b2cb0-113">`-` (negazione unaria)</span><span class="sxs-lookup"><span data-stu-id="b2cb0-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="b2cb0-114">Operatori di confronto di base:</span><span class="sxs-lookup"><span data-stu-id="b2cb0-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="b2cb0-115">`=` di Visual Basic e `==` di C#</span><span class="sxs-lookup"><span data-stu-id="b2cb0-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="b2cb0-116">`<>` di Visual Basic e `!=` di C#</span><span class="sxs-lookup"><span data-stu-id="b2cb0-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="b2cb0-117">`Is/IsNot` Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2cb0-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="b2cb0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2cb0-118">See Also</span></span>  
 [<span data-ttu-id="b2cb0-119">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="b2cb0-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="b2cb0-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b2cb0-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="b2cb0-121">Operatori</span><span class="sxs-lookup"><span data-stu-id="b2cb0-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
