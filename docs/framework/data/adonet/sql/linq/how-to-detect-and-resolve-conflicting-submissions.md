---
title: 'Procedura: rilevare e risolvere gli invii in conflitto'
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
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8eb2e27ab034d464ba6978d9ddc063e623812619
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="d3bde-102">Procedura: rilevare e risolvere gli invii in conflitto</span><span class="sxs-lookup"><span data-stu-id="d3bde-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="d3bde-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono disponibili molte risorse per rilevare e risolvere i conflitti causati dalle modifiche apportate al database da più utenti.</span><span class="sxs-lookup"><span data-stu-id="d3bde-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="d3bde-104">Per ulteriori informazioni, vedere [procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="d3bde-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3bde-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3bde-105">Example</span></span>  
 <span data-ttu-id="d3bde-106">Nell'esempio seguente un `try` / `catch` blocco che memorizza nella cache un <xref:System.Data.Linq.ChangeConflictException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="d3bde-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="d3bde-107">Le informazioni sull'entità e sul membro per ogni conflitto sono visualizzate nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d3bde-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3bde-108">Per supportare il recupero delle informazioni, è necessario includere la direttiva `using System.Reflection` (`Imports System.Reflection` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d3bde-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="d3bde-109">Per altre informazioni, vedere <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="d3bde-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d3bde-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3bde-110">See Also</span></span>  
 [<span data-ttu-id="d3bde-111">Creazione e invio di modifiche ai dati</span><span class="sxs-lookup"><span data-stu-id="d3bde-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="d3bde-112">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="d3bde-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
