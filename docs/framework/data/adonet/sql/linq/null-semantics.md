---
title: Semantica Null
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d32f73c8c2095c23ec164ad40fd1ab27ef1153a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="null-semantics"></a><span data-ttu-id="ee5c3-102">Semantica Null</span><span class="sxs-lookup"><span data-stu-id="ee5c3-102">Null Semantics</span></span>
<span data-ttu-id="ee5c3-103">La tabella seguente fornisce i collegamenti alle varie parti della documentazione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in cui sono descritti i problemi relativi a `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ee5c3-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="ee5c3-104">Argomento</span><span class="sxs-lookup"><span data-stu-id="ee5c3-104">Topic</span></span>|<span data-ttu-id="ee5c3-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee5c3-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ee5c3-106">Tipi SQL-CLR non corrispondenti</span><span class="sxs-lookup"><span data-stu-id="ee5c3-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="ee5c3-107">La sezione sulla semantica null di questo argomento include una discussione relativa al tipo booleano SQL a tre stati rispetto al tipo Common Language Runtime (CLR) a due stati <xref:System.Boolean>, ai tipi letterali `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) e `null` (C#) e altri problemi simili.</span><span class="sxs-lookup"><span data-stu-id="ee5c3-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="ee5c3-108">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="ee5c3-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="ee5c3-109">Nella sezione sulla semantica null di questo argomento viene descritta la semantica di confronto null in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee5c3-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="ee5c3-110">Metodi System.String</span><span class="sxs-lookup"><span data-stu-id="ee5c3-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="ee5c3-111">Nella sezione sulle differenze rispetto a .NET di questo argomento viene descritto come un risultato 0 restituito da <xref:System.String.LastIndexOf%2A> possa significare che la stringa è null o che la posizione trovata è 0.</span><span class="sxs-lookup"><span data-stu-id="ee5c3-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="ee5c3-112">Calcolare la somma dei valori in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="ee5c3-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="ee5c3-113">Viene descritto come l'operatore <xref:System.Linq.Enumerable.Sum%2A> restituisca `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) anziché 0 per una sequenza vuota o che contiene solo valori null.</span><span class="sxs-lookup"><span data-stu-id="ee5c3-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee5c3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee5c3-114">See Also</span></span>  
 [<span data-ttu-id="ee5c3-115">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="ee5c3-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
