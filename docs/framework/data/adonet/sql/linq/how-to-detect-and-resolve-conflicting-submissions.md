---
title: 'Procedura: Rilevare e risolvere gli invii in conflitto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: ff33196f83e2c0d8d759e4ffc3fb7442e8ba0e3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940102"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="45157-102">Procedura: Rilevare e risolvere gli invii in conflitto</span><span class="sxs-lookup"><span data-stu-id="45157-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="45157-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono disponibili molte risorse per rilevare e risolvere i conflitti causati dalle modifiche apportate al database da più utenti.</span><span class="sxs-lookup"><span data-stu-id="45157-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="45157-104">Per altre informazioni, vedere [Procedura: Gestire i conflitti](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)di modifica.</span><span class="sxs-lookup"><span data-stu-id="45157-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45157-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="45157-105">Example</span></span>  
 <span data-ttu-id="45157-106">Nell'esempio seguente viene illustrato `try` un / `catch` blocco che rileva un' <xref:System.Data.Linq.ChangeConflictException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="45157-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="45157-107">Le informazioni sull'entità e sul membro per ogni conflitto sono visualizzate nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="45157-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45157-108">Per supportare il recupero delle informazioni, è necessario includere la direttiva `using System.Reflection` (`Imports System.Reflection` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="45157-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="45157-109">Per altre informazioni, vedere <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="45157-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="45157-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45157-110">See also</span></span>

- [<span data-ttu-id="45157-111">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="45157-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="45157-112">Procedura: Gestione dei conflitti di modifica</span><span class="sxs-lookup"><span data-stu-id="45157-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
