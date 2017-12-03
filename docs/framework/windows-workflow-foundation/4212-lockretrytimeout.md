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
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="58d70-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="58d70-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="58d70-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="58d70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58d70-104">ID</span><span class="sxs-lookup"><span data-stu-id="58d70-104">ID</span></span>|<span data-ttu-id="58d70-105">4212</span><span class="sxs-lookup"><span data-stu-id="58d70-105">4212</span></span>|  
|<span data-ttu-id="58d70-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="58d70-106">Keywords</span></span>|<span data-ttu-id="58d70-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="58d70-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="58d70-108">Livello</span><span class="sxs-lookup"><span data-stu-id="58d70-108">Level</span></span>|<span data-ttu-id="58d70-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="58d70-109">Warning</span></span>|  
|<span data-ttu-id="58d70-110">Canale</span><span class="sxs-lookup"><span data-stu-id="58d70-110">Channel</span></span>|<span data-ttu-id="58d70-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="58d70-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="58d70-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58d70-112">Description</span></span>  
 <span data-ttu-id="58d70-113">Timeout rilevato del provider SQL durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="58d70-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="58d70-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="58d70-114">Message</span></span>  
 <span data-ttu-id="58d70-115">Timeout durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="58d70-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="58d70-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="58d70-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="58d70-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="58d70-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="58d70-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="58d70-118">Details</span></span>  
  
|<span data-ttu-id="58d70-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="58d70-119">Data Item Name</span></span>|<span data-ttu-id="58d70-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="58d70-120">Data Item Type</span></span>|<span data-ttu-id="58d70-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58d70-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="58d70-122">Delay</span><span class="sxs-lookup"><span data-stu-id="58d70-122">Delay</span></span>|<span data-ttu-id="58d70-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="58d70-123">xs:string</span></span>|<span data-ttu-id="58d70-124">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="58d70-124">The delay between retries.</span></span>|  
|<span data-ttu-id="58d70-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="58d70-125">AppDomain</span></span>|<span data-ttu-id="58d70-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="58d70-126">xs:string</span></span>|<span data-ttu-id="58d70-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="58d70-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
