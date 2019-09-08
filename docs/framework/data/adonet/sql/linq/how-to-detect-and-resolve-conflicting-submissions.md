---
title: 'Procedura: Rilevare e risolvere gli invii in conflitto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 2de0182cc0b87768a9cff553b7ec6e77f8ccc7b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793768"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="b8dd4-102">Procedura: Rilevare e risolvere gli invii in conflitto</span><span class="sxs-lookup"><span data-stu-id="b8dd4-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="b8dd4-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono disponibili molte risorse per rilevare e risolvere i conflitti causati dalle modifiche apportate al database da più utenti.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="b8dd4-104">Per altre informazioni, vedere [Procedura: Gestire i conflitti](how-to-manage-change-conflicts.md)di modifica.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8dd4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8dd4-105">Example</span></span>  
 <span data-ttu-id="b8dd4-106">Nell'esempio seguente viene illustrato `try` un / `catch` blocco che rileva un' <xref:System.Data.Linq.ChangeConflictException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="b8dd4-107">Le informazioni sull'entità e sul membro per ogni conflitto sono visualizzate nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8dd4-108">Per supportare il recupero delle informazioni, è necessario includere la direttiva `using System.Reflection` (`Imports System.Reflection` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="b8dd4-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="b8dd4-109">Per altre informazioni, vedere <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b8dd4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8dd4-110">See also</span></span>

- [<span data-ttu-id="b8dd4-111">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="b8dd4-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="b8dd4-112">Procedura: Gestione dei conflitti di modifica</span><span class="sxs-lookup"><span data-stu-id="b8dd4-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
