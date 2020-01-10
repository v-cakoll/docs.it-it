---
title: Eventi ETW di contesa-.NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: 98fc2adcaebe4c9646ab9960f796982681a9015a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716130"
---
# <a name="contention-etw-events"></a><span data-ttu-id="261be-102">Eventi ETW di contesa</span><span class="sxs-lookup"><span data-stu-id="261be-102">Contention ETW events</span></span>

<span data-ttu-id="261be-103">Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativi usati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="261be-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="261be-104">Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.</span><span class="sxs-lookup"><span data-stu-id="261be-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="261be-105">La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi.</span><span class="sxs-lookup"><span data-stu-id="261be-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="261be-106">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="261be-106">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="261be-107">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="261be-107">Keyword for raising the event</span></span>|<span data-ttu-id="261be-108">Livello</span><span class="sxs-lookup"><span data-stu-id="261be-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="261be-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="261be-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="261be-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="261be-110">Informational (4)</span></span>|

<span data-ttu-id="261be-111">Nella tabella seguente vengono illustrate le informazioni sugli eventi:</span><span class="sxs-lookup"><span data-stu-id="261be-111">The following table shows event information:</span></span>

|<span data-ttu-id="261be-112">Event</span><span class="sxs-lookup"><span data-stu-id="261be-112">Event</span></span>|<span data-ttu-id="261be-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="261be-113">Event ID</span></span>|<span data-ttu-id="261be-114">Generato quando</span><span class="sxs-lookup"><span data-stu-id="261be-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="261be-115">81</span><span class="sxs-lookup"><span data-stu-id="261be-115">81</span></span>|<span data-ttu-id="261be-116">Inizio del conflitto.</span><span class="sxs-lookup"><span data-stu-id="261be-116">Contention starts.</span></span> <span data-ttu-id="261be-117">Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.</span><span class="sxs-lookup"><span data-stu-id="261be-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="261be-118">91</span><span class="sxs-lookup"><span data-stu-id="261be-118">91</span></span>|<span data-ttu-id="261be-119">Fine del conflitto.</span><span class="sxs-lookup"><span data-stu-id="261be-119">Contention ends.</span></span>|

<span data-ttu-id="261be-120">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="261be-120">The following table shows event data:</span></span>

|<span data-ttu-id="261be-121">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="261be-121">Field name</span></span>|<span data-ttu-id="261be-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="261be-122">Data type</span></span>|<span data-ttu-id="261be-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="261be-123">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="261be-124">Flag</span><span class="sxs-lookup"><span data-stu-id="261be-124">Flags</span></span>|<span data-ttu-id="261be-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="261be-125">win:UInt8</span></span>|<span data-ttu-id="261be-126">0 per gestito, 1 per nativo.</span><span class="sxs-lookup"><span data-stu-id="261be-126">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="261be-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="261be-127">ClrInstanceID</span></span>|<span data-ttu-id="261be-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="261be-128">win:UInt16</span></span>|<span data-ttu-id="261be-129">ID univoco per l'istanza di CLR.</span><span class="sxs-lookup"><span data-stu-id="261be-129">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="261be-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="261be-130">See also</span></span>

- [<span data-ttu-id="261be-131">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="261be-131">CLR ETW Events</span></span>](clr-etw-events.md)
