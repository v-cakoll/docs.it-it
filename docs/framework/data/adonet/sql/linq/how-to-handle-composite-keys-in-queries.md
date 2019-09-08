---
title: 'Procedura: Gestire le chiavi composite nelle query'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: a6c6e7d1c1d29a049b50f4ea9d70ef5cd9e89a44
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793576"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="ad564-102">Procedura: Gestire le chiavi composite nelle query</span><span class="sxs-lookup"><span data-stu-id="ad564-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="ad564-103">Alcuni operatori possono accettare un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="ad564-103">Some operators can take only one argument.</span></span> <span data-ttu-id="ad564-104">Se l'argomento deve includere più di una colonna del database, è necessario creare un tipo anonimo per rappresentare la combinazione.</span><span class="sxs-lookup"><span data-stu-id="ad564-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad564-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad564-105">Example</span></span>  
 <span data-ttu-id="ad564-106">Nell'esempio seguente viene illustrata una query che richiama l'operatore `GroupBy` che può accettare un solo argomento `key`.</span><span class="sxs-lookup"><span data-stu-id="ad564-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="ad564-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad564-107">Example</span></span>  
 <span data-ttu-id="ad564-108">La stessa situazione è applicabile ai join, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ad564-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ad564-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad564-109">See also</span></span>

- [<span data-ttu-id="ad564-110">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="ad564-110">Query Concepts</span></span>](query-concepts.md)
