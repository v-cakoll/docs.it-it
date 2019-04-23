---
title: 'Procedura: Risolvere conflitti sovrascrivendo i valori di database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 7b8d7cf8ab2335c064062ed3ab4072d81e8042fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189118"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="83aca-102">Procedura: Risolvere conflitti sovrascrivendo i valori di database</span><span class="sxs-lookup"><span data-stu-id="83aca-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="83aca-103">Per risolvere le differenze tra i valori del database previsti ed effettivi prima del tentativo di inviare di nuovo le modifiche, è possibile usare <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> per sovrascrivere i valori del database.</span><span class="sxs-lookup"><span data-stu-id="83aca-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="83aca-104">Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="83aca-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83aca-105">In tutti i casi, viene innanzitutto aggiornato il record sul client recuperando i dati aggiornati dal database.</span><span class="sxs-lookup"><span data-stu-id="83aca-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="83aca-106">Questa azione assicura che il successivo tentativo di aggiornamento non avrà esito negativo durante gli stessi controlli di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="83aca-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83aca-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="83aca-107">Example</span></span>  
 <span data-ttu-id="83aca-108">In questo scenario viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando User1 tenta di inviare le modifiche, in quanto nel frattempo User2 ha modificato le colonne Assistant e Department.</span><span class="sxs-lookup"><span data-stu-id="83aca-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="83aca-109">Nella tabella seguente è illustrata questa situazione.</span><span class="sxs-lookup"><span data-stu-id="83aca-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="83aca-110">Manager</span><span class="sxs-lookup"><span data-stu-id="83aca-110">Manager</span></span>|<span data-ttu-id="83aca-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="83aca-111">Assistant</span></span>|<span data-ttu-id="83aca-112">Department</span><span class="sxs-lookup"><span data-stu-id="83aca-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="83aca-113">Stato del database originale quando viene eseguita una query da User1 e User2.</span><span class="sxs-lookup"><span data-stu-id="83aca-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="83aca-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="83aca-114">Alfreds</span></span>|<span data-ttu-id="83aca-115">Maria</span><span class="sxs-lookup"><span data-stu-id="83aca-115">Maria</span></span>|<span data-ttu-id="83aca-116">Sales</span><span class="sxs-lookup"><span data-stu-id="83aca-116">Sales</span></span>|  
|<span data-ttu-id="83aca-117">User1 si prepara a inviare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="83aca-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="83aca-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="83aca-118">Alfred</span></span>||<span data-ttu-id="83aca-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="83aca-119">Marketing</span></span>|  
|<span data-ttu-id="83aca-120">User2 ha già inviato queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="83aca-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="83aca-121">Mary</span><span class="sxs-lookup"><span data-stu-id="83aca-121">Mary</span></span>|<span data-ttu-id="83aca-122">Service</span><span class="sxs-lookup"><span data-stu-id="83aca-122">Service</span></span>|  
  
 <span data-ttu-id="83aca-123">User1 decide di risolvere questo conflitto sovrascrivendo i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="83aca-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="83aca-124">Quando User1 risolve il conflitto usando <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, il risultato nel database sarà come nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="83aca-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="83aca-125">Manager</span><span class="sxs-lookup"><span data-stu-id="83aca-125">Manager</span></span>|<span data-ttu-id="83aca-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="83aca-126">Assistant</span></span>|<span data-ttu-id="83aca-127">Department</span><span class="sxs-lookup"><span data-stu-id="83aca-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="83aca-128">Nuovo stato dopo la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="83aca-128">New state after conflict resolution.</span></span>|<span data-ttu-id="83aca-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="83aca-129">Alfred</span></span><br /><br /> <span data-ttu-id="83aca-130">(da User1)</span><span class="sxs-lookup"><span data-stu-id="83aca-130">(from User1)</span></span>|<span data-ttu-id="83aca-131">Maria</span><span class="sxs-lookup"><span data-stu-id="83aca-131">Maria</span></span><br /><br /> <span data-ttu-id="83aca-132">(originale)</span><span class="sxs-lookup"><span data-stu-id="83aca-132">(original)</span></span>|<span data-ttu-id="83aca-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="83aca-133">Marketing</span></span><br /><br /> <span data-ttu-id="83aca-134">(da User1)</span><span class="sxs-lookup"><span data-stu-id="83aca-134">(from User1)</span></span>|  
  
 <span data-ttu-id="83aca-135">Nel codice di esempio seguente viene illustrato come sovrascrivere i valori del database con i valori del membro client corrente.</span><span class="sxs-lookup"><span data-stu-id="83aca-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="83aca-136">Non si verificano conflitti di ispezione o gestione personalizzata dei singoli membri.</span><span class="sxs-lookup"><span data-stu-id="83aca-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="83aca-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83aca-137">See also</span></span>

- [<span data-ttu-id="83aca-138">Procedura: Gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="83aca-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
