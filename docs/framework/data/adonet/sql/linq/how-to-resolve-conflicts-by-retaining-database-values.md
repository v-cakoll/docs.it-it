---
title: 'Procedura: Risolvere conflitti mantenendo i valori di database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: 8440ffe61e254403357970d771aea207a6eb6092
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230109"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="3ef3d-102">Procedura: Risolvere conflitti mantenendo i valori di database</span><span class="sxs-lookup"><span data-stu-id="3ef3d-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="3ef3d-103">Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> per conservare i valori trovati nel database.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="3ef3d-104">I valori correnti nel modello a oggetti vengono quindi sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="3ef3d-105">Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ef3d-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ef3d-106">In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="3ef3d-107">Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ef3d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ef3d-108">Example</span></span>  
 <span data-ttu-id="3ef3d-109">In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="3ef3d-110">Nella tabella seguente è illustrata questa situazione.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="3ef3d-111">Manager</span><span class="sxs-lookup"><span data-stu-id="3ef3d-111">Manager</span></span>|<span data-ttu-id="3ef3d-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="3ef3d-112">Assistant</span></span>|<span data-ttu-id="3ef3d-113">Department</span><span class="sxs-lookup"><span data-stu-id="3ef3d-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="3ef3d-114">Stato del database originale quando viene eseguita una query da User1 e User2.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="3ef3d-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="3ef3d-115">Alfreds</span></span>|<span data-ttu-id="3ef3d-116">Maria</span><span class="sxs-lookup"><span data-stu-id="3ef3d-116">Maria</span></span>|<span data-ttu-id="3ef3d-117">Sales</span><span class="sxs-lookup"><span data-stu-id="3ef3d-117">Sales</span></span>|  
|<span data-ttu-id="3ef3d-118">User1 si prepara a inviare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="3ef3d-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="3ef3d-119">Alfred</span></span>||<span data-ttu-id="3ef3d-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="3ef3d-120">Marketing</span></span>|  
|<span data-ttu-id="3ef3d-121">User2 ha già inviato queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="3ef3d-122">Mary</span><span class="sxs-lookup"><span data-stu-id="3ef3d-122">Mary</span></span>|<span data-ttu-id="3ef3d-123">Service</span><span class="sxs-lookup"><span data-stu-id="3ef3d-123">Service</span></span>|  
  
 <span data-ttu-id="3ef3d-124">User1 decide di risolvere questo conflitto sovrascrivendo i valori correnti nel modello a oggetti con i valori del database più recenti.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="3ef3d-125">Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, il risultato nel database sarà come nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="3ef3d-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="3ef3d-126">Manager</span><span class="sxs-lookup"><span data-stu-id="3ef3d-126">Manager</span></span>|<span data-ttu-id="3ef3d-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="3ef3d-127">Assistant</span></span>|<span data-ttu-id="3ef3d-128">Department</span><span class="sxs-lookup"><span data-stu-id="3ef3d-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="3ef3d-129">Nuovo stato dopo la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-129">New state after conflict resolution.</span></span>|<span data-ttu-id="3ef3d-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="3ef3d-130">Alfreds</span></span><br /><br /> <span data-ttu-id="3ef3d-131">(originale)</span><span class="sxs-lookup"><span data-stu-id="3ef3d-131">(original)</span></span>|<span data-ttu-id="3ef3d-132">Mary</span><span class="sxs-lookup"><span data-stu-id="3ef3d-132">Mary</span></span><br /><br /> <span data-ttu-id="3ef3d-133">(da User2)</span><span class="sxs-lookup"><span data-stu-id="3ef3d-133">(from User2)</span></span>|<span data-ttu-id="3ef3d-134">Service</span><span class="sxs-lookup"><span data-stu-id="3ef3d-134">Service</span></span><br /><br /> <span data-ttu-id="3ef3d-135">(da User2)</span><span class="sxs-lookup"><span data-stu-id="3ef3d-135">(from User2)</span></span>|  
  
 <span data-ttu-id="3ef3d-136">Nel codice di esempio seguente viene illustrato come sovrascrivere i valori correnti nel modello a oggetti con i valori del database.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="3ef3d-137">Non si verificano conflitti di ispezione o gestione personalizzata dei singoli membri.</span><span class="sxs-lookup"><span data-stu-id="3ef3d-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3ef3d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef3d-138">See also</span></span>

- [<span data-ttu-id="3ef3d-139">Procedura: Gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="3ef3d-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
