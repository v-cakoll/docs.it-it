---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f47b383547da5145c5307670fee2eda10fcab402
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="c1ff1-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="c1ff1-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="c1ff1-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c1ff1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1ff1-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1ff1-104">ID</span></span>|<span data-ttu-id="c1ff1-105">4212</span><span class="sxs-lookup"><span data-stu-id="c1ff1-105">4212</span></span>|  
|<span data-ttu-id="c1ff1-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c1ff1-106">Keywords</span></span>|<span data-ttu-id="c1ff1-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c1ff1-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c1ff1-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c1ff1-108">Level</span></span>|<span data-ttu-id="c1ff1-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="c1ff1-109">Warning</span></span>|  
|<span data-ttu-id="c1ff1-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c1ff1-110">Channel</span></span>|<span data-ttu-id="c1ff1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c1ff1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1ff1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1ff1-112">Description</span></span>  
 <span data-ttu-id="c1ff1-113">Timeout rilevato del provider SQL durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1ff1-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c1ff1-114">Message</span></span>  
 <span data-ttu-id="c1ff1-115">Timeout durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="c1ff1-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="c1ff1-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1ff1-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c1ff1-118">Details</span></span>  
  
|<span data-ttu-id="c1ff1-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c1ff1-119">Data Item Name</span></span>|<span data-ttu-id="c1ff1-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c1ff1-120">Data Item Type</span></span>|<span data-ttu-id="c1ff1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1ff1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1ff1-122">Delay</span><span class="sxs-lookup"><span data-stu-id="c1ff1-122">Delay</span></span>|<span data-ttu-id="c1ff1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1ff1-123">xs:string</span></span>|<span data-ttu-id="c1ff1-124">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-124">The delay between retries.</span></span>|  
|<span data-ttu-id="c1ff1-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1ff1-125">AppDomain</span></span>|<span data-ttu-id="c1ff1-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1ff1-126">xs:string</span></span>|<span data-ttu-id="c1ff1-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c1ff1-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
