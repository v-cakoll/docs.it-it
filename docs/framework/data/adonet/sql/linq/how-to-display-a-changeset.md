---
title: 'Procedura: visualizzare un insieme di modifiche'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 19f0198103999da687e07f472cd5a480406830cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="1a5cf-102">Procedura: visualizzare un insieme di modifiche</span><span class="sxs-lookup"><span data-stu-id="1a5cf-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="1a5cf-103">È possibile visualizzare modifiche registrate da <xref:System.Data.Linq.DataContext> usando <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a5cf-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a5cf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a5cf-104">Example</span></span>  
 <span data-ttu-id="1a5cf-105">Nell'esempio seguente vengono recuperati i clienti la cui città di residenza è London, la città viene modificata in Paris, quindi le modifiche vengono inviate di nuovo al database.</span><span class="sxs-lookup"><span data-stu-id="1a5cf-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="1a5cf-106">L'output generato da questo codice è analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5cf-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="1a5cf-107">Notare che il riepilogo alla fine dell'output indica che sono state apportate otto modifiche.</span><span class="sxs-lookup"><span data-stu-id="1a5cf-107">Note that the summary at the end shows that eight changes were made.</span></span>  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## <a name="see-also"></a><span data-ttu-id="1a5cf-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a5cf-108">See Also</span></span>  
 [<span data-ttu-id="1a5cf-109">Supporto del debug</span><span class="sxs-lookup"><span data-stu-id="1a5cf-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
