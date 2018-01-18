---
title: 'Procedura: specificare quando vengono generate eccezioni di concorrenza'
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
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a1c7a9c7e8d6429b31f1810e31123d46a179fa4e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="867d6-102">Procedura: specificare quando vengono generate eccezioni di concorrenza</span><span class="sxs-lookup"><span data-stu-id="867d6-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="867d6-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] un'eccezione <xref:System.Data.Linq.ChangeConflictException> viene generata quando gli oggetti non vengono aggiornati a causa di conflitti di concorrenza ottimistici.</span><span class="sxs-lookup"><span data-stu-id="867d6-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="867d6-104">Per ulteriori informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="867d6-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="867d6-105">Prima di inviare le modifiche al database, è possibile specificare quando dovranno essere generate le eccezioni di concorrenza:</span><span class="sxs-lookup"><span data-stu-id="867d6-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
-   <span data-ttu-id="867d6-106">Generare l'eccezione al primo errore (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="867d6-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
-   <span data-ttu-id="867d6-107">Completare tutti i tentativi di aggiornamento, accumulare tutti gli errori e segnalare gli errori accumulati nell'eccezione (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="867d6-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="867d6-108">Quando viene generata, l'eccezione <xref:System.Data.Linq.ChangeConflictException> fornisce l'accesso a una raccolta <xref:System.Data.Linq.ChangeConflictCollection>.</span><span class="sxs-lookup"><span data-stu-id="867d6-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="867d6-109">In questa raccolta vengono forniti i dettagli per ogni conflitto (associato a un unico tentativo di aggiornamento non riuscito), nonché l'accesso alla raccolta <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.</span><span class="sxs-lookup"><span data-stu-id="867d6-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="867d6-110">Per ogni conflitto fra membri viene eseguito il mapping a un unico membro nell'aggiornamento che non ha superato il controllo della concorrenza.</span><span class="sxs-lookup"><span data-stu-id="867d6-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="867d6-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="867d6-111">Example</span></span>  
 <span data-ttu-id="867d6-112">Nel codice riportato di seguito vengono illustrati esempi di entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="867d6-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="867d6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="867d6-113">See Also</span></span>  
 [<span data-ttu-id="867d6-114">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="867d6-114">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="867d6-115">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="867d6-115">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
