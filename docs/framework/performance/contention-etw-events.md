---
title: Eventi ETW di contesa-.NET
description: Ottenere informazioni dettagliate sugli eventi ETW di contesa, che vengono generati ogni volta che è presente una contesa per System. Threading. monitorare i blocchi o i blocchi nativi usati dal runtime.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309599"
---
# <a name="contention-etw-events"></a><span data-ttu-id="deacf-103">Eventi ETW di contesa</span><span class="sxs-lookup"><span data-stu-id="deacf-103">Contention ETW events</span></span>

<span data-ttu-id="deacf-104">Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativi usati dal runtime.</span><span class="sxs-lookup"><span data-stu-id="deacf-104">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="deacf-105">Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.</span><span class="sxs-lookup"><span data-stu-id="deacf-105">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="deacf-106">La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi.</span><span class="sxs-lookup"><span data-stu-id="deacf-106">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="deacf-107">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="deacf-107">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="deacf-108">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="deacf-108">Keyword for raising the event</span></span>|<span data-ttu-id="deacf-109">Livello</span><span class="sxs-lookup"><span data-stu-id="deacf-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="deacf-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="deacf-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="deacf-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="deacf-111">Informational (4)</span></span>|

<span data-ttu-id="deacf-112">Nella tabella seguente vengono illustrate le informazioni sugli eventi:</span><span class="sxs-lookup"><span data-stu-id="deacf-112">The following table shows event information:</span></span>

|<span data-ttu-id="deacf-113">Evento</span><span class="sxs-lookup"><span data-stu-id="deacf-113">Event</span></span>|<span data-ttu-id="deacf-114">ID evento</span><span class="sxs-lookup"><span data-stu-id="deacf-114">Event ID</span></span>|<span data-ttu-id="deacf-115">Generato quando</span><span class="sxs-lookup"><span data-stu-id="deacf-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="deacf-116">81</span><span class="sxs-lookup"><span data-stu-id="deacf-116">81</span></span>|<span data-ttu-id="deacf-117">Inizio del conflitto.</span><span class="sxs-lookup"><span data-stu-id="deacf-117">Contention starts.</span></span> <span data-ttu-id="deacf-118">Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.</span><span class="sxs-lookup"><span data-stu-id="deacf-118">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="deacf-119">91</span><span class="sxs-lookup"><span data-stu-id="deacf-119">91</span></span>|<span data-ttu-id="deacf-120">Fine del conflitto.</span><span class="sxs-lookup"><span data-stu-id="deacf-120">Contention ends.</span></span>|

<span data-ttu-id="deacf-121">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="deacf-121">The following table shows event data:</span></span>

|<span data-ttu-id="deacf-122">Nome campo</span><span class="sxs-lookup"><span data-stu-id="deacf-122">Field name</span></span>|<span data-ttu-id="deacf-123">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="deacf-123">Data type</span></span>|<span data-ttu-id="deacf-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="deacf-124">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="deacf-125">Flags</span><span class="sxs-lookup"><span data-stu-id="deacf-125">Flags</span></span>|<span data-ttu-id="deacf-126">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="deacf-126">win:UInt8</span></span>|<span data-ttu-id="deacf-127">0 per gestito, 1 per nativo.</span><span class="sxs-lookup"><span data-stu-id="deacf-127">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="deacf-128">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="deacf-128">ClrInstanceID</span></span>|<span data-ttu-id="deacf-129">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="deacf-129">win:UInt16</span></span>|<span data-ttu-id="deacf-130">ID univoco per l'istanza di CLR.</span><span class="sxs-lookup"><span data-stu-id="deacf-130">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="deacf-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deacf-131">See also</span></span>

- [<span data-ttu-id="deacf-132">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="deacf-132">CLR ETW Events</span></span>](clr-etw-events.md)
