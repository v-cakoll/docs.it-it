---
title: 'Procedura: gestire i conflitti di modifiche'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 87d895c8d5531d091d773e9f2d51b89408169022
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="cc2e7-102">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="cc2e7-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="cc2e7-103">fornisce una raccolta di API che consentono di individuare, valutare e risolvere i conflitti di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc2e7-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cc2e7-104">In This Section</span></span>  
 [<span data-ttu-id="cc2e7-105">Procedura: rilevare e risolvere gli invii in conflitto</span><span class="sxs-lookup"><span data-stu-id="cc2e7-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="cc2e7-106">Viene descritto come rilevare e risolvere i conflitti di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="cc2e7-107">Procedura: specificare quando vengono generate eccezioni di concorrenza</span><span class="sxs-lookup"><span data-stu-id="cc2e7-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="cc2e7-108">Viene descritto come specificare quando è necessario che l'utente venga informato sui conflitti di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="cc2e7-109">Procedura: specificare quali membri sono verificati conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="cc2e7-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="cc2e7-110">Viene descritto come attribuire i membri per specificare se deve essere effettuato il controllo dei conflitti di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="cc2e7-111">Procedura: recuperare informazioni sui conflitti di entità</span><span class="sxs-lookup"><span data-stu-id="cc2e7-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="cc2e7-112">Viene descritto come raccogliere informazioni sui conflitti di entità.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="cc2e7-113">Procedura: recuperare informazioni sui conflitti di membro</span><span class="sxs-lookup"><span data-stu-id="cc2e7-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="cc2e7-114">Viene descritto come raccogliere informazioni sui conflitti tra membri.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="cc2e7-115">Procedura: risolvere i conflitti mantenendo i valori del Database</span><span class="sxs-lookup"><span data-stu-id="cc2e7-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="cc2e7-116">Viene descritto come sovrascrivere i valori correnti con i valori del database.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="cc2e7-117">Procedura: risolvere i conflitti sovrascrivendo i valori del Database</span><span class="sxs-lookup"><span data-stu-id="cc2e7-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="cc2e7-118">Viene descritto come mantenere i valori correnti sovrascrivendo i valori correnti del database.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="cc2e7-119">Procedura: risolvere i conflitti mediante l'unione con i valori del Database</span><span class="sxs-lookup"><span data-stu-id="cc2e7-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="cc2e7-120">Viene descritto come risolvere un conflitto unendo i valori del database e quelli correnti.</span><span class="sxs-lookup"><span data-stu-id="cc2e7-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cc2e7-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cc2e7-121">Related Sections</span></span>  
 [<span data-ttu-id="cc2e7-122">Concorrenza ottimistica: Panoramica</span><span class="sxs-lookup"><span data-stu-id="cc2e7-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="cc2e7-123">Vengono spiegati i termini applicabili alla concorrenza ottimistica in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc2e7-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
