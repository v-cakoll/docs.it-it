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
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="b5d68-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="b5d68-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="b5d68-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b5d68-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5d68-104">ID</span><span class="sxs-lookup"><span data-stu-id="b5d68-104">ID</span></span>|<span data-ttu-id="b5d68-105">4203</span><span class="sxs-lookup"><span data-stu-id="b5d68-105">4203</span></span>|  
|<span data-ttu-id="b5d68-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b5d68-106">Keywords</span></span>|<span data-ttu-id="b5d68-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b5d68-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b5d68-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b5d68-108">Level</span></span>|<span data-ttu-id="b5d68-109">Errore</span><span class="sxs-lookup"><span data-stu-id="b5d68-109">Error</span></span>|  
|<span data-ttu-id="b5d68-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b5d68-110">Channel</span></span>|<span data-ttu-id="b5d68-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b5d68-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b5d68-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5d68-112">Description</span></span>  
 <span data-ttu-id="b5d68-113">Indica che il provider SQL non è in grado di estendere la scadenza del blocco perché la scadenza è già passata o il proprietario del blocco è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="b5d68-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="b5d68-114">SqlWorkflowInstanceStore verrà interrotto.</span><span class="sxs-lookup"><span data-stu-id="b5d68-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b5d68-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b5d68-115">Message</span></span>  
 <span data-ttu-id="b5d68-116">Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato.</span><span class="sxs-lookup"><span data-stu-id="b5d68-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="b5d68-117">Interruzione di SqlWorkflowInstanceStore in corso.</span><span class="sxs-lookup"><span data-stu-id="b5d68-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b5d68-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b5d68-118">Details</span></span>  
  
|<span data-ttu-id="b5d68-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b5d68-119">Data Item Name</span></span>|<span data-ttu-id="b5d68-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b5d68-120">Data Item Type</span></span>|<span data-ttu-id="b5d68-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5d68-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b5d68-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b5d68-122">AppDomain</span></span>|<span data-ttu-id="b5d68-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d68-123">xs:string</span></span>|<span data-ttu-id="b5d68-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b5d68-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
