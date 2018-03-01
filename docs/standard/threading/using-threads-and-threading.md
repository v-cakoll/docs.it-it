---
title: Utilizzo di thread e threading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="98858-102">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="98858-102">Using Threads and Threading</span></span>
<span data-ttu-id="98858-103">In questa sezione vengono trattati argomenti quali la creazione e la gestione dei thread gestiti, come passare dati ai thread gestiti e ottenere risultati e come eliminare i thread e gestire un'eccezione <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="98858-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98858-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="98858-104">In This Section</span></span>  
 [<span data-ttu-id="98858-105">Creazione di thread e passaggio di dati all'avvio</span><span class="sxs-lookup"><span data-stu-id="98858-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="98858-106">Viene descritta e illustrata la creazione di thread gestiti, incluso come passare dati ai nuovi thread e come ottenere dati.</span><span class="sxs-lookup"><span data-stu-id="98858-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="98858-107">Sospensione e ripresa di thread</span><span class="sxs-lookup"><span data-stu-id="98858-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="98858-108">Vengono discusse le implicazioni della sospensione e ripresa dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="98858-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="98858-109">Eliminazione definitiva di thread</span><span class="sxs-lookup"><span data-stu-id="98858-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="98858-110">Illustra le conseguenze dell'eliminazione definitiva di thread gestiti e come gestire un'eccezione <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="98858-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="98858-111">Pianificazione di thread</span><span class="sxs-lookup"><span data-stu-id="98858-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="98858-112">Vengono illustrate le priorità dei thread e gli effetti delle priorità sulla pianificazione dei thread.</span><span class="sxs-lookup"><span data-stu-id="98858-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="98858-113">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="98858-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="98858-114">Rende disponibile la documentazione di riferimento per la classe <xref:System.Threading.Thread>, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="98858-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="98858-115">Rende disponibile la documentazione di riferimento per il delegato <xref:System.Threading.ThreadStart> che rappresenta le routine di thread senza parametri.</span><span class="sxs-lookup"><span data-stu-id="98858-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="98858-116">Fornisce un modo semplice per passare dati a una routine di thread, sebbene senza tipizzazione forte.</span><span class="sxs-lookup"><span data-stu-id="98858-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="98858-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="98858-117">Related Sections</span></span>  
 <span data-ttu-id="98858-118">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md) (Thread e threading)</span><span class="sxs-lookup"><span data-stu-id="98858-118">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)</span></span>  
 <span data-ttu-id="98858-119">Fornisce un'introduzione al threading gestito.</span><span class="sxs-lookup"><span data-stu-id="98858-119">Provides an introduction to managed threading.</span></span>
