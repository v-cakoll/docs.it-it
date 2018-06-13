---
title: Eventi ETW di conflitto
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3487b67ea49cecfd0da2b5b3f993ea54d562145d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397520"
---
# <a name="contention-etw-events"></a><span data-ttu-id="8cc2c-102">Eventi ETW di conflitto</span><span class="sxs-lookup"><span data-stu-id="8cc2c-102">Contention ETW Events</span></span>
<span data-ttu-id="8cc2c-103">Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativi usati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="8cc2c-104">Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>  
  
 <span data-ttu-id="8cc2c-105">La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="8cc2c-106">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8cc2c-106">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="8cc2c-107">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="8cc2c-107">Keyword for raising the event</span></span>|<span data-ttu-id="8cc2c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8cc2c-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8cc2c-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="8cc2c-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="8cc2c-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8cc2c-110">Informational (4)</span></span>|  
  
 <span data-ttu-id="8cc2c-111">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-111">The following table shows event information.</span></span>  
  
|<span data-ttu-id="8cc2c-112">event</span><span class="sxs-lookup"><span data-stu-id="8cc2c-112">Event</span></span>|<span data-ttu-id="8cc2c-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="8cc2c-113">Event ID</span></span>|<span data-ttu-id="8cc2c-114">Generato quando</span><span class="sxs-lookup"><span data-stu-id="8cc2c-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|<span data-ttu-id="8cc2c-115">81</span><span class="sxs-lookup"><span data-stu-id="8cc2c-115">81</span></span>|<span data-ttu-id="8cc2c-116">Inizio del conflitto.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-116">Contention starts.</span></span> <span data-ttu-id="8cc2c-117">Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|  
|`ContentionStop`|<span data-ttu-id="8cc2c-118">81</span><span class="sxs-lookup"><span data-stu-id="8cc2c-118">81</span></span>|<span data-ttu-id="8cc2c-119">Fine del conflitto.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-119">Contention ends.</span></span>|  
  
 <span data-ttu-id="8cc2c-120">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-120">The following table shows event data.</span></span>  
  
|<span data-ttu-id="8cc2c-121">Nome campo</span><span class="sxs-lookup"><span data-stu-id="8cc2c-121">Field name</span></span>|<span data-ttu-id="8cc2c-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8cc2c-122">Data type</span></span>|<span data-ttu-id="8cc2c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cc2c-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8cc2c-124">Flag</span><span class="sxs-lookup"><span data-stu-id="8cc2c-124">Flags</span></span>|<span data-ttu-id="8cc2c-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="8cc2c-125">win:UInt8</span></span>|<span data-ttu-id="8cc2c-126">0 per gestito, 1 per nativo.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-126">0 for managed; 1 for native.</span></span>|  
|<span data-ttu-id="8cc2c-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8cc2c-127">ClrInstanceID</span></span>|<span data-ttu-id="8cc2c-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8cc2c-128">win:UInt16</span></span>|<span data-ttu-id="8cc2c-129">ID univoco per l'istanza di CLR.</span><span class="sxs-lookup"><span data-stu-id="8cc2c-129">Unique ID for the instance of CLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc2c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cc2c-130">See Also</span></span>  
 [<span data-ttu-id="8cc2c-131">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="8cc2c-131">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
