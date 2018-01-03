---
title: 'Procedura: inviare modifiche al database'
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
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 69ada8afe783ce8cc425a5804eab6a00475871c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="2115f-102">Procedura: inviare modifiche al database</span><span class="sxs-lookup"><span data-stu-id="2115f-102">How to: Submit Changes to the Database</span></span>
<span data-ttu-id="2115f-103">Indipendentemente da quante modifiche si apportano agli oggetti, queste vengono applicate solo alle repliche in memoria.</span><span class="sxs-lookup"><span data-stu-id="2115f-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="2115f-104">Le modifiche non vengono apportate ai dati effettivi nel database</span><span class="sxs-lookup"><span data-stu-id="2115f-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="2115f-105">e non saranno trasmesse al server finché non si chiama in modo esplicito <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="2115f-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="2115f-106">Quando si effettua questa chiamata, <xref:System.Data.Linq.DataContext> tenta di convertire le modifiche in comandi SQL equivalenti.</span><span class="sxs-lookup"><span data-stu-id="2115f-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="2115f-107">È possibile utilizzare la logica personalizzata per eseguire l'override di queste azioni, ma l'ordine di invio viene gestito da un servizio del <xref:System.Data.Linq.DataContext> noti come il *processore delle modifiche*.</span><span class="sxs-lookup"><span data-stu-id="2115f-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="2115f-108">Di seguito viene riportata la sequenza degli eventi:</span><span class="sxs-lookup"><span data-stu-id="2115f-108">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="2115f-109">Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esamina il set di oggetti conosciuti per determinare se a tali oggetti sono state associate nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="2115f-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="2115f-110">In caso affermativo, queste nuove istanze vengono aggiunte al set di oggetti registrati.</span><span class="sxs-lookup"><span data-stu-id="2115f-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2.  <span data-ttu-id="2115f-111">Tutti gli oggetti con modifiche in sospeso vengono ordinati in una sequenza di oggetti in base alle reciproche dipendenze.</span><span class="sxs-lookup"><span data-stu-id="2115f-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="2115f-112">Gli oggetti le cui modifiche dipendono da altri oggetti vengono ordinati in sequenza dopo le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="2115f-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3.  <span data-ttu-id="2115f-113">Immediatamente prima della trasmissione di una qualsiasi modifica effettiva, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione per incapsulare la serie di singoli comandi.</span><span class="sxs-lookup"><span data-stu-id="2115f-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4.  <span data-ttu-id="2115f-114">Le modifiche agli oggetti vengono convertite una alla volta in comandi SQL e inviate al server.</span><span class="sxs-lookup"><span data-stu-id="2115f-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="2115f-115">Qualsiasi errore rilevato dal database in questa fase causa l'interruzione del processo di invio e la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2115f-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="2115f-116">Viene eseguito il rollback di tutte le modifiche al database come se non fosse mai stato eseguito alcun invio.</span><span class="sxs-lookup"><span data-stu-id="2115f-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="2115f-117">In <xref:System.Data.Linq.DataContext> è tuttavia ancora presente una registrazione completa di tutte le modifiche,</span><span class="sxs-lookup"><span data-stu-id="2115f-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="2115f-118">pertanto è possibile tentare di correggere il problema e chiamare nuovamente <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, come nell'esempio di codice che segue.</span><span class="sxs-lookup"><span data-stu-id="2115f-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2115f-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2115f-119">Example</span></span>  
 <span data-ttu-id="2115f-120">Quando la transazione relativa alla sottomissione viene completata correttamente, <xref:System.Data.Linq.DataContext> accetta le modifiche agli oggetti ignorando le informazioni di rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="2115f-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2115f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2115f-121">See Also</span></span>  
 [<span data-ttu-id="2115f-122">Procedura: rilevare e risolvere gli invii in conflitto</span><span class="sxs-lookup"><span data-stu-id="2115f-122">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 [<span data-ttu-id="2115f-123">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="2115f-123">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="2115f-124">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="2115f-124">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="2115f-125">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="2115f-125">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
