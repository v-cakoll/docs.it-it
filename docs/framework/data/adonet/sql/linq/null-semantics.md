---
title: Semantica Null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: d0b18c0a699840d11f5e4add05147672f9bb69e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792976"
---
# <a name="null-semantics"></a><span data-ttu-id="2ecf6-102">Semantica Null</span><span class="sxs-lookup"><span data-stu-id="2ecf6-102">Null Semantics</span></span>
<span data-ttu-id="2ecf6-103">Nella tabella seguente vengono forniti i collegamenti a diverse parti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] della documentazione `null` in`Nothing` cui vengono discussi i problemi (in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="2ecf6-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="2ecf6-104">Argomento</span><span class="sxs-lookup"><span data-stu-id="2ecf6-104">Topic</span></span>|<span data-ttu-id="2ecf6-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ecf6-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2ecf6-106">Tipi SQL-CLR non corrispondenti</span><span class="sxs-lookup"><span data-stu-id="2ecf6-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="2ecf6-107">La sezione "semantica null" di questo argomento include una descrizione del valore booleano SQL a tre Stati rispetto al Common Language Runtime a due stati ( <xref:System.Boolean>CLR), `Nothing` al valore letterale `null` (C#Visual Basic) e () e ad altre analoghe problemi.</span><span class="sxs-lookup"><span data-stu-id="2ecf6-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="2ecf6-108">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="2ecf6-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="2ecf6-109">Nella sezione sulla semantica null di questo argomento viene descritta la semantica di confronto null in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecf6-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="2ecf6-110">Metodi System.String</span><span class="sxs-lookup"><span data-stu-id="2ecf6-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="2ecf6-111">Nella sezione sulle differenze rispetto a .NET di questo argomento viene descritto come un risultato 0 restituito da <xref:System.String.LastIndexOf%2A> possa significare che la stringa è null o che la posizione trovata è 0.</span><span class="sxs-lookup"><span data-stu-id="2ecf6-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="2ecf6-112">Calcolare la somma dei valori in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="2ecf6-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="2ecf6-113">Viene descritto il <xref:System.Linq.Enumerable.Sum%2A> modo in cui l' `null` operatore`Nothing` restituisce (in Visual Basic) anziché 0 per una sequenza che contiene solo valori null o per una sequenza vuota.</span><span class="sxs-lookup"><span data-stu-id="2ecf6-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ecf6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ecf6-114">See also</span></span>

- [<span data-ttu-id="2ecf6-115">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="2ecf6-115">Data Types and Functions</span></span>](data-types-and-functions.md)
