---
title: 'Procedura: risolvere i conflitti mediante l''unione con valori di database'
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
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8e5114052951950c5866d80c974555678b1d040a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="48d41-102">Procedura: risolvere i conflitti mediante l'unione con valori di database</span><span class="sxs-lookup"><span data-stu-id="48d41-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="48d41-103">Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.KeepChanges> per unire i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="48d41-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="48d41-104">Per ulteriori informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48d41-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48d41-105">In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database.</span><span class="sxs-lookup"><span data-stu-id="48d41-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="48d41-106">Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="48d41-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48d41-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="48d41-107">Example</span></span>  
 <span data-ttu-id="48d41-108">In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department.</span><span class="sxs-lookup"><span data-stu-id="48d41-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="48d41-109">Nella tabella seguente è illustrata questa situazione.</span><span class="sxs-lookup"><span data-stu-id="48d41-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="48d41-110">Manager</span><span class="sxs-lookup"><span data-stu-id="48d41-110">Manager</span></span>|<span data-ttu-id="48d41-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="48d41-111">Assistant</span></span>|<span data-ttu-id="48d41-112">Department</span><span class="sxs-lookup"><span data-stu-id="48d41-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="48d41-113">Stato del database originale quando viene eseguita una query da User1 e User2.</span><span class="sxs-lookup"><span data-stu-id="48d41-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="48d41-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="48d41-114">Alfreds</span></span>|<span data-ttu-id="48d41-115">Maria</span><span class="sxs-lookup"><span data-stu-id="48d41-115">Maria</span></span>|<span data-ttu-id="48d41-116">Sales</span><span class="sxs-lookup"><span data-stu-id="48d41-116">Sales</span></span>|  
|<span data-ttu-id="48d41-117">User1 si prepara a inviare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="48d41-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="48d41-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="48d41-118">Alfred</span></span>||<span data-ttu-id="48d41-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="48d41-119">Marketing</span></span>|  
|<span data-ttu-id="48d41-120">User2 ha già inviato queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="48d41-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="48d41-121">Mary</span><span class="sxs-lookup"><span data-stu-id="48d41-121">Mary</span></span>|<span data-ttu-id="48d41-122">Servizio</span><span class="sxs-lookup"><span data-stu-id="48d41-122">Service</span></span>|  
  
 <span data-ttu-id="48d41-123">User1 decide di risolvere questo conflitto unendo i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="48d41-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="48d41-124">Di conseguenza, i valori del database verranno sovrascritti solo quando il set di modifiche corrente avrà modificato anche quel valore.</span><span class="sxs-lookup"><span data-stu-id="48d41-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="48d41-125">Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.KeepChanges>, il risultato nel database sarà come nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="48d41-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="48d41-126">Manager</span><span class="sxs-lookup"><span data-stu-id="48d41-126">Manager</span></span>|<span data-ttu-id="48d41-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="48d41-127">Assistant</span></span>|<span data-ttu-id="48d41-128">Department</span><span class="sxs-lookup"><span data-stu-id="48d41-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="48d41-129">Nuovo stato dopo la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="48d41-129">New state after conflict resolution.</span></span>|<span data-ttu-id="48d41-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="48d41-130">Alfred</span></span><br /><br /> <span data-ttu-id="48d41-131">(da User1)</span><span class="sxs-lookup"><span data-stu-id="48d41-131">(from User1)</span></span>|<span data-ttu-id="48d41-132">Mary</span><span class="sxs-lookup"><span data-stu-id="48d41-132">Mary</span></span><br /><br /> <span data-ttu-id="48d41-133">(da User2)</span><span class="sxs-lookup"><span data-stu-id="48d41-133">(from User2)</span></span>|<span data-ttu-id="48d41-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="48d41-134">Marketing</span></span><br /><br /> <span data-ttu-id="48d41-135">(da User1)</span><span class="sxs-lookup"><span data-stu-id="48d41-135">(from User1)</span></span>|  
  
 <span data-ttu-id="48d41-136">Nell'esempio seguente viene illustrato come unire i valori del database con i valori del membro client corrente, a meno che il client non abbia modificato anche quel valore.</span><span class="sxs-lookup"><span data-stu-id="48d41-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="48d41-137">Non si verifica alcun conflitto di ispezione o gestione personalizzata dei singoli membri.</span><span class="sxs-lookup"><span data-stu-id="48d41-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="48d41-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48d41-138">See Also</span></span>  
 [<span data-ttu-id="48d41-139">Procedura: risolvere i conflitti sovrascrivendo i valori del Database</span><span class="sxs-lookup"><span data-stu-id="48d41-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="48d41-140">Procedura: risolvere i conflitti mantenendo i valori del Database</span><span class="sxs-lookup"><span data-stu-id="48d41-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="48d41-141">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="48d41-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
