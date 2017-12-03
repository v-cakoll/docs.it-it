---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c2214ec48f0c1cba1e3aacad0eaa5a29625f9c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="da78d-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="da78d-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="da78d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="da78d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da78d-104">ID</span><span class="sxs-lookup"><span data-stu-id="da78d-104">ID</span></span>|<span data-ttu-id="da78d-105">4203</span><span class="sxs-lookup"><span data-stu-id="da78d-105">4203</span></span>|  
|<span data-ttu-id="da78d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="da78d-106">Keywords</span></span>|<span data-ttu-id="da78d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="da78d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="da78d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="da78d-108">Level</span></span>|<span data-ttu-id="da78d-109">Errore</span><span class="sxs-lookup"><span data-stu-id="da78d-109">Error</span></span>|  
|<span data-ttu-id="da78d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="da78d-110">Channel</span></span>|<span data-ttu-id="da78d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="da78d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da78d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da78d-112">Description</span></span>  
 <span data-ttu-id="da78d-113">Indica che il provider SQL non è in grado di estendere la scadenza del blocco perché la scadenza è già passata o il proprietario del blocco è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="da78d-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="da78d-114">SqlWorkflowInstanceStore verrà interrotto.</span><span class="sxs-lookup"><span data-stu-id="da78d-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da78d-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="da78d-115">Message</span></span>  
 <span data-ttu-id="da78d-116">Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato.</span><span class="sxs-lookup"><span data-stu-id="da78d-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="da78d-117">Interruzione di SqlWorkflowInstanceStore in corso.</span><span class="sxs-lookup"><span data-stu-id="da78d-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da78d-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="da78d-118">Details</span></span>  
  
|<span data-ttu-id="da78d-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="da78d-119">Data Item Name</span></span>|<span data-ttu-id="da78d-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="da78d-120">Data Item Type</span></span>|<span data-ttu-id="da78d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da78d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da78d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da78d-122">AppDomain</span></span>|<span data-ttu-id="da78d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="da78d-123">xs:string</span></span>|<span data-ttu-id="da78d-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="da78d-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
