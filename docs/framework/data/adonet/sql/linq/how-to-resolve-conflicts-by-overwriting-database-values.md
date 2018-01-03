---
title: 'Procedura: risolvere i conflitti sovrascrivendo i valori di database'
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
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f3155eca2344e32913aaacbd0e2671603824aaf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="ecd05-102">Procedura: risolvere i conflitti sovrascrivendo i valori di database</span><span class="sxs-lookup"><span data-stu-id="ecd05-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="ecd05-103">Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> per sovrascrivere i valori del database.</span><span class="sxs-lookup"><span data-stu-id="ecd05-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="ecd05-104">Per ulteriori informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ecd05-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecd05-105">In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database.</span><span class="sxs-lookup"><span data-stu-id="ecd05-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="ecd05-106">Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="ecd05-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecd05-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecd05-107">Example</span></span>  
 <span data-ttu-id="ecd05-108">In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department.</span><span class="sxs-lookup"><span data-stu-id="ecd05-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="ecd05-109">Nella tabella seguente è illustrata questa situazione.</span><span class="sxs-lookup"><span data-stu-id="ecd05-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="ecd05-110">Manager</span><span class="sxs-lookup"><span data-stu-id="ecd05-110">Manager</span></span>|<span data-ttu-id="ecd05-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="ecd05-111">Assistant</span></span>|<span data-ttu-id="ecd05-112">Department</span><span class="sxs-lookup"><span data-stu-id="ecd05-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="ecd05-113">Stato del database originale quando viene eseguita una query da User1 e User2.</span><span class="sxs-lookup"><span data-stu-id="ecd05-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="ecd05-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="ecd05-114">Alfreds</span></span>|<span data-ttu-id="ecd05-115">Maria</span><span class="sxs-lookup"><span data-stu-id="ecd05-115">Maria</span></span>|<span data-ttu-id="ecd05-116">Sales</span><span class="sxs-lookup"><span data-stu-id="ecd05-116">Sales</span></span>|  
|<span data-ttu-id="ecd05-117">User1 si prepara a inviare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="ecd05-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="ecd05-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="ecd05-118">Alfred</span></span>||<span data-ttu-id="ecd05-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="ecd05-119">Marketing</span></span>|  
|<span data-ttu-id="ecd05-120">User2 ha già inviato queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="ecd05-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="ecd05-121">Mary</span><span class="sxs-lookup"><span data-stu-id="ecd05-121">Mary</span></span>|<span data-ttu-id="ecd05-122">Servizio</span><span class="sxs-lookup"><span data-stu-id="ecd05-122">Service</span></span>|  
  
 <span data-ttu-id="ecd05-123">User1 decide di risolvere questo conflitto sovrascrivendo i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="ecd05-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="ecd05-124">Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, il risultato nel database sarà come nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ecd05-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="ecd05-125">Manager</span><span class="sxs-lookup"><span data-stu-id="ecd05-125">Manager</span></span>|<span data-ttu-id="ecd05-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="ecd05-126">Assistant</span></span>|<span data-ttu-id="ecd05-127">Department</span><span class="sxs-lookup"><span data-stu-id="ecd05-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="ecd05-128">Nuovo stato dopo la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="ecd05-128">New state after conflict resolution.</span></span>|<span data-ttu-id="ecd05-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="ecd05-129">Alfred</span></span><br /><br /> <span data-ttu-id="ecd05-130">(da User1)</span><span class="sxs-lookup"><span data-stu-id="ecd05-130">(from User1)</span></span>|<span data-ttu-id="ecd05-131">Maria</span><span class="sxs-lookup"><span data-stu-id="ecd05-131">Maria</span></span><br /><br /> <span data-ttu-id="ecd05-132">(originale)</span><span class="sxs-lookup"><span data-stu-id="ecd05-132">(original)</span></span>|<span data-ttu-id="ecd05-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="ecd05-133">Marketing</span></span><br /><br /> <span data-ttu-id="ecd05-134">(da User1)</span><span class="sxs-lookup"><span data-stu-id="ecd05-134">(from User1)</span></span>|  
  
 <span data-ttu-id="ecd05-135">Nel codice di esempio seguente viene illustrato come sovrascrivere i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="ecd05-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="ecd05-136">Non si verificano conflitti di ispezione o gestione personalizzata dei singoli membri.</span><span class="sxs-lookup"><span data-stu-id="ecd05-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ecd05-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecd05-137">See Also</span></span>  
 [<span data-ttu-id="ecd05-138">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="ecd05-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
